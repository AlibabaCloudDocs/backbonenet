# Enable overlapping routing {#task_1512598 .task}

This topic describes how to enable the overlapping routing function of a Cloud Enterprise Network \(CEN\) instance. After the overlapping routing function is enabled, CEN can learn overlapping routes that have the same prefix but different netmasks.

**Note:** The overlapping routing function is enabled for CEN instances created after March 1, 2019 by default.

## Before overlapping routing is enabled {#section_2vo_gid_68n .section}

Assume that VPC-A is attached to a CEN instance. A custom route entry with the destination CIDR block of 192.168.1.0/24 and the next hop of an ECS instance is added to VPC-A. By default, CEN will deny all routes with destination IP addresses of 192.168.1.0/x \(1<=x<=32\) learnt from other attached networks.

Similarly, if a route with the destination CIDR block 192.168.1.0/24 is learnt by VPC-A from CEN, you cannot create any route with the destination CIDR block 192.168.1.0/x \(1 <= x <= 32\) in VPC-A, and VPC-A rejects other routes that are sent from CEN with destination CIDR block of 192.168.1.0/x \(1 <= x <= 32\).

## After overlapping routing is enabled {#section_bmm_rzb_9o0 .section}

With overlapping routing enabled, CEN can learn overlapping routes that have the same prefix but different netmasks.

Assume that a custom route with destination CIDR block of 192.168.1.0/24 and the next hop of ECS1 is added to VPC-A which has been attached to a CEN instance. After you enable overlapping routing, routes that are published from other networks in the CEN instance with destination CIDR block of 192.168.0.0/16 can still be accepted by VPC-A.

Also, the routes with the destination CIDR blocks 192.168.1.0/24 and 192.168.0.0/16 can be learned by CEN. CEN uses the longest prefix match algorithm to route traffic.

**Note:** After the overlapping routing function is enabled, VPC does not accept routes that are subsets of its VSwitch. Assume that the CIDR block of a VSwitch is 10.0.0.0/16. The VPC to which the VSwitch belongs does not accept routes with the CIDR block 10.0.0.0/24 but accepts routes with the CIDR block 10.0.0.0/8.

## Procedure {#section_5pu_dny_ybj .section}

To enable the overlapping routing function, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  On the Instances page, find the target CEN instance and click **Manage** in the **Actions** column.
3.  In the Basic Settings section, click **Enable** next to **Overlapping Routing Function**.
4.  In the Enable Overlapping Routing dialog box, click **OK**. 

    **Note:** After the overlapping routing function is enabled, it cannot be disabled.


