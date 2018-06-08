# Connect network instances in different regions using same account {#concept_pvm_j4n_tdb .concept}

This tutorial guides you how to use CEN to connect the networks in different regions of the same account.

## Prerequisite {#section_s15_w3b_tdb .section}

-   You have created VPCs or VBRs.

-   The VPCs and VBRs are not connected using Express Connect.


## Step 1 Create a CEN instance {#section_snn_y3b_tdb .section}

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).
2.  On the Instances page, click Create CEN instance.
3.  Configure the CEN instance.
    -   **Name**: The name of the CEN instance. The name can contain 2-128 English letters, numbers, hyphens, or underlines, and must start with English letters. In this tutorial, enter **Same.AccountDifferentRegion**.
    -   **Attach a network**:

        -   **Account**: Select **Same Account**.
        -   **Network Type**: Select the network to connect. You can attach a VPC or a VBR. In this tutorial, select **VPC**.
        -   **Region**: Select the region of the network. In this tutorial, select **China North 1**.
        -   **Networks**: Select the instance to attach.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3045/899_en-US.png)


## Step 2 Attach networks {#section_rzs_k4n_tdb .section}

1.  On the Instances page, click the **Manage** option in the **Column** action of the created CEN instance.
2.  In the **Networks** tab, click **Attach Network** and configure the network as follows:
    -   **Account**: Select **Your Account**.
    -   **Network Type**: Select the network to connect. You can attach a VPC or a VBR. In this tutorial, select **VPC**.
    -   **Region**: Select the region of the network. In this tutorial, select **China North 2**.
    -   **Networks**: Select the instance to attach. In this tutorial, select a VPC instance.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3045/901_en-US.png)


## Step 3 Account A buys a bandwidth package {#section_yrm_1rn_tdb .section}

To connect networks in different regions, you must buy a bandwidth package:

1.  On the Instances page, click the ID of the CEN instance, and then click the **Bandwidth Packages** tab.
2.  Click **Buy Bandwidth Package \(Subscription\)**.
3.  Configure the bandwidth package as follows:
    -   Cloud Enterprise Network: select the cloud Enterprise Network instance for which you want to purchase bandwidth packets.
    -   **CEN**: Select the CEN instance that requires a bandwidth package.

        **Areas**: Select the areas to connect. An area consists of one or more Alibaba Cloud regions. The networks to connect in this tutorial are located in China North 1 and China North 2. Therefore, the interconnection areas are Mainland China and Mainland China.

    -   **Bandwidth**: Select the bandwidth of the bandwidth package. In this tutorial, select **8 Mbps**.
    -   **Bandwidth Package Name**: Enter the name of the bandwidth package. In this tutorial, enter **MainlandBandwidthPackage**.
    -   **Purchase Period**: Select the purchase period. In this tutorial, select **1 month**.

## Step 4 Set the cross-region bandwidth {#section_nn5_bk4_tdb .section}

1.  On the Instances page, click the ID of the CEN instance, and then click the **Region Connections** tab.
2.  Click **Create Region Connection**.
3.  Configure the cross-region bandwidth:
    -   **Bandwidth Packages**: Select the interconnected areas of the bandwidth package. In this tutorial, select **Mainland China to Mainland China**.
    -   **Connected Regions**: Select the regions to connect. The selected regions must belong to the selected interconnected areas. In this tutorial, select **China North 1** and **China North 2**.
    -   **Bandwidth**: Set the cross-region bandwidth. In this tutorial, set the bandwidth to **5 Mbps**.

## Step 5 Test the connectivity {#section_ucp_y3b_tdb .section}

Log on to any ECS instance in an attached network and ping the private IP of another ECS instance in another attached network to test the connectivity.

**Note:** Make sure that corresponding authorization rules are configured in the security groups of the ECS instances.

