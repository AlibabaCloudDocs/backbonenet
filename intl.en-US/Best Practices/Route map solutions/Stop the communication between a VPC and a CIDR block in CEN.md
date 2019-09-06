# Stop the communication between a VPC and a CIDR block in CEN {#task_1529129 .task}

The topic describes how to use route maps to stop the communication between a VPC and a CIDR block in Cloud Enterprise Network \(CEN\).

Before you add a route map, make sure that the following conditions are met:

-   The on-premises data center is connected to Alibaba cloud through a leased line. For more information, see [../../../../dita-oss-bucket/SP\_72/DNexpressconnect1847151/EN-US\_TP\_13831.md\#](../../../../reseller.en-US/Getting Started (New Console)/Connect an on-premises data center to a VPC through a physical connection.md#) and [Create a VBR](../../../../reseller.en-US/Virtual Border Router/Create a VBR.md#).
-   A CEN instance is created and the required networks are attached to the CEN instance. For more information, see [Create a CEN instance](../../../../reseller.en-US/User Guide/Manage CEN instances/Create a CEN instance.md#) and [Attach networks](../../../../reseller.en-US/User Guide/Manage networks/Attach networks.md#).

VPCs can communicate with the CIDR blocks of VPCs, Virtual Border Routers \(VBRs\), and Cloud Connect Networks \(CCNs\) that are attached to the same CEN instance by default. However, you may need to stop a VPC from communicating with a certain CIDR block of a VPC, VBR or CCN.

![Stop the communication between CIDR blocks](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214244/156776106154819_en-US.png)

As shown in the preceding figure, a VPC and a VBR are attached to CEN. The VBR learns the routes pointing to CIDR block 1 and CIDR block 2 of the on-premises data center through BGP. By default, the VPC can communicate with CIDR block 1 and CIDR block 2 of the on-premises data center, too. If you want to stop the VPC from communicating with CIDR block 1, you can use route maps. By using route maps, you can stop the VPC from communicating with CIDR block 1 while the VPC can still communicate with CIDR block 2.

## Step 1: Set a route map to deny the route of CIDR block 1 {#section_5dc_me0_wra .section}

To set a route map to deny the route of CIDR block 1, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  In the left-side navigation pane, click **Instances**.
3.  On the Instances page, find the target CEN instance and click **Manage** in the **Actions** column.
4.  On the CEN page, click the **Route Maps** tab and then click **Add Route Map**.
5.  On the Add Route Map page, configure the route map according to the following information and then click **OK**. 

    -   **Priority**: Enter the priority of the route map. A smaller number represents a higher priority. In this example, enter **20**.
    -   **Region**: Select the region to which the route map is applied. In this example, select **China \(Hangzhou\)**.
    -   **Transmit Direction**: Select the direction of the route map. In this example, select **Import to Regional Gateway**.
    -   **Match Condition**: Set the matching conditions of the route map. In this example, add two matching conditions:
        -   **Source Instance ID**: Enter the instance ID of the VBR.
        -   **Route Prefix**: Enter 192.168.0.0/24. Select **Exact Match** for **Condition Type**.
    -   **Match Mode**: Select the matching mode of the route map. In this example, select **Deny**.
    ![Configure a route map that blocks the communication between CIDR blocks](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214244/156776106155460_en-US.png)

    After you add the route map, you can see that the route pointing to CIDR block 1, 192.168.0.0/24, is deleted from the VPC on the **Routes** tab.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214244/156776106155467_en-US.png)


## Step 2: Test the network connectivity {#section_47v_ak9_wao .section}

To test the network connectivity between the VPC and CIDR block 1 of the on-premises data center, follow these steps:

1.  Log on to an ECS instance in the VPC.
2.  Use the ping command to ping the IP address of CIDR block 1. The output shows that the ECS instance in the VPC cannot access the IP address of CIDR block 1.

    ![ECS1 to ECS2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776106154751_en-US.png)


To test the network connectivity between the VPC and CIDR block 2 of the on-premises data center, follow these steps:

1.  Log on to the ECS instance in the VPC.
2.  Use the ping command to ping the IP address of CIDR block 2. The output shows that the ECS instance in the VPC can access the IP address of CIDR block 2.

    ![ECS to CIDR block 2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776106154778_en-US.png)


