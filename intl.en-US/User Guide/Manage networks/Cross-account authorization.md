# Cross-account authorization {#task_1681162 .task}

Before you attach a network of a different account to a Cloud Enterprise Network \(CEN\) instance, you must obtain permissions from the network. After obtaining permissions, you must obtain the ID of the account to which the network belongs and the instance ID of the network.

-   The ID of the target CEN instance is obtained.
-   The ID of the account to which the target CEN instance belongs is obtained.

## Obtain permissions from a VPC {#section_mkn_v7p_lgn .section}

To obtain permissions from a VPC, follow these steps:

**Note:** If you grant permissions to another account, this account can attach your networks to its CEN instances and gain access to your networks. Therefore, we recommend that you exercise caution when you grant permissions to other accounts.

1.  Log on to the [VPC console](https://partners-intl.aliyun.com/login-required#/vpc) by using the credentials of the account to which the target VPC belongs.
2.  Select the region of the target VPC.
3.  On the VPCs page, find the target VPC, and click **Actions** in the **Manage** column.
4.  In the CEN cross account authorization information section, click **CEN Cross Account Authorization**.
5.  In the displayed Attach to CEN dialog box, enter the account ID of the target CEN instance and the ID of the target CEN instance, and then click **OK**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/7449/156695400556827_en-US.png)


## Obtain permissions from a VBR {#section_2kc_03o_0us .section}

To obtain permissions from a VBR, follow these steps:

**Note:** If you grant permissions to another account, this account can attach your networks to its CEN instances and gain access to your networks. Therefore, we recommend that you exercise caution when you grant permissions to other accounts.

1.  Log on to the [Express Connect console](https://partners-intl.console.aliyun.com/#/ri) by using the credentials of the account to which the target VBR belongs.
2.  In the left-side navigation pane, choose **Physical Connections** \> **Virtual Border Routers \(VBRs\)**.
3.  Select the region of the VBR.
4.  On the Virtual Border Routers \(VBRs\) page, find the target VBR and click the VBR ID.
5.  Click the **CEN authorization** tab, and then click **Authorize CEN of Another Account to Load Instance**.
6.  In the Authorize CEN of Another Account to Load Instance dialog box, enter the ID of the target CEN instance and the account ID of the target CEN instance, and click **OK**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/7449/156695400556837_en-US.png)


## Obtain permissions from a CCN {#section_gs1_agk_3o9 .section}

To obtain permissions from a CCN, follow these steps:

**Note:** If you grant permissions to another account, this account can attach your networks to its CEN instances and gain access to your networks. Therefore, we recommend that you exercise caution when you grant permissions to other accounts.

1.  Log on to the [Smart Access Gateway console](https://partners-intl.aliyun.com) by using the credentials of the account to which the target CCN belongs.
2.  In the left-side navigation pane, click **CCN**, find the target CCN, and click the instance ID of the CCN.
3.  Click **CEN Cross Account Authorization**, enter the account ID of the target CEN instance and the ID of the CEN instance, and click **OK**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/7449/156695400556877_en-US.png)


[Attach networks](reseller.en-US/User Guide/Manage networks/Attach networks.md#)

