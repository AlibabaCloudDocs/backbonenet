# Manage CEN network routes {#concept_s5p_xzn_q2b .concept}

Cloud Enterprise Network \(CEN\) supports publishing and withdrawing route entries of attached networks. You can publish a route entry of an attached VPC or Virtual Border Router \(VBR\) to a CEN instance. Then, other networks attached to the same CEN instance can learn the route if there is no route conflict. You can withdraw a published route entry when CEN does not need it any more.

**Note:** Currently, the CEN console only supports publishing and withdrawing VPC route entries and does not support publishing and withdrawing VBR route entries. You can publish and withdraw VBR route entries by calling the [../../../../dita-oss-bucket/SP\_17/DNBACK1880143/EN-US\_TP\_15168.md\#](../../../../intl.en-US/API Reference/Manage routes/PublishRouteEntries.md#) API.

The following table lists the route entries that can be published to CEN. You can withdraw a route entry that has been published to CEN. After a route entry is withdrawn, it does not exist in the CEN instance anymore. If you have published a custom route entry to a CEN instance and then delete it from the VPC or VBR route table, the route entry is also deleted from the CEN instance.

|Route entry|Network|Published to CEN by default?|
|:----------|:------|:---------------------------|
|A route entry pointing to an ECS instance|VPC|No|
|A route entry pointing to a VPN Gateway|VPC|No|
|A route entry pointing to a High-Availability Virtual IP Address \(HaVip\)|VPC|No|
|A system route entry|VPC|Yes|
|A route entry pointing to an on-premises data center|VBR|Yes|
|A BGP route entry|VBR|Yes|

As shown in the following figure, four VPCs are attached to a CEN instance. The VPC in the Hangzhou region is configured with a VPN Gateway to connect to the on-premises data center. After you publish the route entry pointing to the VPN Gateway in the VPC to the CEN instance, the other three VPCs learn the route and can also communicate with the on-premises data center.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16976/15663833608451_en-US.png)

## Publish a route entry to CEN {#section_qts_1ct_q2b .section}

To publish a route entry in a VPC to CEN, follow these steps:

**Note:** Make sure that the VPC is attached to a CEN instance.

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).
2.  On the Instances page, click the ID of the target CEN instance.
3.  On the **Networks** tab, click the ID of the target VPC.
4.  On the VPC Details page, click the link to the route table.
5.  On the Route Tables page, click the ID of the route table.
6.  Find the target route entry and click **Publish** in the **Route Status in CEN** column.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16976/15663833608328_en-US.png)

    After the route entry is successfully published, you can view the learnt routes in other networks.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16976/15663833608409_en-US.png)


## Withdraw a route entry from CEN {#section_jnx_z4t_q2b .section}

To withdraw a route entry published to CEN from a VPC, follow these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com/).
2.  On the Instances page, click the ID of the target CEN instance.
3.  On the **Networks** tab, click the ID of the target VPC.
4.  On the VPC Details page, click the link to the route table.
5.  On the Route Tables page, click the ID of the route table.
6.  Find the target route entry and click **Withdraw** in the **Route Status in CEN** column. In the displayed dialog box, click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16976/15663833608434_en-US.png)


