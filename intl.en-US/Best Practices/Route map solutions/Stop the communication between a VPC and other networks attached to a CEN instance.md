# Stop the communication between a VPC and other networks attached to a CEN instance {#task_1529130 .task}

This topic describes how to use route maps to stop the communication between a VPC and other networks \(VPCs, VBRs, or CCNs\) that are attached to the same Cloud Enterprise Network \(CEN\) instance.

A CEN instance is created and the required networks are attached to the CEN instance. For more information, see [Create a CEN instance](../../../../reseller.en-US/User Guide/Manage CEN instances/Create a CEN instance.md#) and [Attach networks](../../../../reseller.en-US/User Guide/Manage networks/Attach networks.md#).

VPCs can communicate with VPCs, Virtual Border Routers \(VBRs\), and Cloud Connect Networks \(CCNs\) that are attached to the same CEN instance by default. However, you may need to block the communication between two VPCs, or between a VPC and a VBR or CCN. In this topic, two VPCs are used as an example to show you how to stop the communication between two VPCs by using route maps.

![Stop the communication between two VPCs](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087054271_en-US.png)

As shown in the preceding figure, VPC1, VPC2, and VPC3 are attached to CEN. By default, VPC1, VPC2, and VPC3 are all connected and can communicate with each other. By using route maps, you can block the communication between VPC1 and VPC2 while VPC1 and VPC2 can still communicate with VPC3.

## Step 1: Set a route map to deny access from VPC1 to VPC2 {#section_kys_s9k_8gl .section}

To set a route map to deny access from VPC1 to VPC2, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  In the left-side navigation pane, click **Instances**.
3.  On the Instances page, find the target CEN instance and click **Manage** in the **Actions** column.
4.  On the CEN page, click the **Route Maps** tab and then click **Add Route Map**.
5.  In the Add Route Map dialog box, configure the route map according to the following information and then click **OK**. 

    -   **Priority**: Enter the priority of the route map. A smaller number represents a higher priority. In this example, enter **20**.
    -   **Region**: Select the region to which the route map is applied. In this example, select **China \(Hangzhou\)**.
    -   **Transmit Direction**: Select the direction of the route map. In this example, select **Export from Regional Gateway**.
    -   **Match Condition**: Set the matching conditions of the route map. In this example, add a matching condition and set the source instance ID to the ID of VPC2 and the target instance ID to the ID of VPC1.
    -   **Match Mode**: Select the matching mode of the route map. In this example, select **Deny**.
    ![Set a route map to deny access from VPC1 to VPC2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087055409_en-US.png)

    After you add the route map, you can view the route that denies access from VPC1 to VPC2 on the **Routes** tab.

    ![View route information](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087055414_en-US.png)


## Step 2: Set a route map to deny access from VPC2 to VPC1 {#section_mwh_cke_twx .section}

To set a route map to deny access from VPC2 to VPC1, follow these steps:

1.  In the left-side navigation pane, click **Instances**.
2.  On the Instances page, find the target CEN instance and click **Manage** in the **Actions** column.
3.  On the CEN page, click the **Route Maps** tab and then click **Add Route Map**.
4.  In the Add Route Map dialog box, configure the route map according to the following information and then click **OK**. 

    -   **Priority**: Enter the priority of the route map. A smaller number represents a higher priority. In this example, enter **50**.
    -   **Region**: Select the region to which the route map is applied. In this example, select **China \(Hangzhou\)**.
    -   **Transmit Direction**: Select the direction of the route map. In this example, select **Export from Regional Gateway**.
    -   **Match Condition**: Set the matching conditions of the route map. In this example, add a matching condition and set the source instance ID to the ID of VPC1 and the target instance ID to the ID of VPC2.
    -   **Match Mode**: Select the matching mode of the route map. In this example, select **Deny**.
    ![Set a route map to deny access from VPC2 to VPC1](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087155415_en-US.png)

    After you add the route map, you can view the route that denies access from VPC2 to VPC1 on the **Routes** tab.

    ![View route information](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087155416_en-US.png)


## Step 3: Test the network connectivity {#section_c10_p33_2k8 .section}

To test the network connectivity between VPC1 and VPC2, follow these steps:

1.  Log on to the ECS instance ECS1 in VPC1.
2.  Use the ping command to ping the IP address of the ECS instance ECS2 in VPC2. The output shows that ECS1 cannot access ECS2, which means VPC1 cannot access VPC2.

    ![ECS1 to ECS2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087154751_en-US.png)

3.  Log on to ECS2 in VPC2.
4.  Use the ping command to ping the IP address of ECS1 in VPC1. The output shows that ECS2 cannot access ECS1, which means VPC2 cannot access VPC1.

    ![ECS2 to ECS1](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087154752_en-US.png)


To test the network connectivity between VPC1 and VPC3, follow these steps:

1.  Log on to ECS1 in VPC1.
2.  Use the ping command to ping the IP address of ECS3 in VPC3. The output shows that ECS1 can access ECS3, which means VPC1 can access VPC3.

    ![ECS1 to ECS3](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087154778_en-US.png)

3.  Log on to ECS3 in VPC3.
4.  Use the ping command to ping the IP address of ECS1 in VPC1. The output shows that ECS3 can access ECS1, which means VPC3 can access VPC1.

    ![ECS3 can access ECS1 normally](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087154781_en-US.png)


To test the network connectivity between VPC2 and VPC3, follow these steps:

1.  Log on to ECS2 in VPC2.
2.  Use the ping command to ping the IP address of ECS3 in VPC3. The output shows that ECS2 can access ECS3, which means VPC2 can access VPC3.

    ![ECS2 to ECS3](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087154778_en-US.png)

3.  Log on to ECS3 in VPC3.
4.  Use the ping command to ping the IP address of ECS2 in VPC2. The output shows that ECS3 can access ECS2, which means VPC3 can access VPC2.

    ![ECS3 can access ECS2 normally](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776087154768_en-US.png)


