# Connect a local data center to Alibaba Cloud using active/standby links formed by a leased line and a Smart Access Gateway {#concept_abc_sxm_sfb .concept}

This topic introduces how to use CEN, a leased line and a Smart Access Gateway to connect a local IDC to Alibaba Cloud and enable the local IDC to communicate with VPCs in different regions through active/standby links formed by a leased line and a Smart Access Gateway.

You can connect a local IDC to Alibaba Cloud through active/standby redundant links formed by a leased line and a Smart Access Gateway. The leased line is connected to the VBR through BGP protocol and acts as the active link. The Smart Access Gateway is connected to the CEN through CCN and acts as the standby link. When the leased line fails, the traffic is automatically distributed to the link of the Smart Access Gateway to achieve high availability.

## Network topology {#section_l1m_1ym_sfb .section}

The network topology is as follows:

-   The local IDC is connected to Alibaba Cloud through redundant links formed by the leased line and the Smart Access Gateway. The leased line uses BGP protocol.
-   Cloud services are deployed in Beijing, Hong Kong, and Shanghai respectively.
-   Ensure that the CIDR blocks of VPCs in different regions do not conflict with the CIDR block of the local IDC. The CIDR blocks of the VPCs and local IDC in this topic are as follows:

    |Network|CIDR block|
    |:------|:---------|
    |Beijing VPC|192.168.1.0/24|
    |Hong Kong VPC|192.168.2.0/24|
    |Shanghai VPC|192.168.3.0/24|
    |Local IDC|10.1.1.0/24|

-   The Smart Access Gateway and the VBR connected to the leased line are attached to the CEN.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/60922/155919517530839_en-US.png)


## Overview {#section_ds1_lsn_sfb .section}

**Route priority within the CEN**

When a leased line and a Smart Access Gateway destined to the same CIDR block are connected to a CEN, the route priority within the CEN is: the leased line takes precedence over Smart Access Gateway.

**1. The leased line advertises a BGP route**

Assume that the local IDC and the VBR are each other's BGP peer.

Now you need to configure the BGP CIDR block 10.1.1.0/24 advertised to Alibaba Cloud in the local IDC. The CPE1 configurations of the local IDC are as follows.

|Configuration|Value|
|:------------|:----|
|Vlan Tag|110|
|Network|10.1.1.0/24|
|BGP ASN|xxx|
|Interface IP|172.16.1.1/24|

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/60922/155919517530840_en-US.png)

**2. Configure the Smart Access Gateway** 

1.  On the Smart Access Gateway console, select the leased line that forms the active/standby links with the Smart Access Gateway \(The leased line always acts as the active link\).
2.  On the Smart Access Gateway console, configure the CIDR block of the local IDC.

    The Smart Access Gateway has been attached to the CEN. You need to configure the CIDR block 10.1.1.0/24 of the local IDC in the Smart Access Gateway.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/60922/155919517530842_en-US.png)


**Note:** You must follow the preceding order when you configure the active/standby links. You must configure the active/standby links first and configure the local IDC CIDR block in the Smart Access Gateway second. If you configure the local IDC CIDR block in the Smart Access Gateway first, the CIDR block cannot be added because the Smart Access Gateway has been attached to the CEN and address conflict occurs.

**3. Routes in CEN**

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/60922/155919517530843_en-US.png)

In this topic, the leased line advertises the CIDR block 10.1.1.0/24 to CEN through BGP and the CIDR block 10.1.1.0/24 is also configured in Smart Access Gateway. Because both the VBR and the CCN are attached to the CEN, the CIDR block 10.1.1.0/24 is also synchronized to the CEN. For a leased line and a Smart Access Gateway destined to the same CIDR block, CEN adopts the following priority: the leased line takes precedence over Smart Access Gateway. Therefore, the next hop of routes destined for 10.1.1.0/24 in other networks attached to the CEN is the VBR. When the leased line fails, the standby line takes effect and traffic from Alibaba Cloud to IDC will be distributed to the Smart Access Gateway.

