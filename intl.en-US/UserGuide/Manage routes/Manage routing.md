# Manage routing {#concept_s5p_xzn_q2b .concept}

Cloud Enterprise Network \(CEN\) supports publishing and withdrawing route entries of attached networks. You can publish a route entry of an attached VPC or VBR to a CEN instance, then other attached networks can learn the route if there is no route conflict. You can withdraw a published route entry when CEN does not need it any more.

**Note:** Currently, the console only supports publishing and withdrawing VPC routes and does not support publishing or withdrawing VBR routes. You can publish or withdraw VBR route entries by calling Open API [PublishRouteEntries](../../../../intl.en-US/API Reference/Manage route entries/PublishRouteEntries.md#).

The following table lists the route entries that can be published to CEN. You can withdraw a route entry that has been published to CEN. Once withdrawn, the route entry does not exist in the CEN instance anymore. If you have published a custom route entry to a CEN instance and then delete it from the VPC route table, the route entry is also deleted from the CEN instance.

|Route entries|Network|Publish to CEN by default|
|:------------|:------|:------------------------|
|A route entry pointing to an ECS instance|VPC|No|
|A route entry pointing to a VPN Gateway|VPC|No|
|A route entry pointing to a HaVip|VPC|No|
|A VPC system route entry|VPC|Yes|
|A route entry pointing to a local data center|VBR|Yes|
|A BGP route entry|VBR|Yes|

As shown in the following figure, four VPCs are attached to the CEN instance. The VPC in the Hangzhou region is configured with a VPN Gateway to connect to the local data center. After you publish the router entry pointing to the VPN Gateway in the VPC to the CEN instance, the other three VPCs learn the route and can also communicate with the local data center.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16976/15335391908451_en-US.png)

## Publish a route entry to CEN {#section_qts_1ct_q2b .section}

To publish a route entry in a VPC to CEN, complete these steps:

**Note:** Make sure that the VPC is attached to the CEN.

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  On the Instances page, click the ID of the target CEN instance.
3.  On the Networks page, click the ID of the target VPC.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16976/15335391908325_en-US.png)

4.  On the VPC Details page, click the link to the route table.
5.  On the Route Tables page, click the ID of the route table.
6.  Find the target route entry and click **Publish**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16976/15335391908328_en-US.png)

    After the route entry is successfully published, you can view the learnt routes in other networks.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16976/15335391908409_en-US.png)


## Withdraw a route entry from CEN {#section_jnx_z4t_q2b .section}

To withdraw a route entry published to CEN, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  On the Instances page, click the ID of the target CEN instance.
3.  On the Networks page, click the ID of the target VPC.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16976/15335391908325_en-US.png)

4.  On the VPC Details page, click the link to the route table.
5.  On the Route Tables page, click the ID of the route table.
6.  Find the target route entry and click **Withdraw**. In the displayed dialog box, click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16976/15335391918434_en-US.png)


