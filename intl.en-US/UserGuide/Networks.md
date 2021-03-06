# Networks {#concept_gbk_1mh_tdb .concept}

## Attach networks {#section_s4y_4mh_tdb .section}

You can attach networks in the same account or a different to a CEN instance. To attach a network in a different account, authorization is required.

## Attach a network in the same account {#section_yq2_qph_tdb .section}

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).
2.  Click the ID of the target CEN instance.
3.  Click **Attach Network**.
4.  Choose **Your Account**, and configure the network according to the following information:

    |Configuration|Description|
    |-------------|-----------|
    |**Network Type**|Select the type of the network to attach.|
    |**Region**|Select the region of the network.|
    |**Networks**| Select the network.

 **Note**: You cannot select a network already attached to a CEN instance or connected using Express Connect.

 |
    |**Description**| Enter the description of the network.

 The description can contain 2-256 characters, and cannot start with `http://`  or `https://`.

 |

5.  Click **OK**.

## Attach a network in a different account {#section_slq_r4h_tdb .section}

To attach a network belonging to a different account, you must get authorized. The network owner must first authorize CEN to attach the network on the corresponding VPC page and VBR page. For more information, see [Cross-account network authorization](#Cross).

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).
2.  Click the ID of the target CEN instance.
3.  Click **Attach Network**.
4.  Choose **Different Account**, and configure the network according to the following information:

    |Configuration|Description|
    |-------------|-----------|
    |**Owner Account**|Enter the ID of the account that owns the network to attach.|
    |**Network Type**|Select the type of the network to attach.|
    |**Region**|Select the region of the authorized network.|
    |**Networks**|Enter the ID of the network to attach.|

5.  Click **OK**.

## Cross-account network authorization {#Cross .section}

To attach a network belonging to a different account, you must get authorized. 

## Cross-account authorization for VPC {#section_ahy_p4h_tdb .section}

1.  Use the account of the target VPC to log on to the [VPC console](https://vpc.console.aliyun.com/#/vpc/).
2.  In the left-side navigation pane, click **VPC**.
3.  Click the ID of the target VPC, and then click **CEN Cross Account Authorization** in the **CEN cross account authorization information** area.
4.  In the displayed dialog box, enter the ID of the account and the CEN instance to authorize.
5.  Click **OK**.

## Cross-account authorization for VBR {#section_ssh_2qn_tdb .section}

1.  Use the account of the target VBR to log on to the [Express Connect console](https://vpc.console.aliyun.com/expressConnect?spm=0.0.0.0.ETImM6#/vbr/).
2.  In the left-side navigation pane, click **Physical Connection \> Virtual Border Router**.
3.  Click the ID of the VBR to attach, and then click **CEN Cross Account Authorization** in the **CEN cross account authorization information** area.
4.  In the displayed dialog box, enter the ID of the account and the CEN instance to authorize.

## Rapidly join in a CEN instance {#section_kmm_p4h_tdb .section}

On the VPC Details or VBR Details page, you can rapidly join in a CEN instance of your account.

-   On the VPC Details page, click **Attach to CEN**, and then select the created CEN instance. Click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3049/893_en-US.png)

-   On the VBR Details page, click **Attach to CEN**, and then select the created CEN instance. Click **OK**.

## Detach a network {#section_kkl_xkn_tdb .section}

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).
2.  Click the ID of the target CEN instance.
3.  Click **Detach** in the **Actions** column of the target network.
4.  In the displayed dialog box, click **OK**.

