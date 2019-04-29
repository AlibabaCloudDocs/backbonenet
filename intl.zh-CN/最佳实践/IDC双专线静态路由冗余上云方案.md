# IDC双专线静态路由冗余上云方案 {#concept_h3t_bnn_l2b .concept}

本教程介绍通过专线接入和云企业网组合的方式，实现客户IDC冗余专线上云，并和云上不同地域VPC互通的场景。

## 方案概述 {#section_mch_fwn_l2b .section}

完成以下操作，将本地IDC接入阿里云：

1.  搭建冗余物理专线

    创建冗余物理专线，将本地IDC接入阿里云。本地IDC和边界路由器之间配置静态路由。

2.  配置健康检查（必须配置）

    设置健康检查，是保障等价冗余专线链路中一条链路中断后，流量可以切换到另外一条链路的前提。在配置健康检查时，您可以将CEN中加载的VPC中任何一个未被使用的私网IP配置为源IP，将和VBR互联的CPE接口IP配置为目标IP。详情参见[健康检查](../../../../intl.zh-CN/用户指南/健康检查.md#)。

3.  加载网络实例

    将需要互通的VBR和VPC加载到已创建的云企业网实例中。

4.  配置和发布路由

    在本地IDC和VPC中分别配置路由，详情参见[IDC和VBR静态路由配置](#section_kvd_hqn_l2b)。


## 网络拓扑 {#section_nhs_nnn_l2b .section}

本方案中使用的网络拓扑如下：

-   本地IDC已通过专线双冗余方式连接到阿里云的不同边界路由器（VBR）。IDC和VBR之间配置静态路由。
-   分别在北京、香港和上海地域部署了VPC。
-   本方案中各网络的网段如下表所示。

    |网络|网段|
    |:-|:-|
    |本地IDC|10.1.1.0/24|
    |北京VPC|192.168.1.0/24|
    |香港VPC|192.168.2.0/24|
    |上海VPC|192.168.3.0/24|


![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17033/15565157508693_zh-CN.png)

## IDC和VBR静态路由配置 {#section_kvd_hqn_l2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17033/15565157508694_zh-CN.png)

本方案中的路由配置如下：

-   IDC路由配置

    分别在CPE1和CPE2上配置指向阿里云的静态路由，实现IDC到云上的路由。

    |配置|CPE1|CPE2|
    |:-|:---|:---|
    |目标网段|192.168.0.0/16|192.168.0.0/16|
    |下一跳|172.16.1.2/24 \(VBR1\)|172.16.2.2/24 \(VBR2\)|

-   VBR路由配置

    分别在VBR1和VBR2上配置指向本地IDC的静态路由，实现云上到IDC的路由。

    |配置|VBR1|VBR2|
    |:-|:---|:---|
    |目标网段|10.1.1.0/24|10.1.1.0/24|
    |下一跳|172.16.1.1/24|172.16.2.1/24|

-   云企业网路由

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17033/15565157508695_zh-CN.png)

    通过在VBR上进行以上路由配置，云企业网会分别将VBR1和VBR2上配置的静态路由同步到云企业网内部。从云企业网内部看，两条专线已形成等价路由（ECMP），并且处于双活状态。


## 冗余容灾 {#section_gxw_wlc_r2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17033/15565157508696_zh-CN.png)

当某条专线断掉后（如VBR1到CPE1），云企业网会对路由进行切换，云上所有到IDC的数据会走VBR2，从而实现了链路的切换和容灾效果。

