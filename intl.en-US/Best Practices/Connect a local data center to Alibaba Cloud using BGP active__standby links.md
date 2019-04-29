# Connect a local data center to Alibaba Cloud using BGP active/standby links {#concept_h3t_bnn_l2b .concept}

This tutorial introduces how to use physical connections and CEN to connect a local data center to Alibaba Cloud, and enable the local data center to communicate with VPCs in different regions.

## Overview {#section_mch_fwn_l2b .section}

To configure active/standby links to access Alibaba Cloud, follow these steps:

1.  Build redundant physical connections

    Create redundant physical connections to connect the local data center to Alibaba Cloud. Configure BGP routing between the local data center and the VBRs.

2.  Configure health checks

    Configure health checks so that when the active link fails, traffic is distributed to the standby link. For more information, see [Health check](../../../../reseller.en-US/User Guide/Health check.md#).

3.  Attach the VBRs and VPCs that the local data center requires to connect to the created CEN instance.
4.  Configure routes

    You can set the routing priority by configuring the length of the AS-Path. For more information, see [Advertise BGP routes and set the routing weights at the local data center](#section_kvd_hqn_l2b).


## Network topology {#section_nhs_nnn_l2b .section}

The network topology used in this tutorial is as follows:

-   The local data center is already connected to different VBRs through redundant physical connections. The BGP protocol is used between the local data center and the VBRs.
-   Separate VPCs are already created in the China \(Beijing\), China \(Shanghai\), and Hong Kong regions.
-   The CIDR blocks used in this tutorial are as follows:

    |Network|CIDR block|
    |:------|:---------|
    |Local data center|10.1.1.0/24|
    |Beijing VPC|192.168.1.0/24|
    |Hong Kong VPC|192.168.2.0/24|
    |Shanghai VPC|192.168.3.0/24|


![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/15565156737114_en-US.png)

## Advertise BGP routes and set the routing weights at the local data center {#section_kvd_hqn_l2b .section}

Assume that BGP peering sessions have been established between the local data center and each VBR \(for more information, see [Create a BGP peer](../../../../reseller.en-US/Archives/BGP/Manage BGP peers.md#section_fxm_rbb_ydb)\).

You must configure the BGP route \(10.1.1.0/24\) advertised to Alibaba Cloud and set the AS-Path to determine the routing weights at the local data center to implement active/standby routes from Alibaba Cloud to IDC.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/15565156737115_en-US.png)

As shown in the preceding figure, the green line \(CPE1\) is the active link and the red line \(CPE2\) is the standby link. The BGP configurations of the two CPEs are as follows.

You can set the routing priority by configuring the AS-Path length. The shorter the As-Path length, the higher the priority.

|Configuration|CPE1|CPE2|
|:------------|:---|:---|
|Vlan Tag|110|120|
|Network|10.1.1.0/24|10.1.1.0/24|
|BGP ASN|XXX|XXX|
|Interface IP|172.16.100.0/24|172.16.2.1/24|
|As-Path|B,A|C,B,A|

The CEN can automatically learn and distribute route entries. After routes are configured, the CEN synchronizes the routes to attached networks based on the routing weights.

-   BGP routes in VBRs

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/15565156737116_en-US.png)

    As shown in the following figure, the route tables of VBR1 and VBR2 contain routes and next hops learned from the BGP peers of VBR1 and VBR2. The VBRs, which are attached to the CEN, send the BGP routes learned from the local data center to the CEN, including AS-Path configurations.

-   All routes in the CEN

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/15565156737117_en-US.png)

    After the VPCs and VBRs are attached to CEN, the BGP routes learned from the VBRs are distributed to the CEN. The CEN then synchronizes the routes to all attached networks based on the routing weights.

    The BGP routes that the VBRs learn from the local data center share the same destination CIDR block but have different routing weights. The physical connection connected to VBR1 acts as the active link \(the AS-Path is shorter\), and the one connected to VBR2 acts as the standby link. CEN will synchronize this routing configuration to other attached networks, such as VPCs. As shown in the route tables of the VPCs, all routes destined for 10.1.1.0/24 point to VBR1.

    Additionally, CEN redistributes CEN system routes to the BGP network. Therefore, the BGP route table of the local data center includes the learned CEN routes and the next hops are the interface IPs of the two VBRs.

    Similarly, if you want to configure active/standby links that connect the local data center to the Alibaba Cloud IP address \(192.168. X. 0/24\), you can do this by configuring the BGP AS-Path. Configure weights for the routes learned from different BGP peers \(192.168. X. 0/24\).


