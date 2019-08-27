# Route map overview {#concept_994907 .concept}

This topic provides an overview of the route map function supported by Cloud Enterprise Networks \(CENs\). By using the route map function, you can filter route information and modify route attributes to manage the communication between networks attached to a CEN.

## Background information {#section_g3p_9s8_f5s .section}

A CEN instance has a regional CEN gateway in each region. The regional CEN gateways allow network instances \(VPC, VBR, and CCN instances\) attached to the CEN to communicate with each other. Routes can be transmitted to network instances in the same region or different regions through the inbound regional gateway \(Import to Regional Gateway\) and the outbound regional gateway \(Export from Regional Gateway\).

![Route map](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803311/156689485451040_en-US.png)

You can configure route maps for different regional gateways in a CEN. Each regional gateway can be configured with a route map in the inbound direction and the outbound direction. The corresponding route maps of each gateway consist of a set of conditional statements and executable statements that are sorted in ascending order of priority. When route maps are executed, the system first check whether the route map with the highest priority matches the conditional statements. The route map permits or denies routes. If a route is permitted, you can modify its attributes.

## Elements of a route map {#section_6rr_6rj_3pj .section}

A route map consists of basic information, match conditions, and actions.

**Note:** Actions are only supported when the match mode is set to Permit.

-   The following table describes the basic information of a route map.

    |Element|Description|
    |-------|-----------|
    |**Priority**|The priority of the route map. A lower value indicates a higher priority. The priority of route maps in the same region and the same direction must be unique. When route maps are executed, the system first check whether the route map with the highest priority matches the conditional statements. Therefore, we recommend that you specify an appropriate priority for each route map.

 |
    |**Description**|The description of the route map.|
    |**Region**|The region where the route map is applied.|
    |**Transmit Direction**|The direction of the route map.     -   Import to Regional Gateway: the direction in which a route is published to the regional gateway of the CEN. For example, a route is published to the local regional gateway from a local network instance or from another region.
    -   Export from Regional Gateway: the direction in which a route is published from the regional gateway of the CEN. For example, a route is published from a local regional gateway to another network instance in this region or to another regional gateway.
 |
    |**Match Mode**|The match mode used if a route matches all the matching conditions. The following match modes are supported:     -   Permit: The route is permitted.
    -   Deny: The route is denied.
 |
    |**Preference**|The preference of the associated next route map. Optional. Value range: 1 to 100.     -   If this parameter is not set, the current route map is not associated with the next route map.
    -   If this parameter is set to 1, the current route map is associated with the next route map.
    -   If this parameter is set to a value that is not 1, the preference of the associated route map must be greater than that of the current route map.
 Only route maps whose match mode is set to Permit will be checked whether they match route maps associated with preference after meeting all current match conditions.

 |

-   The following table describes the elements of a match condition.

    |Element|Description|
    |-------|-----------|
    |**Region**|The source region of a matched route.|
    |**Instance Type**|The instance type of a matched route. The following instance types are supported:     -   The type of the source instance
    -   The type of the target instance

**Note:** The type of the target instance is valid only when the Transmit Direction is set to Export from Regional Gateway and the type of the target instance is the type of instances in this region.

 |
    |**Instance ID**|The list of instance IDs contained in a matched route. The following instance IDs are supported:     -   A list of source instance IDs
    -   A list of target instance IDs

**Note:** The list of target instance IDs is valid only when the Transmit Direction is set to Export from Regional Gateway and the ID of the target instance is the ID of instances in this region.

 If an instance ID that matches the route is not in the instance ID list of the match condition, the matching succeeds. Otherwise, the matching fails.

 |
    |**Route Table**|The route table of a matched route. The following route tables are supported:     -   The source route table
    -   The target route table

**Note:** The target route table is valid only when the Transmit Direction is set to Export from Regional Gateway and the target route table is a route table in this region.

 |
    |**Route Type**|The type of a matched route. The following route types are supported:     -   System: the routes generated by the system.
    -   Custom: the custom routes.
    -   BGP: the routes advertised to BGP.
 |
    |**Route Prefix**|The prefix of a matched route. The following match methods are supported:     -   Fuzzy Match: If the prefix of a route to be matched is contained in the prefix in the match condition, the route matches the condition.

For example, if the prefix in the match condition is set to 1.1.0.0/16 and the match method is set to Fuzzy Match, the route with the prefix of 1.1.1.0/24 matches the condition.

    -   Exact Match: A route matches the condition only when the prefix of the route is the same as the prefix in the match condition.

For example, if the prefix in the match condition is set to 1.1.0.0/16 and the match method is set to Exact Match, only the route with the prefix of 1.1.1.0/16 matches the condition.

 |
    |**AS Path**|The AS path of a matched route. The following match methods are supported:     -   Fuzzy Match: A route matches the condition if the AS path in the route overlaps the AS path in the match condition.

For example, if the AS path in the match condition is set to \[65001, 65002\] and the match method is set to Fuzzy Match, the route with the AS path of \[65501, 65001\] matches the condition.

    -   Exact Match: A route matches the condition only when the AS path of the route is the same as the AS path in the match condition.

