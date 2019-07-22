# ModifyCenRouteMap {#doc_api_Cbn_ModifyCenRouteMap .reference}

Modifies a routing policy.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Cbn&api=ModifyCenRouteMap) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-7qthudw0ll6jmc\*\*\*\*|The ID of the CEN instance.

 |
|CenRegionId|String|Yes|cn-hangzhou|The region of the CEN instance. To query the region ID, call [DescribeRegions](~~36063~~).

 |
|MapResult|String|Yes|Permit|The result action of the routing policy. Valid values:

 -   **Permit**: If a route matches all the matching conditions on the node, corresponding executions are performed and the route is allowed. If a route fails to match any matching condition on the node, the next node is checked to see if the route matches the conditions in this next node.
-   **Deny**: If a route matches all the matching conditions on the node, the route is rejected and the matching process ends immediately. If a route fails to match any matching condition on the node, the next node is checked to see if the route matches the conditions in this next node.

 |
|NextPriority|Integer|Yes|20|The priority of the next associated routing policy node. Value range: **1** to **100**

 |
|Priority|Integer|Yes|10|The priority of the routing policy node. Value range: **1** to **100**. A smaller number represents a higher priority.

 **Note:** The priorities of nodes in the same region and the same direction must be unique. When a route is processed, the node with the highest priority is checked first to see if the route matches the matching conditions on the node. Therefore, we recommend that you specify an appropriate priority for each node.

 |
|RouteMapId|String|Yes|cenrmap-abcdedfghij\*\*\*\*|The ID of the routing policy.

 |
|Action|String|No|ModifyCenRouteMap|Optional. The name of this action. Value: **ModifyCenRouteMap**

 |
|AsPathMatchMode|String|No|Include|Optional. The as-path matching mode as a matching condition. Valid values:

 -   **Include**: Indicates fuzzy matching.
-   **Complete**: Indicates exact matching.

 |
|CidrMatchMode|String|No|Include|Optional. The prefix matching mode as a matching condition. Valid values:

 -   **Include**: Indicates fuzzy matching.
-   **Complete**: Indicates exact matching.

 |
|CommunityMatchMode|String|No|Include|Optional. The community attribute matching mode as a matching condition. Valid values:

 -   **Include**: Indicates fuzzy matching.
-   **Complete**: Indicates exact matching.

 |
|CommunityOperateMode|String|No|Additive|Optional. The operation on the community attribute as an execution. Valid values:

 -   **Additive**: Set a value for the community attribute.
-   **Replace**: Modify the value of the community attribute.

 |
|Description|String|No|test|Optional. The description of the routing policy.

 |
|DestinationChildInstanceTypes.N|RepeatList|No|VPC,VBR,CCN|Optional. The target instance type as a matching condition. Valid values: **VPC** | **VBR** | **CCN**. Separate multiple instance types by using commas \(,\).

 |
|DestinationCidrBlocks.N|RepeatList|No|1.1.1.0/10, 2.0.0.0/16|Optional. The prefix as a matching condition. Use the CIDR notation. Separate multiple CIDR blocks by using commas \(,\). Up to 32 CIDR blocks can be entered.

 |
|DestinationInstanceIds.N|RepeatList|No|vpc-a, vpc-b, vbr-a|Optional. The target instance ID as a matching condition. Separate multiple instance IDs by using commas \(,\). Up to 32 instance IDs can be entered.

 |
|DestinationInstanceIdsReverseMatch|Boolean|No|false|Optional. The matching method of the DestinationInstanceIds matching condition. Valid values:

 -   **false** \(default\): If the destination instance ID contained in a route is included in `DestinationInstanceIds`, the route does not match the node.
-   **true**: If the destination instance ID contained in a route is not included in `DestinationInstanceIds`, the route matches the node.

 |
|DestinationRouteTableIds.N|RepeatList|No|vtb-a, vtb-b|Optional. The target route table ID as a matching condition. Separate multiple route table IDs by using commas \(,\). Up to 32 route table IDs can be entered.

 |
