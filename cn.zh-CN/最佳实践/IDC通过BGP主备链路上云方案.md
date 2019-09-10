# IDC通过BGP主备链路上云方案 {#concept_h3t_bnn_l2b .concept}

本教程介绍通过专线接入和云企业网组合的方式，实现客户IDC通过主备链路上云，并和云上不同地域VPC互通的场景。

## 方案概述 {#section_mch_fwn_l2b .section}

完成以下操作，配置主备选路（主链路优先）接入阿里云：

1.  搭建冗余物理专线

    创建冗余物理专线，将本地IDC接入阿里云。本地IDC和边界路由器之间配置BGP路由。

2.  配置健康检查

    设置健康检查，是保障等价冗余专线链路中一条链路中断后，流量可以切换到另外一条链路的前提。详情参见[设置健康检查](../../../../cn.zh-CN/用户指南/健康检查/设置健康检查.md#)。

3.  加载网络实例将需要互通的VBR和VPC加载到已创建的云企业网实例中。
4.  配置路由

    您可以通过设置AS-Path的长度来确定路由选路的优先级。详情参见[IDC侧宣告BGP路由并设置权重](#section_kvd_hqn_l2b)。


## 网络拓扑 {#section_nhs_nnn_l2b .section}

本方案中使用的网络拓扑如下：

-   本地IDC已通过专线双冗余方式连接到阿里云的不同边界路由器（VBR）。IDC和VBR之间采用BGP路由协议。
-   分别在北京、香港和上海地域部署了VPC。
-   本方案中各网络的网段如下表所示。

    |网络|网段|
    |:-|:-|
    |本地IDC|10.1.1.0/24|
    |北京VPC|192.168.1.0/24|
    |香港VPC|192.168.2.0/24|
    |上海VPC|192.168.3.0/24|


![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/15681130047114_zh-CN.png)

## IDC侧宣告BGP路由并设置权重 {#section_kvd_hqn_l2b .section}

假设IDC和边界路由器之间分别已经建立起BGP邻居关系（详情参见[创建BGP邻居](../../../../cn.zh-CN/历史文档/BGP/管理BGP邻居.md#section_fxm_rbb_ydb)）。

现在需要在IDC侧配置向阿里云宣告的BGP路由（10.1.1.0/24），并通过设置AS-Path来确定选路权重，实现阿里云到IDC路由的主备模式。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/15681130047115_zh-CN.png)

如上图所示，绿色链路（CPE1）为主链路，红色链路（CPE2）为备份链路，则IDC侧分别在两个CPE的BGP配置如下表所示。

您可以通过设置AS-Path的长度来确定路由选路的优先级。As-Path长度越短，优先级越高。

|配置|CPE1|CPE2|
|:-|:---|:---|
|Vlan Tag|110|120|
|Network|10.1.1.0/24|10.1.1.0/24|
|BGP ASN|XXX|XXX|
|Interface IP|172.16.1.1/24|172.16.2.1/24|
|As-Path|B,A|C,B,A|

云企业网具备自动学习分发路由的能力，在配置好路由后，云企业网会基于选路权重等信息，将路由同步到云企业网内部。

-   边界路由器BGP路由

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/15681130047116_zh-CN.png)

    如上图所示，在VBR1和VBR2可以看到从对端邻居学到的路由信息和下一跳。由于VBR已经加载到云企业网中，所以VBR会将从IDC侧学来的BGP路由信息发送到云企业网，包括AS-Path。

-   全量路由配置

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/15681130047117_zh-CN.png)

    由于VBR和VPC均已加载到云企业网中，那么从VBR上学来的BGP路由也会发布到云企业网中，云企业网会基于选路权重等信息，将路由同步到云企业网内部。

    两个VBR从IDC侧学习到的BGP路由目标网段一致，但是路由权重不同，VBR1作为主选路（AS-Path短），VBR2是备选（AS-Path长），那么云企业网会将该路由的属性通知到云企业网中的其他网络实例例如VPC。从VPC的路由表中就可以看到去往10.1.1.0/24的路由均指向VBR1。

    云企业网也会将云企业网内系统路由重发布到BGP中，所以在IDC的BGP路由表中就可以看到学习到的云企业网中的路由信息，并且下一跳分别指向与IDC建立邻居的两个VBR的接口IP。

    同理，如果想从IDC侧设置到阿里云业务地址（192.168.X.0/24）的主备链路，同样可以通过BGP选路属性，在IDC侧分别设置从不同邻居（VBR1，VBR2）学习到的路由192.168.X.0/24的权重，便可实现从IDC到阿里云的主备选路。


