# Withdraw a route from CEN {#task_1780835 .task}

This topic describes how to withdraw a route from Cloud Enterprise Network \(CEN\). You can withdraw a route that has been published to CEN. After the route is withdrawn, other networks attached to the same CEN instance cannot learn the route. If you publish a custom VPC or Virtual Border Router \(VBR\) route entry to a CEN instance and then delete the route from the VPC or VBR route table, the route entry is also deleted from CEN.

The following table lists the route entries that can be withdrawn from CEN.

**Note:** Currently, the console only supports withdrawing VPC routes from CEN. If you need to withdraw VBR routes, call WithdrawPublishedRouteEntries. For more information, see [WithdrawPublishedRouteEntries](../../../../reseller.en-US/API Reference/Manage routes/WithdrawPublishedRouteEntries.md#).

|Route entries|Network|Published to CEN by default?|
|:------------|:------|:---------------------------|
|A route entry pointing to an ECS instance|VPC|No|
|A route entry pointing to a VPN Gateway|VPC|No|
|A route entry pointing to a High-Availability Virtual IP Address \(HaVip\)|VPC|No|
|A VPC system route entry|VPC|Yes|
|A route entry pointing to an on-premises data center|VBR|Yes|
|A BGP route entry|VBR|Yes|

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  On the Instances page, find the target CEN instance and click **Manage** in the **Actions** column.
3.  On the CEN page, click the **Networks** tab. Find the target VPC and click the VPC ID.
4.  On the VPC Details page, click the link to the route table.
5.  On the Route Tables page, find the target route table, and click **Manage** in the **Actions** column.
6.  On the **Route Entry List** tab, find the target route entry, and click **Withdraw** in the **Route Status in CEN** column.
7.  In the Withdraw Published Route Entry dialog box, click **OK**.