|MatchAsns.N|RepeatList|No|65501|Optional. The as-path as a matching condition.

 Only AS SEQUENCE is supported. AS SET, AS CONFED SEQUENCE, and AS CONFED SET are not supported. Specifically, only a list of AS numbers are supported. Sets and sub-lists are not supported.

 |
|MatchCommunitySet.N|RepeatList|No|65501:1,65001:2,60011|Optional. The communities of a matched route. This parameter is a matching condition. The format of each community is nn:nn. Value range of nn: **1** to **65535**. Separate multiple communities by using commas \(,\). Up to 32 communities can be entered. Communities must comply with RFC 1997. Large communities \(RFC 8092\) are not supported.

 **Note:** Community configuration errors may cause a problem that the route cannot be published to the on-premises data center.

 |
|OperateCommunitySet.N|RepeatList|No|65501:1,65001:2,60011|Optional. The communities on which you perform operations. This parameter is an execute statement. The format of each community is nn:nn. Value range of nn: **1** to **65535**. Separate multiple communities by using commas \(,\). Up to 32 communities can be entered. Communities must comply with RFC 1997. Large communities \(RFC 8092\) are not supported.

 **Note:** Community configuration errors may cause a problem that the route cannot be published to the on-premises data center.

 |
|Preference|Integer|No|22|Optional. The priority of a matched route to be modified. Value range: **1** to **100**. Default value: **50**. The smaller the value is, the higher the priority is.

 Routing priorities: the length of BGP as\_path \(a shorter as\_path represents a higher priority\) \> routes in the local region \> routes learnt from other regions \> routes modified through routemap

 |
|RouteTypes.N|RepeatList|No|System,Custom,BGP|Optional. The route type as a matching condition. Valid values:

 -   **System**: Indicates system routes.
-   **Custom**: Indicates user routes.
-   **BGP**: Indicates BGP routes.

 You can set multiple types. Separate multiple types by using commas \(,\).

 |
|SourceChildInstanceTypes.N|RepeatList|No|VPC,VBR,CCN|Optional. The source instance type as a matching condition. Valid values: **VPC** | **VBR** | **CCN**. Separate multiple instance types by using commas \(,\).

 |
|SourceInstanceIds.N|RepeatList|No|vpc-a, vpc-b, vbr-a|Optional. The source instance ID as a matching condition. Separate multiple instance IDs by using commas \(,\). Up to 32 instance IDs can be entered.

 |
|SourceInstanceIdsReverseMatch|Boolean|No|false|Optional. The matching method of the SourceInstanceIds matching condition. Valid values:

 -   **false** \(default\): If the source instance ID contained in a route is included in `SourceInstanceIds`, the route does not match the node.
-   **true**: If the source instance ID contained in a route is not included in `SourceInstanceIds`, the route matches the node.

 |
|SourceRegionIds.N|RepeatList|No|cn-beijing, cn-hangzhou|Optional. The source region ID as a matching condition. Separate multiple region IDs by using commas \(,\). Up to 32 region IDs can be entered.

 |
|SourceRouteTableIds.N|RepeatList|No|vtb-a, vtb-b|Optional. The source route table ID as a matching condition. Separate multiple route table IDs by using commas \(,\). Up to 32 route table IDs can be entered.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B457|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=ModifyCenRouteMap
&CenId=cen-7qthudw0ll6jmc****
&CenRegionId=cn-hangzhou
&MapResult=Permit
&NextPriority=20
&Priority=10
&RouteMapId=cenrmap-abcdedfghij****
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<ModifyCenRouteMapResponse>
  <RequestId>62172DD5-6BAC-45DF-8D44-xxxxxxxx</RequestId>
</ModifyCenRouteMapResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"62172DD5-6BAC-45DF-8D44-xxxxxxxx"
}
```

## Errors { .section}

