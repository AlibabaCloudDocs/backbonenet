# Connect an on-premises data center to Alibaba Cloud through a VPN Gateway {#concept_h3t_bnn_l2b .concept}

This topic describes how to use VPN Gateway and Cloud Enterprise Network \(CEN\) to connect an on-premises data center to Alibaba Cloud and enable the on-premises data center to communicate with VPCs in different regions.

## Overview {#section_mch_fwn_l2b .section}

To connect an on-premises data center to Alibaba Cloud, follow these steps:

1.  Configure a VPN Gateway

    Create an IPsec-VPN connection to connect the on-premises data center to Alibaba Cloud. For more information, see [Establish a connection between a VPC and an on-premises data center](../../../../reseller.en-US/IPsec-VPN Quick Start/Establish a connection between a VPC and an on-premises data center.md#).

2.  Attach networks

    Attach the VBRs and VPCs to a created CEN instance.

3.  Configure and publish routes

    You can publish the route entry pointing to the VPN Gateway in the VPC to CEN, so that other networks attached to the CEN instance can learn the route.


## Network topology {#section_nhs_nnn_l2b .section}

The network architecture used in this topic is as follows:

-   The on-premises data center is connected to Alibaba Cloud through the VPN Gateway.
-   Three VPCs are created in the China \(Hangzhou\), China \(Beijing\), China \(Shanghai\), and Hong Kong regions.
-   The CIDR blocks of networks in this topic are as follows. Make sure that the CIDR blocks do not conflict with each other.

    |Network|CIDR block|
    |:------|:---------|
    |On-premises data center|10.1.1.0/24|
    |Beijing VPC|192.168.1.0/24|
    |Hong Kong VPC|192.168.2.0/24|
    |Shanghai VPC|192.168.3.0/24|
    |Hangzhou VPC|192.168.4.0/24|


![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15674950278697_en-US.png)

## On-premises data center route configuration {#section_kvd_hqn_l2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15674950278698_en-US.png)

An IPsec-VPN connection is established between the on-premises data center and the VPN Gateway, and custom or contributing route entries pointing to Alibaba Cloud are configured.

|Destination CIDR block|Next hop|
|:---------------------|:-------|
|192.168.1.0/24|VPN Gateway|
|192.168.2.0/24|VPN Gateway|
|192.168.3.0/24|VPN Gateway|
|192.168.4.0/24|VPN Gateway|

|Destination CIDR block|Next hop|
|:---------------------|:-------|
|0.0.0.0/0|VPN Gateway|

## VPC route configuration {#section_gxw_wlc_r2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15674950278708_en-US.png)

To enable the communication between the on-premises data center and the VPCs, you need to configure a route entry pointing to the on-premises data center \(VPN Gateway\) in the VPC connected to the VPN Gateway and publish the route to CEN.

A route entry pointing to Alibaba Cloud is created in the on-premises data center, so traffic from the on-premises data center can be forwarded to Alibaba Cloud. To forward traffic from the Hangzhou VPC to the on-premises data center, configure a route entry pointing to the VPN Gateway in the Hangzhou VPC.

As shown in the following figure, you need to configure a custom route entry pointing to the VPN Gateway \(on-premises data center\) in the Hangzhou VPC:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15674950288709_en-US.png)

You can see the route entry pointing to the VPN Gateway in the route table of the Hangzhou VPC:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15674950288710_en-US.png)

## Publish the route entry to CEN {#section_u2m_dkd_r2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15674950288711_en-US.png)

To mark other VPCs attached to the CEN instance learn the route pointing to the on-premises data center, you need to publish the route entry pointing to the VPN Gateway to the CEN instance so that other attached VPCs can learn the route.

The following figure shows the route table before the route entry is published.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15674950288712_en-US.png)

The following figure shows the route table after the route entry is published.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15674950288713_en-US.png)

The following figure shows the route table of other VPCs attached to the CEN instance.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17034/15674950288714_en-US.png)

After the previous operations, other VPCs attached to the CEN instance have learned the route entry pointing to the on-premises data center. Therefore, the on-premises data center can communicate with any VPC attached to the CEN instance.

## CEN route publishing {#section_lbw_mld_r2b .section}

The preceding solution describes one of the scenarios where a network attached to a CEN instance publishes a route entry to or withdraw a route entry from the instance. For VPCs/VBRs attached to a CEN instance, the following operations are supported:

|Route type|Network|Publish to CEN by default?|
|:---------|:------|:-------------------------|
|A route entry pointing to an ECS instance|VPC|No|
|A route entry pointing to a VPN Gateway|VPC|No|
|A route entry pointing to a High-Availablity Virtual IP Address \(HaVip\)|VPC|No|
|A VPC system route entry|VPC|Yes|
|A route entry pointing to an on-premises data center|VBR|Yes|
|A BGP route entry|VBR|Yes|

All these route entries published to CEN can be withdrawn. After a route entry is withdrawn, the route entry no longer exists in CEN.

If a custom route entry is published to a CEN instance and then is deleted from the VPC to which it belongs, the route entry is also deleted from the CEN instance.

**Note:** Currently, the console only supports publishing and withdrawing VPC route entries and does not support publishing and withdrawing VBR route entries. You can publish and withdraw VBR route entries by calling the [PublishRouteEntries](../../../../reseller.en-US/API Reference/Manage routes/PublishRouteEntries.md#) API.

