# Grant permissions to CCN {#concept_bby_dmy_pgb .concept}

If you need to access the PrivateZone service through local branches of a Cloud Connect Network \(CCN\) in a Cloud Enterprise Network \(CEN\) instance, you must grant permissions to the CCN.

## Same CEN, VPC, and CCN account {#section_bvq_vl1_qgb .section}

If the CCN, the VPC that is configured with PrivateZone, and the CEN instance all belong to the same account, you need to click **Authorization** on the PrivateZone tab, and grant permissions to CCN by following the prompts. The following table provides example information of this scenario.

|Resource|User ID|
|--------|-------|
|CEN|111111|
|VPC|111111|
|CCN|111111|

After you grant permissions to the CCN, the system automatically creates a RAM role named **AliyunSmartAGAccessingPVTZRole**. You can view the RAM role on the RAM Roles page of the [RAM console](https://ram.console.aliyun.com/roles).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122769/156508377238863_en-US.png)

## Same CEN and VPC account, but different CCN account {#section_igl_bp1_qgb .section}

If the CEN instance and the VPC that is configured with PrivateZone belong to the same account, but the CCN belongs to a different account, you need to modify the authorization policy. The following table provides example information of this scenario.

|Resource|User ID|
|--------|-------|
|CEN|111111|
|VPC|111111|
|CCN|333333|

To grant permissions to the CCN, follow these steps:

**Note:** You need to use the account to which the VPC belongs.

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).
2.  Click the ID of the target CEN instance.
3.  Click the **PrivateZone** tab, and then click **Authorization**. Grant permissions to the CCN by following the prompts.
4.  Go to the [RAM console](https://ram.console.aliyun.com/roles).
5.  In the left-side navigation pane, click **RAM Roles**.
6.  In the search box, enter **AliyunSmartAGAccessingPVTZRole** and click the displayed role name.
7.  Click the Trust Policy Management tab and then click **Edit Trust Policy**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122769/156508377238865_en-US.png)

8.  In Service, add a record of `account ID of the CCN@smartag.aliyuncs.com` and click **OK**.

## Same CCN and VPC account, but different CEN account {#section_aw1_mt1_qgb .section}

If the CCN and the VPC that is configured with PrivateZone belong to the same account, but the CEN instance belongs to a different account, you need to create a RAM role and grant it permissions by using the account of the VPC. The following table provides example information of this scenario.

|Resource|User ID|
|--------|-------|
|CEN|333333|
|VPC|111111|
|CCN|111111|

To grant permissions to the CCN, follow these steps:

1.  Log on to the [RAM console](https://ram.console.aliyun.com/) by using the credentials of the account to which the VPC belongs.
2.  In the left-side navigation pane, click **RAM Roles**.
3.  Click **Create RAM Role**, configure it by referring to the following description, and then click **OK**.
    -   **Select type of trusted entity**: Select **Alibaba Cloud Service**.
    -   **Select Trusted Service**: Select **smartag Smart Access Gateway**.
    -   **RAM Role Name**: Enter **AliyunSmartAGAccessingPVTZRole**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122769/156508377238428_en-US.png)

4.  Click the created RAM role name.
5.  On the Permissions tab, click **Add Permissions**.
6.  In the search box, enter **pvtz** and click the displayed **AliyunPvtzReadOnlyAccess** policy.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122769/156508377338429_en-US.png)

7.  Go back to the RAM role details page, and click the Trust Policy Management tab to view the permission information.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122769/156508377338430_en-US.png)


## Three different accounts {#section_ul3_qv1_qgb .section}

If the CCN, the VPC that is configured with PrivateZone, and the CEN instance belong to three different accounts, you need to complete the following tasks:

|Resource|User ID|
|--------|-------|
|CEN|111111|
|VPC|222222|
|CCN|333333|

1.  Use the account of the VPC to create a RAM role and grant it permissions. For more information, see [Same CCN and VPC account, but different CEN account](#section_aw1_mt1_qgb).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122769/156508377338430_en-US.png)

2.  Use the account of the VPC to modify the policy associated with the corresponding RAM role by adding the CCN service in the format of `CCN account ID@aliyuncs.com`. For more information, see [Same CEN and VPC account, but different CCN account](#section_igl_bp1_qgb).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122769/156508377338427_en-US.png)


To allow multiple CCNs to access the PrivateZone service, add all the CCNs to the trust policy, as shown in the following figure.

|Resource|User ID|
|--------|-------|
|CEN|111111|
|VPC|222222|
|CCN|333333|
|CCN|444444|
|CCN|555555|

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122769/156508377338431_en-US.png)

