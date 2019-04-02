# Build an enterprise-level hybrid cloud in multiple ways {#concept_lz4_pm2_ggb .concept}

As a basic network platform, CEN can be used together with multiple services \(such as Express Connect, VPN Gateway, and Smart Access Gateway\) to provide rich hybrid cloud solutions.

## Overview {#section_tn3_gn2_ggb .section}

CEN is devoted to providing a high-quality network transmission environment. By simplifying your networking process, it helps you rapidly build a hybrid cloud network with enterprise-level scale and communication capability. This solution describes how to rapidly build a hybrid cloud network by using CEN together with physical connections of Express Connect, VPN Gateway, and Smart Access Gateway.

## Network topology {#section_qmv_gr2_ggb .section}

This tutorial takes the following network topology as an example:

-   [The Beijing IDC and the Shanghai IDC access Alibaba Cloud through physical connections](#leaseline)
-   [The Hangzhou IDC accesses Alibaba Cloud through VPN Gateway](#vpn)
-   [The Guangzhou IDC accesses Alibaba Cloud through Smart Access Gateway](#guangzhouIDC)

-   A company has deployed local data centers in Beijing, Shanghai, Hangzhou, and Guangzhou.
-   The company has also deployed services on the cloud. It has created separate VPCs in Beijing, Shanghai, Hangzhou, and Shenzhen.
-   The Beijing IDC and the Shanghai IDC are connected to access points of Alibaba Cloud through physical connections and their corresponding VBRs are attached to the CEN.
-   The Hangzhou IDC is connected to the Hangzhou VPC through VPN Gateway.
-   The Guangzhou IDC accesses Alibaba Cloud through Smart Access Gateway and the CCN to which the Smart Access Gateway belongs is attached to the CEN.
-   The VPCs in Beijing, Shanghai, Shenzhen, and Hangzhou are attached to the CEN.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/155417194335239_en-US.png)


## IP address planning {#section_ksl_tgf_ggb .section}

When you build a hybrid cloud, you must ensure that all CIDR blocks do not conflict with one another. The CIDR blocks in this tutorial are as follows:

|Network|CIDR block|
|-------|----------|
|Hangzhou IDC|10.1.1.0/24|
|Guangzhou IDC|10.1.2.0/24|
|Beijing IDC|10.1.3.0/24|
|Shanghai IDC|10.1.4.0/24|
|Beijing VPC|192.168.1.0/24|
|Shenzhen VPC|192.168.2.0/24|
|Shanghai VPC|192.168.3.0/24|
|Hangzhou VPC|192.168.4.0/24|

## Access mode {#section_orz_1hf_ggb .section}

In this tutorial, IDCs access Alibaba Cloud through the following ways:

**The Beijing IDC and the Shanghai IDC access Alibaba Cloud through physical connections**

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/155417194335240_en-US.png)

Configuration description:

1.  The Beijing IDC and the Shanghai IDC are connected to VBRs through physical connections, and each IDC and the corresponding VBR are each other's BGP peer. For more information, see[Configure BGP](../../../../../intl.en-US/User Guide (New Console)/Virtual border router/Configure BGP.md#).
2.  The CPEs of the Beijing IDC and the Shanghai IDC advertise the CIDR blocks of the IDCs to the CEN through BGP. The main configurations of the CPEs are as follows:

    |Configuration|Beijing CPE|Shanghai CPE|
    |-------------|-----------|------------|
    |Local BGP ASN|A|B|
    |Peer BGP ASN|45104|45104|
    |Network|10.1.3.0/24|10.1.4.0/24|

    After each IDC and the corresponding VBR become each other's peer, the IDC and the VBR can learn each other's routes.


**The Hangzhou IDC accesses Alibaba Cloud through VPN Gateway**

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/155417194335241_en-US.png)

Configuration description:

1.  The Hangzhou IDC accesses the Hangzhou VPC through VPN Gateway. For more information, see[Configure a site-to-site connection](../../../../../intl.en-US/IPsec-VPN Quick Start/Configure a site-to-site connection.md#).
2.  An IPsec-VPN connection has been established between the IDC and the VPN Gateway, and contributing routes or default routes pointing to the cloud have been configured.

    Contributing routes:

    |Destination CIDR block|Next hop|
    |----------------------|--------|
    |10.1.2.0/24|VPN Gateway|
    |10.1.3.0/24|VPN Gateway|
    |10.1.4.0/24|VPN Gateway|
    |192.168.1.0/24|VPN Gateway|
    |192.168.2.0/24|VPN Gateway|
    |192.168.3.0/24|VPN Gateway|
    |192.168.4.0/24|VPN Gateway|

    Default route:

    |Destination CIDR block|Next hop|
    |----------------------|--------|
    |0.0.0.0/0|VPN Gateway|

3.  To enable the communication between the IDC and networks attached to the CEN, you must configure a route entry pointing to the IDC \(VPN Gateway\) in the VPC connected to the VPN Gateway and publish the route to the CEN.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/155417194335242_en-US.png)

    To configure the route, follow these steps:

    1.  Configure a route of which the destination CIDR block is 10.1.1.0/24 and the next hop is the VPN Gateway in the route table of the VPC.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/155417194335243_en-US.png)

    2.  Publish the route to the CEN in the Hangzhou VPC.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/155417194335244_en-US.png)

        Through the preceding steps, all networks in the CEN can learn the route pointing to the IDC and the IDC can communicate any network in the CEN. For more information, see [Connect a local data center to Alibaba Cloud through a VPN Gateway](intl.en-US/Best Practices/Connect a local data center to Alibaba Cloud through a VPN Gateway.md#).


**The Guangzhou IDC accesses Alibaba Cloud through Smart Access Gateway**

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/155417194335245_en-US.png)

Configuration description:

1.  On the Smart Access Gateway console, configure the CIDR block of the Guangzhou IDC connected to Smart Access Gateway as a private CIDR block.
2.  Attach the CCN bound to the Smart Access Gateway to the CEN. Then the Guangzhou IDC can communicate with any network in the CEN.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/155417194335311_en-US.png)


## Interconnection { .section}

Through the preceding ways:

-   The Beijing IDC and Shanghai IDC access Alibaba Cloud through physical connections and use BGP protocol, and the VBRs of the physical connections are attached to the CEN.
-   The Hangzhou IDC accesses Alibaba Cloud through VPN Gateway and the VPC connected to the VPN Gateway is attached to the CEN.
-   The Guangzhou IDC accesses Alibaba Cloud through Smart Access Gateway and the CCN associated with the Smart Access Gateway is attached to the CEN.

CEN ignores conflict routes and dynamically forwards routes of attached networks to build a fully connected hybrid cloud.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/155417194335246_en-US.png)

Take Beijing CPE, Beijing VBR, and Shenzhen VPC as examples and view their route tables.

|Destination CIDR block|Next hop|Route type|
|----------------------|--------|----------|
|10.1.1.0/24|BGP peer \(Beijing VBR\)|BGP route|
|10.1.2.0/24|BGP peer \(Beijing VBR\)|BGP route|
|10.1.4.0/24|BGP peer \(Beijing VBR\)|BGP route|
|192.168.1.0/24|BGP peer \(Beijing VBR\)|BGP route|
|192.168.2.0/24|BGP peer \(Beijing VBR\)|BGP route|
|192.168.3.0/24|BGP peer \(Beijing VBR\)|BGP route|
|192.168.4.0/24|BGP peer \(Beijing VBR\)|BGP route|

|Destination CIDR Block|Next hop|Route type|
|----------------------|--------|----------|
|10.1.3.0/24|BGP peer \(Beijing CPE\)|BGP route|
|10.1.1.0/24|Hangzhou VPC|CEN route|
|10.1.2.0/24|CCN|CEN route|
|10.1.4.0/24|Shanghai VPC|CEN route|
|192.168.1.0/24|Beijing VPC|CEN route|
|192.168.2.0/24|Shenzhen VPC|CEN route|
|192.168.3.0/24|Shanghai VPC|CEN route|
|192.168.4.0/24|Hangzhou VPC|CEN route|

|Destination CIDR block|Next hop|Route type|
|----------------------|--------|----------|
|10.1.1.0/24|Hangzhou VPC|CEN route|
|3.1.2.0/24|CCN|CEN route|
|10.1.3.0/24|Beijing VBR|CEN route|
|10.1.4.0/24|Shanghai VBR|CEN route|
|192.168.1.0/24|Beijing VPC|CEN route|
|192.168.3.0/24|Shanghai VPC|CEN route|
|192.168.4.0/24|Hangzhou VPC|CEN route|

