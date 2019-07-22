# DescribeCenRouteMaps {#doc_api_Cbn_DescribeCenRouteMaps .reference}

Queries routing policies.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Cbn&api=DescribeCenRouteMaps) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-7qthudw0ll6jmc\*\*\*\*| The ID of the CEN instance.

 |
|Action|String|No|DescribeCenRouteMaps| Optional. The name of this action. Value: **DescribeCenRouteMaps**

 |
|CenRegionId|String|No|cn-beijing| Optional. The region of the CEN instance. To query the region ID, call [DescribeRegions](~~36063~~).

 |
|PageNumber|Integer|No|1| Optional. The page number of the routing policy list. Default value: 1

 |
|PageSize|Integer|No|10| Optional. The number of rows per page for a paged query. Maximum value: 50. Default value: 10.

 |
|RouteMapId|String|No|cenrmap-abcdedfghij\*\*\*\*| Optional. The ID of the routing policy.

 |
|TransmitDirection|String|No|RegionIn| Optional. The direction of the routing policy. Valid values:

 -   **RegionIn**: inbound routing to the CEN node
-   **RegionOut**: outbound routing from the CEN node

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|PageNumber|Integer|1| The current page number.

 |
|PageSize|Integer|10| The number of entries per page.

 |
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B45| The ID of the request.

 |
|RouteMaps| | | The routing policy details.

 |
|AsPathMatchMode|String|Include| The as-path matching mode as a matching condition. Valid values:

 -   **Include**: Indicates fuzzy matching.
-   **Complete**: Indicates exact matching.

 |
|CenId|String|cen-7qthudw0ll6jmc\*\*\*\*| The ID of the CEN instance.

 |
|CenRegionId|String|cn-hangzhou| The region of the CEN instance.

 |
|CidrMatchMode|String|Include| The prefix matching mode as a matching condition. Valid values:

 -   **Include**: Indicates fuzzy matching.
-   **Complete**: Indicates exact matching.

 |
|CommunityMatchMode|String|Include| The community attribute matching mode as a matching condition. Valid values:

 -   **Include**: Indicates fuzzy matching.
-   **Complete**: Indicates exact matching.

 |
|CommunityOperateMode|String|Additive| The operation on the community attribute as an execution. Valid values:

 -   **Additive**: Set a value for the community attribute.
-   **Replace**: Modify the value of the community attribute.

 |
|Description|String|abc| The description of the routing policy.

 |
|DestinationChildInstanceTypes| |VPC,VBR| The destination instance type as a matching condition. Valid values: **VPC** | **VBR** | **CCN**

 |
|DestinationCidrBlocks| |1.1.1.0/10, 2.0.0.0/16| The prefix list as a matching condition.

 |
|DestinationInstanceIds| |vpc-a, vpc-b, vbr-a| The list of target instance IDs as a matching condition.

 |
|DestinationInstanceIdsReverseMatch|Boolean|false| The matching method of the DestinationInstanceIds matching condition. Valid values:

 -   **false** \(default\): If the destination instance ID of a route is included in `DestinationInstanceIds`, the route does not match the node.
-   **true**: If the destination instance ID of a route is not included in `DestinationInstanceIds`, the route matches the node.

 |
|DestinationRouteTableIds| |vtb-a, vtb-b| The list of target route table IDs as a matching condition.

 |
|MapResult|String|Permit| The result action of the routing policy. Valid values:

 -   **Permit**: If a route matches all the matching conditions on the node, corresponding executions are performed and the route is allowed. If a route fails to match any matching condition on the node, the next node is checked to see if the route matches the conditions in this next node.
-   **Deny**: If a route matches all the matching conditions on the node, the route is rejected and the matching process ends immediately. If a route fails to match any matching condition on the node, the next node is checked to see if the route matches the conditions in this next node.

 |
|MatchAsns| |65501| The as-path list as a matching condition.

 |
|MatchCommunitySet| |65501:1,65001:2,60011| The communities of a matched route. This parameter is a matching condition.

 |
|NextPriority|Integer|33| The priority of the next associated routing policy node. Value range: **1** to **100**

 |
|OperateCommunitySet| |65501:1,65001:2,60011| The communities on which you perform operations. This parameter is an execute statement.

 |
|Preference|Integer|20| The priority of a matched route to be modified. This parameter is an execute statement.

 |
|Priority|Integer|22| The priority of the routing policy node. Value range: **1** to **100**

 |
|RouteMapId|String|cenrmap-abcdedfghij\*\*\*\*| The ID of the routing policy.

 |
|RouteTypes| |System,Custom,BGP| The route type as a matching condition. Valid values:

 -   **System**: Indicates system routes.
-   **Custom**: Indicates user routes.
-   **BGP**: Indicates BGP routes.

 |
|SourceChildInstanceTypes| |VPC,VBR,CCN| The source instance type as a matching condition. Valid values: **VPC** | **VBR** | **CCN**

 |
|SourceInstanceIds| |vpc-a, vpc-b, vbr-a| The source instance ID as a matching condition.

 |
|SourceInstanceIdsReverseMatch|Boolean|false| The matching method of the SourceInstanceIds matching condition. Valid values:

 -   **false** \(default\): If the source instance ID contained in a route is included in `SourceInstanceIds`, the route does not match the node.
-   **true**: If the source instance ID contained in a route is not included in `SourceInstanceIds`, the route matches the node.

 |
|SourceRegionIds| |cn-beijing, cn-hangzhou| The resource region ID as a matching condition.

 |
|SourceRouteTableIds| |vtb-a, vtb-b| The source route table ID as a matching condition.

 |
|TransmitDirection|String|RegionIn| The direction of the routing policy. Valid values:

 -   **RegionIn**: inbound routing to the CEN node
-   **RegionOut**: outbound routing from the CEN node

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCenRouteMaps
&CenId=cen-7qthudw0ll6jmc****
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeCenRouteMapsResponse>
  <RouteMaps>
    <RouteMap>
      <Status>Active</Status>
      <CenRegionId>cn-beijing</CenRegionId>
      <RouteMapId>cenrmap-jumdfzmj5sgggl****</RouteMapId>
      <MapResult>Permit</MapResult>
      <TransmitDirection>RegionIn</TransmitDirection>
      <CenId>cen-nh98vzx8gfhlwn****</CenId>
      <Priority>1</Priority>
    </RouteMap>
  </RouteMaps>
  <PageNumber>1</PageNumber>
  <TotalCount>1</TotalCount>
  <PageSize>10</PageSize>
</DescribeCenRouteMapsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"RouteMaps":{
		"RouteMap":[
			{
				"Status":"Active",
				"RouteMapId":"cenrmap-jumdfzmj5sgggl****",
				"CenRegionId":"cn-beijing",
				"MapResult":"Permit",
				"TransmitDirection":"RegionIn",
				"CenId":"cen-nh98vzx8gfhlwn****",
				"Priority":20
			}
		]
	},
	"TotalCount":1,
	"PageSize":10
}
```

## Errors {#section_ibo_8w8_9bx .section}

