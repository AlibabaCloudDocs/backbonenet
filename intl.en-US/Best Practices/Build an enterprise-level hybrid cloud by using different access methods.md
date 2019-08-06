# Build an enterprise-level hybrid cloud by using different access methods {#concept_lz4_pm2_ggb .concept}

Cloud Enterprise Network \(CEN\) provides a high-quality network transmission environment. By simplifying the networking process, CEN helps you rapidly build a hybrid cloud network with enterprise-level scale and communication capability. This topic describes how to rapidly build a hybrid cloud network by using CEN together with Express Connect physical connections, VPN Gateway, and Smart Access Gateway.

## Network topology {#section_qmv_gr2_ggb .section}

This topic takes the following network topology as an example:

-   A company has deployed on-premises data centers in Beijing, Shanghai, Hangzhou, and Guangzhou.
-   The company has also deployed services on the cloud. It has created separate VPCs in the China \(Beijing\), China \(Shanghai\), China \(Hangzhou\), and China \(Shenzhen\) regions.
-   Beijing and Shanghai on-premises data centers are connected to access points of Alibaba Cloud through physical connections and their corresponding Virtual Border Routers \(VBRs\) are attached to a CEN instance.
-   Hangzhou data center is connected to the Hangzhou VPC through VPN Gateway.
-   Guangzhou on-premises data center accesses Alibaba Cloud through Smart Access Gateway. The Cloud Connect Network \(CCN\) to which the Smart Access Gateway belongs is attached to the CEN instance.
-   The VPCs in the China \(Beijing\), China \(Shanghai\), China \(Shenzhen\), and China \(Hangzhou\) regions are attached to the CEN instance.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/156508652135239_en-US.png)


## IP address planning {#section_ksl_tgf_ggb .section}

When you build a hybrid cloud, you must ensure that no CIDR blocks conflict with each other. The CIDR blocks used in this example are as follows:

|Network|CIDR block|
|-------|----------|
|Hangzhou data center|10.1.1.0/24|
|Guangzhou data center|10.1.2.0/24|
|Beijing data center|10.1.3.0/24|
|Shanghai data center|10.1.4.0/24|
|Beijing VPC|192.168.1.0/24|
|Shenzhen VPC|192.168.2.0/24|
|Shanghai VPC|192.168.3.0/24|
|Hangzhou VPC|192.168.4.0/24|

## Access methods {#section_orz_1hf_ggb .section}

In this topic, on-premises data centers are connected to Alibaba Cloud in the following ways:

-   [Beijing and Shanghai data centers access Alibaba Cloud through physical connections.](#leaseline)
-   [Hangzhou data center accesses Alibaba Cloud through VPN Gateway.](#vpn)
-   [Guangzhou data center accesses Alibaba Cloud through Smart Access Gateway.](#guangzhouIDC)

**Beijing and Shanghai data centers access Alibaba Cloud through physical connections**

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/156508652135240_en-US.png)

Configuration description:

1.  Beijing and Shanghai data centers are connected to VBRs through physical connections, and each data center and the corresponding VBR are each other's BGP peer. For more information, see [Configure BGP](../../../../reseller.en-US/Virtual Border Router/Configure BGP.md#).
2.  The CPEs of Beijing and Shanghai data centers advertise the CIDR blocks of the data centers to CEN through BGP. The main configurations of the CPEs are as follows:

    |Configuration|Beijing CPE|Shanghai CPE|
    |-------------|-----------|------------|
    |Local BGP ASN|A|B|
    |Peer BGP ASN|45104|45104|
    |Network|10.1.3.0/24|10.1.4.0/24|

    After each data center and the corresponding VBR become each other's BGP peer, the data center and the VBR can learn each other's routes.


**Hangzhou data center accesses Alibaba Cloud through VPN Gateway**

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/156508652135241_en-US.png)

Configuration description:

1.  Hangzhou data center accesses the Hangzhou VPC through VPN Gateway. For more information, see [Establish a connection between a VPC and an on-premises data center](../../../../reseller.en-US/IPsec-VPN Quick Start/Establish a connection between a VPC and an on-premises data center.md#).
2.  An IPsec-VPN connection is established between the on-premises data center and the VPN Gateway, and contributing routes or default routes pointing to Alibaba Cloud are configured.

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

3.  To enable the communication between the on-premises data center and the networks attached to CEN, you must configure a route entry pointing to the data center \(VPN Gateway\) in the VPC connected to the VPN Gateway and publish the route to CEN.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/156508652135242_en-US.png)

    To configure the route, follow these steps:

    1.  Configure a route of which the destination CIDR block is 10.1.1.0/24 and the next hop is VPN Gateway in the route table of the VPC.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/156508652235243_en-US.png)

    2.  Publish the route to CEN from the VPC.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/156508652235244_en-US.png)

        Through the preceding steps, all networks in the CEN instance can learn the route pointing to the data center and the data center can communicate with any network in the CEN instance. For more information, see [Connect a local data center to Alibaba Cloud through a VPN Gateway](reseller.en-US/Best Practices/Connect a local data center to Alibaba Cloud through a VPN Gateway.md#).


**Guangzhou data center accesses Alibaba Cloud through Smart Access Gateway**

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/156508652235245_en-US.png)

Configuration description:

1.  In the Smart Access Gateway console, configure the CIDR block of Guangzhou data center connected to Smart Access Gateway as a private CIDR block.
2.  Attach the CCN associated with the Smart Access Gateway to the CEN instance. Then Guangzhou data center can communicate with any network in the CEN instance.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/156508652235311_en-US.png)


## Interconnection of on-premises data centers and networks { .section}

Through the preceding ways:

-   Beijing and Shanghai data centers access Alibaba Cloud through physical connections and the BGP protocol. The VBRs of the physical connections are attached to the CEN instance.
-   Hangzhou data center accesses Alibaba Cloud through VPN Gateway. The VPC connected to the VPN Gateway is attached to the CEN instance.
-   Guangzhou data center accesses Alibaba Cloud through Smart Access Gateway. The CCN associated with the Smart Access Gateway is attached to the CEN instance.

CEN ignores conflict routes and dynamically forwards routes of attached networks to build a fully connected hybrid cloud.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83131/156508652235246_en-US.png)

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

|Destination CIDR block|Next hop|Route type|
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
|10.1.2.0/24|CCN|CEN route|
|10.1.3.0/24|Beijing VBR|CEN route|
|10.1.4.0/24|Shanghai VBR|CEN route|
|192.168.1.0/24|Beijing VPC|CEN route|
|192.168.3.0/24|Shanghai VPC|CEN route|
|192.168.4.0/24|Hangzhou VPC|CEN route|

