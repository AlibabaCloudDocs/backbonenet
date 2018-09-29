# View CEN routes {#concept_pst_dmh_tdb .concept}

CEN automatically realizes the multi-node adaptive routing forwarding and distribution. The adaptive routing process improves the network performance.

## View CEN routes on the CEN console {#section_xrg_dxn_tdb .section}

You can view routes of networks in other regions learned by the CEN instance. For example, a CEN instance has attached a VPC in China North 1 \(Qingdao\) and another VPC in China North 2 \(Beijing\). You can follow these steps to view routes learned from the VPC in China North 1.

To view the learned routes, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).
2.  Click the ID of the target CEN instance.
3.  Click **Routes** and select the region to query.

    Descriptions of fields in a route entry are as follows:

    |Field|Description|
    |:----|:----------|
    |**Region**|The region of the routes to query.|
    |**CIDR Block**|The learned CIDR block.|
    |**Destination Region**|The region of the learned CIDR block.|
    |**Destination Network ID**|The network to which the destination CIDR block belongs.|

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3052/1538231845913_en-US.png)


## View learned CEN routes in a VPC {#section_r3b_wxn_tdb .section}

To view the learned routes and conflict routes in a VPC, complete these steps:

1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com/vpc/).
2.  In the left-side navigation pane, click **Route Tables**.
3.  Click the ID of the target route table, then you can view CEN route entries in the **Route Entry List**.
4.  Click the icon next to the next hop of the CEN route entry to view the detailed information.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3052/1538231845914_en-US.png)


## View learned CEN routes in a VBR {#section_zkp_hyn_tdb .section}

To view the learned routes and conflict routes in a VBR, complete these steps:

1.  Log on to the [Express Connect](https://vpc.console.aliyun.com/expressConnect#/vbr/).
2.  In the left-side navigation pane, click **Physical Connection** \> **Virtual Border Router**.
3.  Click the ID of the target VBR, then you can view CEN route entries in the **Route Entry List**.

