# Connect a local data center to Alibaba Cloud using BGP active/standby links {#concept_h3t_bnn_l2b .concept}

This tutorial introduces how to use a Cloud Enterprise Network \(CEN\) and leased lines to build a hybrid cloud with active/standby links.

## Solution overview {#section_mch_fwn_l2b .section}

Complete these steps to configure an active/standby link that enables access to Alibaba Cloud:

1.  Build redundant leased lines

    Create redundant leased lines to connect the local data center to Alibaba Cloud. Configure BGP routing between the local data center and the VBRs. For more information, see [Redundant physical connection](../../../../intl.en-US/User Guide/Redundant physical connection.md#).

2.  Configure health check

    Configure health check so that when the active link fails, traffic will automatically be sent on the standby link instead. For more information, see [Health check](../../../../intl.en-US/UserGuide/Health check.md#).

3.  Attach networks

    Attach VBRs and VPCs to the created CEN instance. For more information, see [Connect network instances in different regions using same account](../../../../intl.en-US/Quick Start/Connect network instances in different regions using same account.md#).

4.  Configure routing

    You can set the routing priority by configuring the length of the AS-Path. For more information, see [Advertise the BGP network and set the routing weights at the local IDC](#section_kvd_hqn_l2b).


## Network architecture {#section_nhs_nnn_l2b .section}

The network architecture used in this tutorial is as follows:

-   The local data center is already connected to Alibaba Cloud VBRs with two redundant leased lines. The BGP protocol is used between the local data center and the VBRs.
-   Three VPCs are already created in China \(Beijing\), China \(Shanghai\), and China \(Hong Kong\) regions.
-   The CIDR blocks of networks used in this tutorial are as follows:

    |Network|CIDR Block|
    |:------|:---------|
    |Local data center|10.1.1.0/24|
    |Beijing VPC|192.168.1.0/24|
    |Shanghai VPC|192.168.1.0/24|
    |Hong Kong VPC|192.168.3.0/24|


![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/7114_en-US.png)

## Advertise the BGP network and set the routing weights at the local IDC {#section_kvd_hqn_l2b .section}

Assume that the local data center and the VBRs have both created BGP peers \(for more information, see [Create a BGP peer](../../../../intl.en-US/User Guide/BGP/Manage BGP peers.md#section_fxm_rbb_ydb)\).

You must configure a BGP route \(10.1.1.0/24\) advertised to Alibaba Cloud and configure routing weights by setting the AS-Path at the local data center to implement active/standby routing from Alibaba Cloud to IDC.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/7115_en-US.png)

As shown in the preceding figure, the green link \(CPE1\) is the active link and the red one \(CPE2\) is the standby link. The BGP configurations of these two CPEs are as follows.

You can set the routing priority by configuring the AS-Path length. The shorter the As-Path length, the higher the priority.

|Configuration|CPE1|CPE2|
|:------------|:---|:---|
|Vlan Tag|110|120|
|Network|10.1.1.0/24|10.1.1.0/24|
|BGP ASN|XXX|XXX|
|Interface IP|172.16.1.1/24|172.16.2.1/24|
|As-Path|B,A|C,B,A|

CEN can automatically learn routing entries from the attached networks, and also propagate its own routing entries to them. After a VBR learns a route from IDC, CEN synchronizes the route to the networks attached to it with route weight.

-   BGP routing in VBR

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/7116_en-US.png)

    As shown in the following figure, the routing tables of VBR1 and VBR2 contain routing information and next hops learned from the BGP peers of VBR1 and VBR2. The VBRs, which are attached to the CEN, send the BGP routing information learned from the local data center to the CEN, including AS-Path properties.

-   Full routing table

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15706/7117_en-US.png)

    After attaching the VPC and VBR to CEN, the BGP route that the VBR learned are propagated to CEN. The CEN then synchronizes the routes to all attached networks based on the routing property.

    The BGP route that the VBRs learned from the local data center has the same destination CIDR but have different routing property. The leased line connected to VBR1 acts as the active link \(the AS-Path is shorter\), and the one connected to VBR2 acts as the standby link. CEN will synchronize this route information to other networks attached to it, such as VPCs. As shown in the VPC routing tables, all routes to 10.1.1.0/24 point to VBR1.

    Additionally, CEN propagates CEN system routes into BGP network. Therefore, the routing table of the local data center includes the CEN routes and the next hops are the IP addresses of the two VBR interfaces.

    Similarly, if you want to configure an active/standby route that from the local IDC to the Alibaba Cloud \(192.168. x. 0/24\), you can do this by configuring the BGP properties like weight.


