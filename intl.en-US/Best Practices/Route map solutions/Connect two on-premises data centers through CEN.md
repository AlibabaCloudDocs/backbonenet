# Connect two on-premises data centers through CEN {#task_1614395 .task}

This topic describes how to connect two on-premises data centers by using route maps of Cloud Enterprise Network \(CEN\).

Before you configure a route map, make sure that the following conditions are met:

-   The on-premises data centers are connected to Alibaba Cloud through a leased line. For more information, see [../../../../dita-oss-bucket/SP\_72/DNexpressconnect1847151/EN-US\_TP\_13831.md\#](../../../../reseller.en-US/Getting Started (New Console)/Connect an on-premises data center to a VPC through a physical connection.md#) and [Create a VBR](../../../../reseller.en-US/Virtual Border Router/Create a VBR.md#).
-   A CEN instance is created and the required networks are attached to the CEN instance. For more information, see [Create a CEN instance](../../../../reseller.en-US/User Guide/Manage CEN instances/Create a CEN instance.md#) and [Attach networks](../../../../reseller.en-US/User Guide/Manage networks/Attach networks.md#).
-   A bandwidth package is purchased and cross-region connection bandwidth is set. For more information, see [Purchase a bandwidth package](../../../../reseller.en-US/User Guide/Bandwidth package management/Purchase a bandwidth package.md#) and [Configure a cross-region connection bandwidth](../../../../reseller.en-US/User Guide/Manage cross-region connection bandwidth/Configure a cross-region connection bandwidth.md#).

By default, CEN adds a route map with the priority of 5000 and the matching mode of DENY to the regional gateway. This route map stops Virtual Border Routers \(VBRs\) and Cloud Connect Networks \(CCNs\) from communicating with other VBRs and CCNs attached to the CEN instance. However, you may need to connect two VBRs or two CCNs attached to the CEN instance.

**Note:** Deletion of default route maps may cause a routing loop. Therefore, we recommend that you exercise caution when you delete default route maps.

![Connect two on-premises data centers through CEN](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280065/156776115254882_en-US.png)

As shown in the preceding figure, the on-premises data center IDC1 is located in Beijing and connected to Alibaba Cloud through VBR1. The on-premises data center IDC2 is located in Hangzhou and connected to Alibaba Cloud through VBR2. VBR1 and VBR2 are attached to a CEN instance. By default, IDC1 and IDC2 are not connected. If you want to connect IDC1 with IDC2, you can use route maps.

## Step 1: Set a route map that allows IDC1 to access IDC2 {#section_j2x_cll_5wy .section}

To set a route map that allows IDC1 to access IDC2, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  In the left-side navigation pane, click **Instances**.
3.  On the Instances page, find the target CEN instance and click **Manage** in the **Actions** column.
4.  On the CEN page, click the **Route Maps** tab and then click **Add Route Map**.
5.  In the Add Route Map dialog box, configure the route map according to the following information and then click **OK**. 

    -   **Priority**: Enter the priority of the route map. A smaller number represents a higher priority. In this example, enter **20**.
    -   **Region**: Select the region to which the route map is applied. In this example, select **China \(Beijing\)**.
    -   **Transmit Direction**: Select the direction of the route map. In this example, select **Export from Regional Gateway**.
    -   **Match Condition**: Set the matching conditions of the route map. In this example, add two matching conditions:
        -   **Source Instance ID**: Enter the instance ID of VBR2.
        -   **Target Instance ID**: Enter the instance ID of VBR1.
    -   **Match Mode**: Select the matching mode of the route map. In this example, select **Permit**.
    ![Configure the route map that allows VBR1 to access VBR2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280065/156776115255480_en-US.png)

    After you add the route map, you can view the route that allows IDC1 to access IDC2 on the **Routes** tab.

    ![Route that allows IDC1 to access IDC2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280065/156776115255562_en-US.png)


## Step 2: Set a route map that allows IDC2 to access IDC1 {#section_93p_493_xaj .section}

To set a route map that allows IDC2 to access IDC1, follow these steps:

1.  In the left-side navigation pane, click **Instances**.
2.  On the Instances page, find the target CEN instance**and click Manage****in the Actions** column.
3.  On the CEN page, click**the Route Maps** tab, and then click**Add Route Map**.
4.  In the Add Route Map dialog box, configure the route map according to the following information and then click**OK**. 

    -   **Priority**: Enter the priority of the route map. A smaller number represents a higher priority. In this example, enter **20**.
    -   **Region**: Select the region to which the route map is applied. In this example, select **China \(Hangzhou\)**.
    -   **Transmit Direction**: Select the direction of the route map. In this example, select **Export from Regional Gateway**.
    -   **Match Condition**: Set the matching conditions of the route map. In this example, add two matching conditions:
        -   **Source Instance ID**: Enter the instance ID of VBR1.
        -   **Target Instance ID**: Enter the instance ID of VBR2.
    -   **Match Mode**: Select the matching mode of the route map. In this example, select **Permit**.
    ![Route map that allows IDC2 to access IDC1](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280065/156776115255486_en-US.png)

    After you add the route map, you can view the route that allows IDC2 to access IDC1 on the **Routes** tab.

    ![Route that allows IDC2 to access IDC1](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1280065/156776115255564_en-US.png)


## Step 3: Test the network connectivity {#section_shj_1u8_ovm .section}

To test the network connectivity between IDC1 and IDC2, follow these steps.

1.  Open the command prompt of the PC at the on-premises data center IDC1.
2.  Use the ping command to ping the IP address of the PC at the on-premises data center IDC2.. The output shows that the PC of IDC1 can access the PC of IDC2.

    ![PC of IDC1 can access the PC of IDC2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776115254781_en-US.png)

3.  Open the command prompt of the PC of IDC2.
4.  Use the ping command to ping the IP address of the PC of IDC1. The output shows that the PC of IDC2 can access the PC of IDC1.

    ![PC of IDC2 can access the PC of IDC1](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156776115254768_en-US.png)


