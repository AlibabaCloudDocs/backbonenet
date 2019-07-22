# Routing policies {#concept_994907 .concept}

This topic describes the routing policy feature of Cloud Enterprise Network \(CEN\). By setting routing policies, you can filter route information and modify route attributes to control the communication between networks attached to CEN.

## Overview {#section_g3p_9s8_f5s .section}

You can configure one or more inbound and outbound routing policy nodes on a CEN instance in each region. Each node contains routing conditions and executions. Each node is assigned a number to indicate its priority. A smaller number indicates a higher priority. When a route is processed, the conditions contained in the node with the highest priority is first checked to see if the route matches the conditions. If the route matches the conditions, it is permitted or denied based on the routing policy settings. If a route is permitted, you can modify the routing attributes of this route.

![Routing policies](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803311/156376843851040_en-US.png)

## Elements of a routing policy {#section_6rr_6rj_3pj .section}

A routing policy consists of basic policy information, matching conditions, and executions.

**Note:** Executions are only supported when the policy action is set to "Permit". If the policy action is set to "Deny", you cannot set executions.

-   The basic policy information contains the following elements.

    |Element|Description|
    |-------|-----------|
    |**Priority**|The priority of the routing policy node. A smaller number represents a higher priority. The priorities of nodes in the same region and the same direction must be unique. When a route is processed, the node with the smallest number is checked for matching first. Therefore, we recommend that you specify an appropriate priority for each node.

 |
    |**Description**|The description of the routing policy.|
    |**Region**|The region where the routing policy is applied.|
    |**Direction**|The direction of the routing policy.     -   RegionIn: Indicates outbound routing from a node.
    -   RegionOut: Indicates inbound routing to a node.
 |
    |**Action**|The action performed if a route matches all the matching conditions. The following actions are supported:     -   Permit: The route is permitted.
    -   Deny: The route is rejected.
 |
    |**Associated policy priority**|The priority of the next associated routing policy node.|

-   The matching conditions consist of the following elements:

    |Element|Description|
    |-------|-----------|
    |**Region**|The region of a matched route. Only the source region can be set as a matching condition.|
    |**Instance type**|The instance type of a matched route. The following instance types can be set as matching conditions:     -   The type of the source instance
    -   The type of the target instance
    -   The types of the source and target instances
 |
    |**The list of instance IDs**|The list of instance IDs contained in a matched route. The following instance IDs can be set as matching conditions:     -   The list of source instance IDs
    -   The list of target instance IDs
    -   The list of source and target instance IDs
 |
    |**Route table**|The route table of a matched route. The following route tables can be set as matching conditions:     -   Source route table
    -   Destination route table
    -   Source and destination route tables
 |
    |**Route type**|The type of a matched route. The following route types can be set as matching conditions:     -   System route
    -   User route
    -   BGP route
 |
    |**Route prefix**|The prefix of a matched route. The following matching modes are supported:     -   Fuzzy matching
    -   Exact matching
 |
    |**AS Path**|The AS Path of a matched route. The following matching modes are supported:     -   Fuzzy matching
    -   Exact matching
 **Note:** The AS Path is a well-known mandatory attribute, which describes the numbers of the ASs that a BGP route passes through during transmission.

 |
    |**Community**|The community of a matched route. The following matching modes are supported:     -   Fuzzy matching
    -   Exact matching
 **Note:** Community is an optional transitive attribute. You can set different community attribute values for different routes. A downstream router can use the community attribute value to match the target route.

 |

-   The executions consist of the following elements.

    |Element|Description|
    |-------|-----------|
    |**Community**|Set the community attribute value. The following settings are supported:     -   Add: Set a value for the community attribute.
    -   Replace: Modify the value of the community attribute.
 |
    |**Route priority**|Set the priority of the permitted route.|


## Matching process {#section_h1g_wng_q7s .section}

Routing policies use the match-action mode. Specifically, executions are performed only after conditions are matched. When a route is processed, the node with the highest priority is checked for matching first.

-   If the route matches all the matching conditions on the node, the policy action is then checked.
    -   If the policy action is set to "Permit", the executions in the node are performed and the route is allowed.
    -   If the policy action is set to "Deny", the route is rejected and the matching process ends immediately.
-   If the route fails to match any matching condition on the node, the next node is checked to see if the route matches the conditions in this next node.
-   If the route matches all the matching conditions on the next node, the policy action is then determined.
    -   If the policy action is set to "Permit", the executions on the node are performed and the route is allowed.
    -   If the policy action is set to "Deny", the route is rejected and the matching process ends immediately.
-   If the route fails to match any matching condition on the next node, another node is checked to see if the route matches the conditions in this node.
-   If the route fails to match all the nodes, the route is allowed.

![Matching process](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803311/156376843851016_en-US.png)

## Scenarios {#section_z3z_9s4_00y .section}

The routing policy can be used in the following scenarios:

-   Control the communication between two VPCs, or between a VPC and a VBR or CCN

    VPCs can communicate with VPCs, Virtual Border Routers \(VBRs\), and Cloud Connect Networks \(CCNs\) that are attached to the same CEN instance by default. However, you may need to block the communication between two VPCs, or between a VPC and a VBR or CCN, as shown in the following figure.

    ![Control the communication between two VPCs, or between a VPC and a VBR or CCN ](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803311/156376843851086_en-US.png)

    You can use routing policies to block the communication between VPC1 and VPC2 while VPC1 and VPC2 can communicate with CCN1 and VBR1 normally.

-   Control the communication between two VBRs or between a VBR and a CCN

    VBRs cannot communicate with VBRs or CCNs that are attached to the same CEN instance by default. However, you may need to enable the communication between two VBRs or between a VBR and a CCN, as shown in the following figure.

    ![Control the communication between two VBRs or between a VBR and a CCN](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803311/156376843851104_en-US.png)

    You can use routing policies to enable the communication between VBR1 and VBR2 while the communication between VBR1 and CCN1, and that between VBR2 and CCN1 are blocked.

-   Control the communication between two CCNs or between a CCN and a VBR

    CCNs cannot communicate with CCNs or VBRs that are attached to the same CEN instance by default. However, you may need to enable the communication between two CCNs or between a VBR and a CCN, as shown in the following figure.

    ![Control the communication between two CCNs or between a CCN and a VBR](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/803311/156376843851135_en-US.png)

    You can use routing policies to enable the communication between CCN1 and CCN2 while the communication between VBR1 and CCN1, and that between VBR1 and CCN2 are blocked.


## References {#section_f4u_x3b_mkj .section}

[CreateCenRouteMap](../../../../reseller.en-US/API Reference/Routing policies/CreateCenRouteMap.md#)

[DescribeCenRouteMaps](../../../../reseller.en-US/API Reference/Routing policies/DescribeCenRouteMaps.md#)

[ModifyCenRouteMap](../../../../reseller.en-US/API Reference/Routing policies/ModifyCenRouteMap.md#)

[DeleteCenRouteMap](../../../../reseller.en-US/API Reference/Routing policies/DeleteCenRouteMap.md#)

