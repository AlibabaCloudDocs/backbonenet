# Connect a local data center to Alibaba Cloud using two leased lines configured with static routes {#concept_h3t_bnn_l2b .concept}

This tutorial introduces how to use leased lines and CEN to connect an IDC to Alibaba Cloud and enable the IDC to communicate with VPCs in different regions.

## Solution overview {#section_mch_fwn_l2b .section}

To connect a local IDC to Alibaba Cloud, complete these steps:

1.  Build redundant leased lines

    Create redundant leased lines to connect the local data center to Alibaba Cloud. Configure static routes between the IDC and the VBRs. For more information, see [Redundant physical connection](../../../../intl.en-US/User Guide/Redundant physical connection.md#). 

2.  Configure health check \(required\)

    Configure health check. Therefore, the traffic can be automatically routed to the standby link when the active link fails. When configuring health check, you can set any unused private IP address in a VPC attached to the CEN instance as the source IP address, and set the IP address of the CPE interface connected to the VBR as the destination IP address. For more information, see [Health check](../../../../intl.en-US/UserGuide/Health check.md#). 

3.  Attach networks

    Attach the VBRs and VPCs to the created CEN instance. For more information, see [Attach networks](../../../../intl.en-US/UserGuide/Networks.md#section_s4y_4mh_tdb). 

4.  Configure and publish routes

    Configure routes in the IDC and VPCs. For more information, see [IDC and VBR static route configuration](#section_kvd_hqn_l2b).


## Network architecture {#section_nhs_nnn_l2b .section}

The network architecture used in this tutorial is as follows:

-   The local data center is already connected to the VBRs through two leased lines. Configure static routes between the IDC and the VBRs.
-   Three VPCs are already created in the China \(Beijing\), China \(Shanghai\), and China \(Hong Kong\) regions.
-   The CIDR blocks of networks used in this tutorial are as follows:

    |Network|CIDR Block|
    |:------|:---------|
    |Local data center|10.1.1.0/24|
    |Beijing VPC|192.168.1.0/24|
    |Shanghai VPC|192.168.1.0/24|
    |Hong Kong VPC|192.168.3.0/24|


![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17033/15335366918693_en-US.png)

## IDC and VBR static route configuration {#section_kvd_hqn_l2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17033/15335366918694_en-US.png)

The routing configurations in this tutorial are as follows:

-   IDC route configuration

    Configure a static route pointing to Alibaba Cloud on CPE1 and CPE2 respectively.

    |Configuration|CPE1|CPE2|
    |:------------|:---|:---|
    |Destination CIDR Block|192.168.0.0/16|192.168.0.0/16|
    |Next hop|172.16.1.2/24 \(VBR1\)|172.16.2.2/24 \(VBR2\)|

-   VBR route configuration

    Configure a static route pointing to the local IDC on VBR1 and VBR2 respectively.

    |Configuration|VBR1|VBR2|
    |:------------|:---|:---|
    |Destination CIDR Block|10.1.1.0/24|10.1.1.0/24|
    |Next hop|172.16.100.0/24|172.16.2.1/24|

-   CEN routes

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17033/15335366918695_en-US.png)

    After configuring routes for the VBRs, the CEN publishes the configured static routes to the CEN. In CEN, the two leased lines form ECMP and are in active-active status.


## Redundant disaster tolerance {#section_gxw_wlc_r2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17033/15335366918696_en-US.png)

When a leased line fails \(such as the line from VBR1 to CPE1\), data from Alibaba Cloud to the IDC is forwarded to VBR2. This solution achieves disaster tolerance by automatically switching the link.

