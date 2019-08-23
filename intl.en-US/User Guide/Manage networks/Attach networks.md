# Attach networks {#task_1563531 .task}

You can attach the networks \(VPCs, VBRs, and CCNs\) that need to communicate with each other to a Cloud Enterprise Network \(CEN\) instance. CEN automatically learns the routes of the attached networks to achieve intranet communication.

Before you attach networks, make sure the following conditions are met:

-   [Create a CEN instance](../reseller.en-US/Quick Start/Create a CEN instance.md#).
-   The networks to be attached are not attached to other CEN instances.

## Attach a network in the same account {#d7e31 .section}

To attach a network in the same account, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  On the Instances page, find the target CEN instance and click the instance ID.
3.  Click the Networks tab and then click **Attach Network**.
4.  Click the Your account tab.
5.  **Network Type**: Select the type of the network to be attached. You can attach VPCs, Virtual Border Routers \(VBRs\), and Cloud Connect Networks \(CCNs\).
6.  **Region**: Select the region of the network.
7.  **Networks**: Select the instance to be attached. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1240694/156654829454458_en-US.png)

8.  Click **OK**.

## Attach a network in a different account {#d7e108 .section}

**Note:** Before you attach a network of a different account, you must obtain permissions from this account. After obtaining permissions, you must obtain the ID of this account and the instance ID of the network.

For more information, see:

-   [Obtain permissions from a VPC](../reseller.en-US/User Guide/Manage networks/Cross-account authorization.md#section_mkn_v7p_lgn)
-   [Obtain permissions from a VBR](../reseller.en-US/User Guide/Manage networks/Cross-account authorization.md#section_2kc_03o_0us)
-   [Obtain permissions from a CCN](../reseller.en-US/User Guide/Manage networks/Cross-account authorization.md#section_gs1_agk_3o9)

To attach a network in a different account, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  On the Instances page, find the target CEN instance and click the instance ID.
3.  Click the Networks tab and then click **Attach Network**.
4.  Click the **Different Account** tab.
5.  **Owner Account**: Enter the ID of the account to which the network to be attached belongs.
6.  **Network Type**: Select the type of the network to be attached. You can attach VPCs, Virtual Border Routers \(VBRs\), and Cloud Connect Networks \(CCNs\).
7.  **Region**: Select the region of the network.
8.  **Networks**: Enter the instance ID of the network to be attached. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1240694/156654829554474_en-US.png)

9.  Click **OK**.

