# Networks {#concept_gbk_1mh_tdb .concept}

After you create a CEN instance, you must add networks that need to communicate with one another to the CEN instance. Currently, you can add VPCs, Virtual Border Routers \(VBRs\), and Cloud Connect Networks \(CCNs\) to a CEN instance.

You can attach networks in the same account or a different account to a CEN instance. To attach a network in a different account, authorization is required. For more information, see [Attach a network in a different account](reseller.en-US/User Guide/Attach a network in a different account.md#).

## Attach a network in the same account {#section_yq2_qph_tdb .section}

To attach a network with the same account, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  Click the ID of the target CEN instance.
3.  Click the **Networks** tab and then click **Attach Network**.
4.  Click the **Your Account** tab, and attach a network according to the following information.

    |Configuration|Description|
    |:------------|:----------|
    |**Network Type**|Select the type of the network to attach:     -   **VPC**: Attach a VPC.
    -   **Virtual Border Router \(VBR\)**: Attach an on-premises data center associated with the VBR.
    -   **Cloud Connect Network \(CCN\)**: Attach a local branch added to the CCN.
 |
    |**Region**|Select the region of the network.|
    |**Networks**| Select the network.

 **Note:** You cannot select a network that is already attached to a CEN instance or uses Express Connect.

 |

5.  Click **OK**.

## Attach a network in a different account {#section_slq_r4h_tdb .section}

To attach a network that belongs to a different account, you must grant permissions to the CEN instance by using the account of the network. For more information, see [Attach a network in a different account](reseller.en-US/User Guide/Attach a network in a different account.md#).

To attach a network in a different account, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  Click the ID of the target CEN instance.
3.  Click the **Networks** tab and then click **Attach Network**.
4.  Click the **Different Account** tab, and attach a network according to the following information.

    |Configuration|Description|
    |:------------|:----------|
    |**Owner Account**|Enter the ID of the account that owns the network to attach.|
    |**Network Type**|Select the type of the network to attach.|
    |**Region**|Select the region of the network to attach.|
    |**Networks**|Enter the ID of the network to attach.|

5.  Click **OK**.

## Attach VPCs or VBRs from the details page {#section_kmm_p4h_tdb .section}

You can attach VPCs or VBRs to a CEN instance directly from the VPC or VBR details page.

-   On the VPC details page, click **Attach to CEN** in the upper-right corner, and then select the target CEN instance. Click **OK**.
-   On the VBR details page, click **Join CEN**, and then select the target CEN instance. Click **OK**.

## Detach a network {#section_kkl_xkn_tdb .section}

To detach a network from a CEN instance, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  Click the ID of the target CEN instance. Click the **Networks** tab.
3.  Find the target network and click **Detach** in the **Actions** column.
4.  In the displayed dialog box, click **OK**.

