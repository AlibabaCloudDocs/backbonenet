# DescribeCenRouteMaps {#doc_api_Cbn_DescribeCenRouteMaps .reference}

Queries the route maps of a CEN instance.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeCenRouteMaps&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-7qthudw0ll6jmc\*\*\*\*|The ID of the CEN instance.

 |
|Action|String|No|DescribeCenRouteMaps|The name of this action. Value: **DescribeCenRouteMaps**.

 |
|CenRegionId|String|No|cn-beijing|The ID of the region to which the CEN instance belongs. To query the region ID, call [DescribeRegions](~~36063~~).

 |
|RouteMapId|String|No|cenrmap-abcdedfghij\*\*\*\*|The ID of the route map.

 |
|TransmitDirection|String|No|RegionIn|The direction of the route map. Valid values:

 -   **RegionIn**: the direction in which a route is published to the regional gateway of the CEN instance.

For example, a route is published to the local regional gateway from a local network instance or from another region.

-   **RegionOut**: the direction in which a route is published from the regional gateway of the CEN instance.

For example, a route is published from a local regional gateway to another network instance in this region or to another regional gateway.


 |
|PageNumber|Integer|No|1|The page number of the list. Default value: **1**.

 |
|PageSize|Integer|No|10|The number of rows per page for a paged query. Maximum value: **50**. Default value: **10**.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RouteMaps| | |The route map details.

 |
|AsPathMatchMode|String|Include|A match statement. It indicates the mode in which the as-path attribute is matched. Valid values:

 -   **Include**: indicates fuzzy match. A route matches the condition if the AS path in the route overlaps the AS path in the match condition.
-   **Complete**: indicates exact match. A route matches the condition only when the AS path of the route is the same as the AS path in the match condition.

 |
|CenId|String|cen-7qthudw0ll6jmc\*\*\*\*|The ID of the CEN instance.

 |
|CenRegionId|String|cn-hangzhou|The region to which the CEN instance belongs.

 |
|CidrMatchMode|String|Include|A match statement. It indicates the mode in which the prefix attribute is matched. Valid values:

 -   **Include**: indicates fuzzy match. If the prefix of a route is contained in the prefix in the match condition, the route matches the condition.

For example, if the prefix in the match condition is set to 1.1.0.0/16 and the match method is set to Fuzzy Match, the route with the prefix of 1.1.1.0/24 matches the condition.

-   **Complete**: indicates exact match. A route matches the condition only when the prefix of the route is the same as the prefix in the match condition.

For example, if the prefix in the match condition is set to 1.1.0.0/16 and the match method is set to Exact Match, only the route with the prefix of 1.1.1.0/16 matches the condition.


 |
|CommunityMatchMode|String|Include|A match statement. It indicates the mode in which the community attribute is matched. Valid values:

 -   **Include**: indicates fuzzy match. A route matches the condition if the community of the route overlaps the community in the match condition.
-   **Complete**: indicates exact match. A route matches the condition only when the community of the route is the same as the community in the match condition.

 |
|CommunityOperateMode|String|Additive|An action statement. It indicates the mode in which the community attribute is operated. Valid values:

 -   **Additive**: sets a value for the community attribute.
-   **Replace**: modifies the value of the community attribute.

 |
|Description|String|abc|The description of the route map.

 |
|DestinationChildInstanceTypes| |VPC|A match statement that indicates the type of the target instance. Valid values: **VPC**|**VBR**|**CCN**.

 This parameter is valid only when the TransmitDirection parameter is set to RegionOut and the type of the target instance is the type of an instance in this region.

 |
|DestinationCidrBlocks| |1.1.1.0/10|A match statement that indicates the prefix list.

 |
|DestinationInstanceIds| |vpc-a|A match statement that indicates the ID of the target instance.

 This parameter is valid only when the TransmitDirection parameter is set to RegionOut and the ID of the target instance is the ID of an instance in this region.

 |
|DestinationInstanceIdsReverseMatch|Boolean|false|The match method of the DestinationInstanceIds match condition. Valid values:

 -   **false** \(default\): If the target instance's ID contained in a route is included in `DestinationInstanceIds`, the route is permitted.
-   **true**: If the target instance's ID contained in a route is not included in `DestinationInstanceIds`, the route is permitted.

 |
|DestinationRouteTableIds| |vtb-a|A match statement that indicates the ID of the target route table.

 This parameter is valid only when the TransmitDirection parameter is set to RegionOut and the target route table is a route table in this region.

 |
|MapResult|String|Permit|The match mode used if a route meets all match conditions. Valid values:

 -   **Permit**: permits a route if it meets all match conditions.
-   **Deny**: denies a route if it meets all match conditions.

 |
|MatchAsns| |65501|A match statement that indicates the As path list.

 |
|MatchCommunitySet| |65501:1|A match statement that indicates the community set.

 |
|NextPriority|Integer|33|The priority of the associated next route map. Value range: **1** to **100**.

 -   If this parameter is not set, the current route map is not associated with the next route map.
-   If this parameter is set to 1, the current route map is associated with the next route map.
-   If this parameter is set to a value that is not 1, the priority of the associated route map must be greater than that of the current route map.

 Only route maps whose **MapResult** is set to **Permit** will be checked whether they match the associated next route map after meeting all current match conditions.

 |
|OperateCommunitySet| |65501:1|An action statement that modifies the value of the community attribute.

 |
|Preference|Integer|20|An action statement that modifies the preference of the route.

 |
|Priority|Integer|22|The priority of the route map. Value range: **1** to **100**. A lower value indicates a higher priority.

 |
|RouteMapId|String|cenrmap-abcdedfghij\*\*\*\*|The ID of the route map.

 |
|RouteTypes| |System|A match statement that indicates the list of route types. Valid values:

 -   **System**: indicates routes generated by the system.
-   **Custom**: indicates routes added by users.
-   **BGP**: indicates routes advertised to BGP.

 |
|SourceChildInstanceTypes| |VPC|A match statement that indicates the type of the source instance. Valid values: **VPC**|**VBR**|**CCN**.

 |
|SourceInstanceIds| |vpc-a|A match statement that indicates the ID of the source instance.

 |
|SourceInstanceIdsReverseMatch|Boolean|false|The match method of the SourceInstanceIds match condition. Valid values:

 -   **false** \(default\): If the source instance's ID contained in a route is included in `SourceInstanceIds`, the route is permitted.
-   **true**: If the source instance's ID contained in a route is not included in `SourceInstanceIds`, the route is permitted.

 |
|SourceRegionIds| |cn-beijing|A match statement that indicates the ID of the source region.

 |
|SourceRouteTableIds| |vtb-a|A match statement that indicates the ID of the source route table.

 |
|Status|String|Active|The status of the route map. Valid values:

 -   **Active**: The route map is active.
-   **Creating**: The route map is being created.

 |
|TransmitDirection|String|RegionIn|The direction of the route map. Valid values:

 -   **RegionIn**: the direction in which a route is published to the regional gateway of the CEN.

For example, a route is published to the local regional gateway from a local network instance or from another region.

-   **RegionOut**: the direction in which a route is published from the regional gateway of the CEN.

For example, a route is published from a local regional gateway to another network instance in this region or to another regional gateway.


 |
|PageSize|Integer|10|The number of entries per page.

 |
|PageNumber|Integer|1|The current page number.

 |
|TotalCount|Integer|10|The total number of entries.

 |
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B45|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCenRouteMaps
&CenId=cen-7qthudw0ll6jmc****
&<CommonParameters>

```

Response example

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
			      <Priority>20</Priority>
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

## Errors { .section}

