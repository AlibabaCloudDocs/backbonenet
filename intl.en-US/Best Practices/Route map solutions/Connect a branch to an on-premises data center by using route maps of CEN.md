# Connect a branch to an on-premises data center by using route maps of CEN {#task_1614571 .task}

This topic describes how to use the route maps of Cloud Enterprise Network \(CEN\) to connect a branch of a company and an on-premises data center.

Before you configure a route map, make sure that the following conditions are met:

-   A Cloud Connect Network \(CCN\) is created and the Smart Access Gateway \(SAG\) instances connected to the branches are attached to the CCN. For more information, see [Create a CCN instance](../../../../reseller.en-US/Cloud Connect Network/Create a CCN instance.md#) and [Associate an SAG instance with a network instance](../../../../reseller.en-US/Smart Access Gateway/Configuration Guide/Network configurations/Associate an SAG instance with a network instance.md#).
-   A CEN instance is created and the networks that need to communicate with each other are attached to the CEN instance. For more information, see [Create a CEN instance](../../../../reseller.en-US/User Guide/Manage CEN instances/Create a CEN instance.md#) and [Attach networks](../../../../reseller.en-US/User Guide/Manage networks/Attach networks.md#).
-   A bandwidth package is purchased and cross-region connection bandwidth is set. For more information, see [Purchase a bandwidth package](../../../../reseller.en-US/User Guide/Bandwidth package management/Purchase a bandwidth package.md#) and [Configure a cross-region connection bandwidth](../../../../reseller.en-US/User Guide/Manage cross-region connection bandwidth/Configure a cross-region connection bandwidth.md#).

By default, CEN adds a route map with the priority of 5000 and the matching mode of DENY to the regional gateway. This route map stops Virtual Border Routers \(VBRs\) and CCNs from communicating with other VBRs and CCNs attached to the CEN instance. However, you may need to connect two VBRs or two CCNs attached to the CEN instance.

**Note:** Deletion of default route maps may cause a routing loop. Therefore, we recommend that you exercise caution when you delete default route maps.

![Connect enterprise branches and on-premises data centers through CEN](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280289/156776124554946_en-US.png)

As shown in the preceding figure, the on-premises data center is located in Beijing and connected to Alibaba Cloud through a VBR. Branch 1 is located in Shanghai. Branch 2 is located in Hangzhou. The corresponding SAG instances SAG1 and SAG2 are attached to a CCN. The CCN and the VBR are attached to a CEN instance. By default, the on-premises data center cannot communicate with branch 1 or branch 2. If you want the on-premises data center to communicate with branch 1, you can use route maps.

## Step 1: Set a route map that allows the on-premises data center to access branch 1 {#section_7vg_ncc_ah9 .section}

To set a route map that allows the on-premises data center to access branch 1, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  In the left-side navigation pane, click **Instances**.
3.  On the Instances page, find the target CEN instance and click **Manage** in the **Actions** column.
4.  On the CEN page, click **Route Maps** and then click **Add Route Map**.
5.  In the Add Route Map dialog box, configure the route map according to the following information and then click **OK**. 

    -   **Priority**: Enter the priority of the route map. A smaller number represents a higher priority. In this example, enter **20**.
    -   **Region**: Select the region to which the route map is applied. In this example, select **China \(Beijing\)**.
    -   **Transmit Direction**: Select the direction of the route map. In this example, select **Export from Regional Gateway**.
    -   **Match Condition**: Set the matching conditions of the route map. In this example, add two matching conditions:
        -   **Source Instance ID**: Enter the instance ID of SAG1.
        -   **Target Instance ID**: Enter the instance ID of the VBR.
        -   **Route Prefix**: Enter 172.16.0.0/24.
    -   **Match Mode**: Select the matching mode of the route map. In this example, select **Permit**.
    ![Set a route map that allows the on-premises data cente to access branch 1](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280289/156776124655582_en-US.png)

    After you add the route map, you can view the route that allows the on-premises data center to access branch 1 on the **Routes** tab.

    ![Set a route map that allows the on-premises data cente to access branch 1](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280289/156776124655587_en-US.png)


## Step 2: Set a route map that allows the CCN to access the on-premises data center {#section_533_lnn_kcx .section}

To set a route map that allows the CCN to access the on-premises data center, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  In the left-side navigation pane, click **Instances**.
3.  On the Instances page, find the target CEN instance and click **Manage** in the **Actions** column.
4.  On the CEN page, click **Route Maps** and then click **Add Route Map**.
5.  In the Add Route Map dialog box, configure the route map according to the following information and then click **OK**. 

    -   **Priority**: Enter the priority of the route map. A smaller number represents a higher priority. In this example, enter **20**.
    -   **Region**: Select the region to which the route map is applied. In this example, select **China \(Shanghai\)**.
    -   **Transmit Direction**: Select the direction of the route map. In this example, select **Export from Regional Gateway**.
    -   **Match Condition**: Set the matching conditions of the route map. In this example, add two matching conditions:
        -   **Source Instance ID**: Enter the instance ID of the VBR.
        -   **Target Instance ID**: Enter the instance ID of the CCN.
        -   **Route Prefix**: Enter 192.168.0.0/24.
    -   **Match Mode**: Select the matching mode of the route map. In this example, select **Permit**.
    ![Set a route map that allows the CCN to access the on-premises data center](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280289/156776124655583_en-US.png)

    After you add the route map, you can view the route that allows the CCN to access the on-premises data center on the **Routes** tab.

    ![View the route map that allows the CCN to access the on-premises data center](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280289/156776124655588_en-US.png)


## Step 3: Test the network connectivity {#section_6dn_byq_hhk .section}

To test the network connectivity between the on-premises data center and branch 1, follow these steps:

1.  Open the command prompt of the PC at the on-premises data center.
2.  Use the ping command to ping the IP address of branch 1. The output shows that the PC of the on-premises data center can access branch 1.

    ![The on-premises data center can access branch 1.](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776124654781_en-US.png)

3.  Open the command prompt of the PC at branch 1.
4.  Use the ping command to ping the IP address of the PC at the on-premises data center. The output shows that branch 1 can access the on-premises data center.

    ![Branch 1 can access the on-premises data center.](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776124654768_en-US.png)


To test the network connectivity between the on-premises data center and branch 2, follow these steps:

1.  Open the command prompt of the PC at the on-premises data center.
2.  Use the ping command to ping the IP address of branch 2. The output shows that the PC of the on-premises data center cannot access branch 2.

    ![The on-premises data center cannot access branch 2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280289/156776124754957_en-US.png)


