# IDC通过VPN网关上云方案 {#concept_h3t_bnn_l2b .concept}

本教程介绍通过VPN网关和云企业网组合的方式，实现客户IDC上云，并和云上不同地域VPC互通的场景。

## 方案概述 {#section_mch_fwn_l2b .section}

完成以下操作，将本地IDC接入阿里云：

1.  配置VPN网关

    创建IPSec-VPN连接，将本地IDC接入阿里云。详情参见[建立站点到站点连接](../../../../intl.zh-CN/IPsec-VPN入门/建立站点到站点连接.md#)。

2.  加载网络实例

    将需要互通的VBR和VPC加载到已创建的云企业网实例中。

3.  配置和发布路由

    您可以将VPC中指向VPN网关的路由发布到CEN中，CEN中其他加载的网络实例便可以学习到该条路由。


## 网络拓扑 {#section_nhs_nnn_l2b .section}

本方案中使用的网络拓扑如下：

-   本地IDC已通过VPN网关连接到阿里云。
-   分别在杭州、北京、香港和上海地域部署了VPC。
-   本方案中各网络的网段如下表所示，确保各VPC的地址段不冲突。

    |网络|网段|
    |:-|:-|
    |本地IDC|10.1.1.0/24|
    |北京VPC|192.168.1.0/24|
    |香港VPC|192.168.2.0/24|
    |上海VPC|192.168.3.0/24|
    |杭州VPC|192.168.4.0/24|


![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15565158688697_zh-CN.png)

## IDC路由配置 {#section_kvd_hqn_l2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15565158688698_zh-CN.png)

本地IDC已与阿里云VPN网关之间建立起IPsec-VPN连接，并且已配置指向云上的明细路由或默认路由：

|目标网段|下一跳|
|:---|:--|
|192.168.1.0/24|VPN网关|
|192.168.2.0/24|VPN网关|
|192.168.3.0/24|VPN网关|
|192.168.4.0/24|VPN网关|

|目标网段|下一跳|
|:---|:--|
|0.0.0.0/0|VPN网关|

## VPC路由配置 {#section_gxw_wlc_r2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15565158688708_zh-CN.png)

为了能够让IDC和云上的VPC之间互相通信，需要在连接VPN网关的VPC内，配置一条指向IDC侧（VPN网关）的路由，并且宣告到CEN。

IDC侧已经配置了指向云上的路由，那么数据流量便可从云下到达云上；在杭州VPC内，配置一条回程路由指向VPN网关，便可实现流量从杭州VPC到达云下IDC。

如下图所示，您需要在杭州VPC内配置指向VPN网关（IDC）的自定义路由：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15565158688709_zh-CN.png)

在杭州VPC路由表中可以看到该条指向VPN网关的路由：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15565158688710_zh-CN.png)

## 在CEN中宣告路由 {#section_u2m_dkd_r2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15565158698711_zh-CN.png)

为了能够让CEN内其他VPC学习到指向IDC的路由，需要在杭州VPC将指向VPN网关的路由发布到CEN内，其他VPC便可学习到该条路由。

路由发布前

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15565158698712_zh-CN.png)

路由发布后

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15565158698713_zh-CN.png)

CEN内其他VPC路由表如下图所示。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15565158698714_zh-CN.png)

通过以上操作，可以看到加载到CEN中的其他VPC已经学习到了该条指向IDC的路由，本地IDC便可和CEN内的任意VPC之间进行通信。

## CEN发布路由功能说明 {#section_lbw_mld_r2b .section}

以上方案只是对加载到CEN中的网络实例向CEN发布或撤销路由的一种场景，对于加载到CEN中的VPC/VBR，支持如下的路由发布或撤销操作：

|路由类型|路由所属实例|是否默认发布到CEN|
|:---|:-----|:---------|
|指向ECS实例的路由|VPC|否|
|指向VPN网关的路由|VPC|否|
|指向高可用虚拟IP的路由|VPC|否|
|VPC系统路由|VPC|是|
|指向IDC的路由|VBR|是|
|BGP路由|VBR|是|

以上发布到CEN中的路由，均可进行撤销操作。路由撤销后，CEN中将不再存在该路由条目。

对于各条自定义路由，如果已发布到CEN中，在VPC上删除该自定义路由后，该路由也将从CEN中删除。

**说明：** 目前控制台只支持VPC的路由发布和撤销，VBR路由的发布和撤销操作暂不支持，您可以通过调用Open API[PublishRouteEntries](../../../../intl.zh-CN/API参考/管理路由/PublishRouteEntries.md#)发布、撤销VBR路由条目。

