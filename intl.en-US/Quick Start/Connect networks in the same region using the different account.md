# Connect networks in the same region using the different account {#concept_vvj_pjf_tdb .concept}

This tutorial guides you how to use CEN to connect the networks in the same region of different accounts.

It takes Account A and Account B as an example to introduce how to attach a network under Account B to a CEN instance under Account A.

## Prerequisite {#section_s15_w3b_tdb .section}

-   You have created VPCs or VBRs.

-   The VPCs and VBRs are not connected using Express Connect.


## Step 1 Account A creates a CEN instance {#section_snn_y3b_tdb .section}

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).
2.  On the Instances page, click Create CEN instance.
3.  Configure the CEN instance.
    -   **Name**: The name of the CEN instance. The name can contain 2-128 English letters, numbers, hyphens, or underlines, and must start with English letters. In this tutorial, enter **SameRegionDifferentAccount**.
    -   **Attach a network**:

        -   **Account**: Select **Your Account**.
        -   **Network Type**: Select the network to connect. You can attach a VPC or a VBR. In this tutorial, select **VPC**.
        -   **Region**: Select the region of the network. In this tutorial, select **China North 1**.
        -   **Networks**: Select the instance to attach. In this tutorial, select a VPC instance.
4.  Step 2 Attach networks

    In this tutorial, the ID of the CEN instance is `cbn-xxxxxxxxxx4l7`.


## Step 2 Account B authorizes Account A to attach a network under Account B {#section_x3t_kh4_tdb .section}

Cross-account network instance loading requires authorization on the VPC or VBR detail page to be loaded, this operation takes VPC as an example.

1.  Use Account B to log on to the [VPC Console](https://vpcnext.console.aliyun.com/).
2.  In the left-side navigation pane, click **VPC**.
3.  Click the ID of the target VPC.
4.  On the **VPC Details** page, click **CEN Cross Account Authorization**.
5.  In the displayed dialog box, enter the ID of the account and the CEN instance to authorize, and then click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3046/926_en-US.png)


## Step 3 Account A attaches the network {#section_nr2_g34_tdb .section}

After the authorization is completed, Account A can attach the network of Account B:

1.  Use Account A to log on to the [CEN console](https://cen.console.aliyun.com/).
2.  On the Instances page, click the **Manage** option in the **Column** action of the created CEN instance.
3.  In the **Networks** tab, click **Attach Network** and configure the network as follows:
    -   **Account**: Select **Different Account**.
    -   **Owner Account**: Enter the ID of the account that owns the network to attach. In this tutorial, enter the account ID of Account B.
    -   **Network Type**: Select the network to connect. You can attach a VPC or a VBR. In this tutorial, select **VPC**.
    -   **Region**: Select the region of the network. In this tutorial, select **China North 1**.
    -   **Networks**: Select the instance to attach. In this tutorial, select a VPC instance.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3046/927_en-US.png)


## Step 4 Test the connectivity {#section_ucp_y3b_tdb .section}

Log on to any ECS instance in an attached network and ping the private IP of another ECS instance in another attached network to test the connectivity.

**Note:** Make sure that corresponding authorization rules are configured in the security groups of the ECS instances.

