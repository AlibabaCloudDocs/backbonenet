# Enable overlapping routing {#concept_irn_snm_gfb .concept}

Cloud Enterprise Network \(CEN\) automatically learns routes from attached networks. If two routes overlap, the conflicted routes will be denied. With overlapping routing enabled, CEN can learn overlapping routes that have same prefix but different netmasks.

## Enable overlapping routing {#section_p1w_tnm_gfb .section}

For example, VPC-A is already attached to a CEN instance. A custom route entry with the destination CIDR block of 192.168.1.0/24 and next hop of an ECS instance is added to the VPC-A. By default, all learned the routes of IP address 192.168.1.0/x \(1<=x<=32\) published by other networks will be denied by CEN.

Similarly, if VPC-A has a route entry destined to 192.168.1.0/24 that is learned from CEN, you are not allowed to add a custom rout entry with the destination CIDR block 192.168.1.0/x \(1<=x<=32\), and all the routes with the destination CIDR block 192.168.1.0/x \(1<=x<=32\) will be denied by VPC-A.

## After overlapping routing is enabled {#section_u2n_5nm_gfb .section}

With overlapping routing enabled, CEN can learn overlapping routes that have same prefix but different netmasks.

For example, VPC-A is already attached to a CEN instance. A custom route entry with the destination CIDR block of 192.168.1.0/24 and next hop of an ECS instance is added to the VPC-A. After overlapping routing is enabled, VPC-A can learn the route entry with the destination CIDR block 192.168.0.0/16 published by other networks in the CEN instance.

At the same time, the route entry with the CIDR block 168.1.0/24 and 192.168.0.0/16 can also be learned by CEN. CEN uses the longest prefix match algorithm to route traffic.

## Exception {#section_cyx_xnm_gfb .section}

After this function is enabled, VPC will not accept routes that are subsets of a VSwitch. For example, the CIDR block of a VSwitch is 10.0.0.0/16, then the VPC that the VSwitch is located will not accept the route with the CIDR block 10.0.0.0/24 but will accept the route with the CIDR block 10.0.0.0/8.

## Procedure {#section_rcs_c4m_gfb .section}

To enable the overlapping routing function, complete these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  Click the ID of the target CEN instance.
3.  In the **Basic Settings** area, click **Enable** next to the **Overlapping Routing Function** option.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21814/154993471112715_en-US.png)


**Note:** Once the overlapping routing function is enabled, it cannot be disabled.

