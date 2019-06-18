# 配置BFD功能 {#concept_525843 .concept}

BFD（Bidirectional Forwarding Detection）是一种网络监测协议，提供了一个标准化的与介质和上层协议无关的快速故障检测机制。云企业网支持配置支持BFD。

## BFD概述 {#section_6ft_85n_uh8 .section}

BFD在两台网络设备上建立会话，用来检测网络设备间的双向转发路径，为上层应用服务。BFD本身并没有邻居发现机制，而是依靠被服务的上层应用通知其邻居信息以建立会话。会话建立后会周期性地快速发送BFD报文，如果在检测时间内没有收到BFD报文则认为该双向转发路径发生了故障，通知被服务的上层应用进行相应的处理。

BFD功能具有以下优势：

-   对网络设备间任意类型的双向转发路径进行故障检测，包括直连物理链路、虚电路、隧道、MPLS LSP、多跳路由路径以及单向链路等。
-   可以为不同的上层应用服务，提供一致的快速故障检测时间。
-   提供小于1秒的检测时间，从而加快网络收敛速度，减少应用中断时间，提高网络的可靠性。

## 使用限制 {#section_x2l_9pu_slg .section}

默认情况不支持在边界路由器（VBR）上开启BFD功能，如有需要请提交工单。

## 配置BFD {#section_z4a_a5u_92b .section}

您可以使用以下API配置BFD。

|配置|API|参数说明|
|--|---|----|
|创建BGP邻居时开启/关闭BFD|[CreateBgpPeer](../../../../cn.zh-CN/API参考/BGP/CreateBgpPeer.md#)|在CreateBgpPeer接口中指定EnableBfd参数，取值： -   true：开启BFD功能。
-   false：不开启BFD功能。

 |
|修改BGP邻居属性时开启/关闭BFD|[ModifyBgpPeerAttribute](../../../../cn.zh-CN/.md#)|在ModifyBgpPeerAttribute接口中指定EnableBfd参数，取值： -   true：开启BFD功能。
-   false：不开启BFD功能。

 |
|查看BFD状态|[DescribeBgpPeers](../../../../cn.zh-CN/API参考/BGP/DescribeBgpPeers.md#)|在DescribeBgpPeers接口的返回值中查看EnableBfd参数： -   true：处于开启BFD状态。
-   false：处于未开启BFD状态。

 |
|配置BFD参数|[ModifyVirtualBorderRouterAttribute](../../../../cn.zh-CN/API参考/边界路由器/ModifyVirtualBorderRouterAttribute.md#)|在ModifyVirtualBorderRouterAttribute接口中指定以下参数： -   MinTxInterval：配置BFD报文的发送间隔，取值：200-1000，单位为ms。
-   MinRxInterval：配置BFD报文的接收间隔，取值：200-1000，单位为ms。
-   DetectMultiplier：检测时间倍数。即接收方允许发送方发送报文的最大连接丢包数，用来检测链路是否正常，取值：3-10。

 |
|查看配置的BFD参数|[DescribeVirtualBorderRouters](../../../../cn.zh-CN/API参考/边界路由器/DescribeVirtualBorderRouters.md#)|在DescribeVirtualBorderRouters接口中查看返回值中的MinTxInterval、MinRxInterval和DetectMultiplier字段。 -   MinTxInterval：BFD报文的发送间隔，单位为ms。
-   MinRxInterval：报文的接收间隔，单位为ms。
-   DetectMultiplier：检测时间倍数。即接收方允许发送方发送报文的最大连接丢包数，用来检测链路是否正常。

 |

