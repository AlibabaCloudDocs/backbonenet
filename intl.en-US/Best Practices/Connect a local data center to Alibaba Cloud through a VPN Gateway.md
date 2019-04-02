# Connect a local data center to Alibaba Cloud through a VPN Gateway {#concept_h3t_bnn_l2b .concept}

This tutorial introduces how to use VPN Gateway and CEN to connect an IDC to Alibaba Cloud and enable the IDC to communicate with VPCs in different regions.

## Solution overview {#section_mch_fwn_l2b .section}

To connect an IDC to Alibaba Cloud, complete these steps:

1.  Configure a VPN Gateway

    Create an IPsec-VPN connection to connect the local IDC to the Alibaba Cloud. For more information, see [Configure a site-to-site connection](../../../../../intl.en-US/IPsec-VPN Quick Start/Configure a site-to-site connection.md#).

2.  Attach networks

    Attach the VBR and VPCs to communicate with one another to the created CEN instance.

3.  Configure and publish routes

    You can publish the route entry pointing to the VPN Gateway in the VPC to the CEN, so that other networks attached to the CEN instance can learn the route.


## Network topology {#section_nhs_nnn_l2b .section}

The network topology used in this tutorial is as follows:

-   The local IDC is connected to Alibaba Cloud through the VPN Gateway.
-   Four VPCs are already created in the China \(Hangzhou\), China \(Beijing\), China \(Shanghai\), and China \(Hong Kong\) regions.
-   The CIDR blocks of networks in this tutorial are as follows. Make sure that the CIDR blocks do not conflict with one another.

    |Network|CIDR block|
    |:------|:---------|
    |Local data center|10.1.1.0/24|
    |Beijing VPC|192.168.1.0/24|
    |Shanghai VPC|192.168.2.0/24|
    |Hong Kong VPC|192.168.3.0/24|
    |Hangzhou VPC|192.168.4.0/24|


![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15541755838697_en-US.png)

## IDC route configuration {#section_kvd_hqn_l2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15541755838698_en-US.png)

An IPsec-VPN connection has been established between the IDC and the VPN Gateway, and custom or system route entries pointing to the Alibaba Cloud have been configured.

|Destination CIDR block|Next hop|
|:---------------------|:-------|
|192.168.1.0/24|VPN Gateway|
|192.168.1.0/24|VPN Gateway|
|192.168.3.0/24|VPN Gateway|
|192.168.3.0/24|VPN Gateway|

|Destination CIDR block|Next hop|
|:---------------------|:-------|
|0.5.0.0/0|VPN Gateway|

## VPC route configuration {#section_gxw_wlc_r2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15541755838708_en-US.png)

To enable the communication between the IDC and the VPCs, you need to configure a route entry pointing to the IDC \(VPN Gateway\) in the VPC connected to the VPN Gateway and publish the route to the CEN.

A route entry pointing to Alibaba Cloud is already created in the IDC, so traffic from the IDC can be forwarded to Alibaba Cloud. To forward traffic from the Hangzhou VPC to the IDC, configure a route entry pointing to the VPN Gateway in the Hangzhou VPC.

As shown in the following figure, you need to configure a custom route entry pointing to the VPN Gateway \(IDC\) in the Hangzhou VPC:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15541755838709_en-US.png)

You can see the route entry pointing to the VPN Gateway in the route table of the Hangzhou VPC:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15541755838710_en-US.png)

## Publish the route entry to CEN {#section_u2m_dkd_r2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15541755838711_en-US.png)

To mark other VPCs attached to the CEN instance learn the route pointing to the IDC, you need to publish the route entry pointing to the VPN Gateway to the CEN instance so that other attached VPCs can learn the route.

The following figure shows the route table before the route entry is published.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15541755838712_en-US.png)

The following figure shows the route table after the route entry is published.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15541755838713_en-US.png)

The following figure shows the route table of other VPCs attached to the CEN.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15541755848714_en-US.png)

After the previous operations, other VPCs attached to the CEN instance have learned the route entry pointing to the IDC. Therefore, the IDC can communicate with any VPC attached to the CEN instance.

## CEN route publishing {#section_lbw_mld_r2b .section}

This solution describes one of the scenarios where a network attached to a CEN instance publishes a route entry to or withdraw a route entry from the instance. For VPCs/VBRs attached to a CEN instance, the following operations are supported:

|Route type|Network|Publish to CEN by default|
|:---------|:------|:------------------------|
|A route entry pointing to an ECS instance|VPC|No|
|A route entry pointing to a VPN Gateway|VPC|No|
|A route entry pointing to a HaVip|VPC|No|
|A VPC system route entry|VPC|Yes|
|A route entry pointing to a local IDC|VBR|Yes|
|A BGP route entry|VBR|Yes|

All these route entries published to CEN can be withdrawn. After a route entry is withdrawn, the route entry no longer exists in CEN.

If a custom route entry is published to a CEN and then is deleted from the VPC to which it belongs, the route entry is also deleted from the CEN.

**Note:** Currently, the console only supports publishing and withdrawing VPC route entries and does not support publishing and withdrawing VBR route entries. You can publish and withdraw VBR route entries by calling the Open API [PublishRouteEntries](../../../../../intl.en-US/API Reference/Manage route entries/PublishRouteEntries.md#).

