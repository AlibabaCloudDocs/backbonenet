# Migrate a VPC in a peering connection to a CEN instance {#concept_778704 .concept}

This topic describes how to migrate a VPC that uses a peering connection to a Cloud Enterprise Network \(CEN\) instance. By using CEN, you can build private network communication channels between VPCs or between VPCs and on-premises data centers. CEN uses automatic route distribution and learning, which can improve the network convergence and the quality and security of cross-network communication, and achieve the interconnection of all network resources.

**Warning:** After you migrate a VPC to a CEN instance, do not freeze or delete the same-region peering connections that belong to the China \(Hangzhou\) or China \(Shanghai\) regions.

## Prerequisites {#section_6p0_pcw_ejv .section}

If you want to use an existing CEN instance, make sure that the overlapping routing function is enabled.

**Note:** If the overlapping routing function is not enabled for the target CEN instance, enable the function first.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630333/156402047949935_en-US.png)

## Procedure {#section_lof_6p8_d68 .section}

To migrate a VPC in a peering connection to a CEN instance, follow these steps:

**Note:** Make sure that you have made the necessary preparations before migration.

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  On the Instances page, find the target CEN instance and click the instance ID.
3.  On the Networks tab, click **Attach Network** and add the VPC to be migrated. For more information, see [Networks](../../../../intl.en-US/User Guide/Networks.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630439/156402047949889_en-US.png)

4.  If you need the VPC to communicate with other resources that belong to different regions, you need to buy a bandwidth package and set an intranet communication bandwidth value.

    For more information, see [Set a cross-region interconnection bandwidth](../../../../intl.en-US/User Guide/Cross-region interconnection bandwidth.md#section_gtq_n5n_tdb).

5.  If you have added routes destined for ECS instances, VPN Gateways, or High-Availability Virtual IP Addresses \(HaVips\) in the VPC, you need to publish these routes to the CEN instance.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630439/156402047949940_en-US.png)

6.  Log on to the [CEN console](https://cen.console.aliyun.com/cen/detail/cen-0e7i2gmdfs6ymbxgay/route), click the ID of the target CEN instance, and on the **Routes** tab, check the routes. Make sure that the routes do not conflict with each other after you add the VPC to the CEN instance.

    The static route configured for the peering connection takes precedence over the dynamic route of the CEN instance. Specifically, if a static route is configured for the peering connection, no CEN route that is more detailed than or the same as the static route is allowed to be learnt by the CEN instance. In this case, we recommend that you divide a large route segment into smaller route segments and delete these routes after CEN learns the routes to ensure smooth migration.

    For example, the CEN route 172.16.1.0/24 in the following figure is more detailed than the route 172.16.0.0/16 configured for the peering connection, which constitutes a route conflict.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630439/156402047949944_en-US.png)

    -   You can directly delete the route of the peering connection through the VPC console. Then, the CEN route takes effect automatically. However, this method causes intermittent disconnections.

        The duration of disconnections is in proportion to the number of CEN routes. Therefore, we recommend that you use the following method to smoothly migrate the VPC for important services.

    -   You can divide the peering connection route 172.16.0.0/16 into two smaller route segments, 172.16.1.0/25 and 172.16.1.128/25, which are smaller than the CEN route 172.16.1.0/24.
        1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com) and find the route table to which the target peering connection route belongs.
        2.  Click **Add Route Entry**. Add two route entries that are respectively destined for 172.16.1.0/25 and 172.16.1.128/25 with the Express Connect route interface as the next hop type.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630439/156402048049945_en-US.png)

        3.  In the VPC route table, find the target peering connection route 172.16.0.0/16 and click **Delete** to delete this route.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630439/156402048049946_en-US.png)

        4.  Click **Refresh** to check if the CEN route has taken effect.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630439/156402048049947_en-US.png)

        5.  After the CEN route takes effect, delete the added two route entries 172.16.1.0/25 and 172.16.1.128/25 to complete the smooth migration.