For example, if the AS path in the match condition is set to \[65501, 65001, 60011\] and the match method is set to Exact Match, only the route with the AS path of \[65501, 65001, 60011\] matches the condition.

 **Note:** The AS path is a well-known mandatory attribute, which describes the numbers of the ASs that a BGP route passes through during transmission.

 |
    |**Community**|The community of a matched route. The following match methods are supported:     -   Fuzzy Match: A route matches the condition if the community of the route overlaps the community in the match condition.

For example, if the community in the match condition is set to \[65001:1000, 65002:2000\] and the match method is set to Fuzzy Match, the route with the community of \[65501:1000, 65001:1000\] matches the condition.

    -   Exact Match: A route matches the condition only when the community of the route is the same as the community in the match condition.

For example, if the community in the match condition is set to \[65001:65001, 65002:65005, 65003:65001\] and the match method is set to Exact Match, only the route with the community of \[65001:65001, 65002:65005, 65003:65001\] matches the condition.

 **Note:** Community is an optional transitive attribute. You can set different community values for different routes. Downstream routers can use community values to match the target routes.

 |

-   The following table describes the elements of an action.

    |Element|Description|
    |-------|-----------|
    |**Community**|Set the community value. The following settings are supported:     -   Additive
    -   Replace
 |
    |**Preference**|Set the preference of the permitted routes.|


## Matching process of route maps {#section_h1g_wng_q7s .section}

Route maps use the match-action mode. Specifically, actions are performed only after conditions are matched. When route maps are executed, the system first check whether the route map with the highest priority matches the conditional statements.

-   If a route meet all the match conditions in the route map, the match mode is then checked.
    -   If the match mode is set to Permit, the executable statements in the route map are executed and the route is permitted. By default, the route will not be checked whether it matches the next route map unless the current route map is configured with a preference.
    -   If the match mode is set to Deny, the route is denied. By default, the route will not be checked whether it matches the next route map, and the matching process is immediately ended.
-   If the route fails to meet any match conditions in the current route map, the route will be checked whether it matches the next route map.
-   If the route matches all the match conditions in the next route map, the match mode is then checked.
    -   If the match mode is set to Permit, the executable statements in the route map are executed and the route is permitted. By default, the route will not be checked whether it matches the next route map unless the current route map is configured with a preference.
    -   If the match mode is set to Deny, the route is denied. By default, the route will not be checked whether it matches the next route map, and the matching process is immediately ended.
-   If the route fails to meet any match conditions in the current route map, the route will be checked whether it matches the next route map, and so on.
-   If the route fails to meet any match conditions in all route maps, the route is permitted.

![Matching process of route maps](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803311/156689485451016_en-US.png)

## Scenarios {#section_z3z_9s4_00y .section}

Route maps can be used in the following scenarios:

-   Control the communication between two VPCs, or between a VPC and a VBR or a CCN

    By default, a VPC can communicate with Virtual Border Routers \(VBRs\), Cloud Connect Networks \(CCNs\) and other VPCs that are attached to the same CEN instance. However, you may need to block the communication between two VPCs, or between a VPC and a VBR or a CCN in some cases, as shown in the following figure.

    ![Control the communication between two VPCs, or between a VPC and a VBR or a CCN ](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803311/156689485451086_en-US.png)

    You can use the route map function to block the communication between VPC1 and VPC2 while maintaining the communication between VPC1 and CCN1 or VBR1, or between VPC2 and CCN1 or VBR1.

-   Control the communication between two VBRs, or between a VBR and a VPC or a CCN

    By default, a VBR cannot communicate with CCNs or other VBRs that are attached to the same CEN instance. However, you may need to enable the communication between two VBRs or between a VBR and a CCN in some cases, as shown in the following figure.

    ![Control the communication between two VBRs, or between a VBR and a VPC or a CCN](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803311/156689485451104_en-US.png)

    You can use the route map function to enable the communication between VBR1 and VBR2 while blocking the communication between VBR1 and CCN1 and between VBR2 and CCN1.

-   Control the communication between two CCNs, or between a CCN and a VPC or a VBR

    By default, a CCN cannot communicate with VBRs or other CCNs that are attached to the same CEN instance. However, you may need to enable the communication between two CCNs or between a VBR and a CCN in some cases, as shown in the following figure.

    ![Control the communication between two CCNs, or between a CCN and a VPC or a VBR](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803311/156689485451135_en-US.png)

    You can use the route map function to enable the communication between CCN1 and CCN2 while blocking the communication between VBR1 and CCN1 and between VBR1 and CCN2.


## Limits {#section_jf7_of5_x4z .section}

The following table describes the limits that apply when you use the route map function.

|Item|Limit|Quota increase supported?|
|----|-----|-------------------------|
|Number of route maps that can be created in the inbound gateway direction in each region|100|Not supported.|
|Number of route maps that can be created in the outbound gateway direction in each region|100|Not supported.|

## Documentation {#section_f4u_x3b_mkj .section}

[Add a route map](reseller.en-US/User Guide/Routing policies/Add a route map.md#)

[Modify a route map](reseller.en-US/User Guide/Routing policies/Modify a route map.md#)

[Delete a route map](reseller.en-US/User Guide/Routing policies/Delete a route map.md#)

[Route map APIs](../../../../reseller.en-US/API Reference/API overview.md#section_zax_pco_bki)

