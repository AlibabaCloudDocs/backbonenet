# Connect networks in the same region using the same account {#concept_u15_r3b_tdb .concept}

This tutorial guides you how to use CEN to connect the networks in the same region of the same account.

## Prerequisite {#section_s15_w3b_tdb .section}

-   You have created VPCs or VBRs.

-   The VPCs and VBRs are not connected using Express Connect.


## Step 1 Create a CEN instance {#section_snn_y3b_tdb .section}

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).
2.  On the Instances page, click Create CEN instance.
3.  Configure the CEN instance.
    -   **Name**: The name of the CEN instance. The name can contain 2-128 English letters, numbers, hyphens, or underlines, and must start with English letters. In this tutorial, enter **SameRegionSameAccount**.
    -   **Attach a network**:

        -   **Account**: Select **Your Account**.
        -   **Network Type**: Select the network to connect. You can attach a VPC or a VBR. In this tutorial, select **VPC**.
        -   **Region**: Select the region of the network. In this tutorial, select **China North 1**.
        -   **Networks**: Select the instance to attach. In this tutorial, select a VPC instance.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3044/859_en-US.png)


## Step 2 Attach networks { .section}

1.  On the Instances page, click the **Manage** option under the **Action** column of the created CEN instance.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3044/860_en-US.png)

2.  On the **Networks** page, Click **Attach Network** and configure the network as follows:
    -   **Account**: Select **Your Account**.
    -   **Network Type**: Select the network to connect. You can attach a VPC or a VBR. In this tutorial, select **VPC**.
    -   **Region**: Select the region of the network. In this tutorial, select **China North 2**.
    -   **Networks**: Select the instance to attach. In this tutorial, select a VPC instance.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3044/5956_en-US.png)


## Step 3 Test the connectivity {#section_ucp_y3b_tdb .section}

Log on to any ECS instance in an attached network and ping the private IP of another ECS instance in another attached network to test the connectivity.

**Note:** Make sure that corresponding authorization rules are configured in the security groups of the ECS instances.

