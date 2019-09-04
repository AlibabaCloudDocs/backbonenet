# ModifyCenRouteMap {#doc_api_Cbn_ModifyCenRouteMap .reference}

Modifies a route map of a CEN instance.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=ModifyCenRouteMap&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-7qthudw0ll6jmc\*\*\*\*|The ID of the CEN instance.

 |
|CenRegionId|String|Yes|cn-hangzhou|The region of the CEN instance. To query the region ID, call [DescribeRegions](~~36063~~).

 |
|MapResult|String|Yes|Permit|The match mode used if a route meets all match conditions. Valid values:

 -   **Permit**: permits a route if it meets all match conditions.
-   **Deny**: denies a route if it meets all match conditions.

 |
|Priority|Integer|Yes|10|The priority of the route map. Value range: **1** to **100**. A smaller value indicates a higher priority.

 **Note:** The priority of route maps in the same region and the same direction must be unique. When route maps are executed, the system first checks whether the route map with the highest priority matches the conditional statements. Therefore, we recommend that you specify an appropriate priority for each route map.

 |
|RouteMapId|String|Yes|cenrmap-abcdedfghij\*\*\*\*|The ID of the route map.

 |
|Action|String|No|ModifyCenRouteMap|The name of this action. Value: **ModifyCenRouteMap**.

 |
|NextPriority|Integer|No|20|The priority of the associated next route map. Value range: **1** to **100**.

 -   If this parameter is not set, the current route map is not associated with the next route map.
-   If this parameter is set to 1, the current route map is associated with the next route map.
-   If this parameter is set to a value that is not 1, the priority of the associated route map must be greater than that of the current route map.

 Only route maps whose **MapResult** is set to **Permit**, will be checked whether they match the associated next route map after meeting all current match conditions.

 |
|Description|String|No|test|The description of the route map.

 |
|SourceRegionIds.N|RepeatList|No|cn-beijing|A match statement that indicates the ID of the source region. Up to 32 region IDs can be entered.

 |
|SourceInstanceIds.N|RepeatList|No|vpc-a|A match statement that indicates the ID of the source instance. Up to 32 instance IDs can be entered.

 |
|SourceInstanceIdsReverseMatch|Boolean|No|false|The match method of the SourceInstanceIds match condition. Valid values:

 -   **false** \(default\): If the source instance's ID contained in a route is included in `SourceInstanceIds`, the route is permitted.
-   **true**: If the source instance's ID contained in a route is not included in `SourceInstanceIds`, the route is permitted.

 |
|DestinationInstanceIds.N|RepeatList|No|vpc-a|A match statement that indicates the ID of the target instance. Up to 32 instance IDs can be entered.

 This parameter is valid only when the TransmitDirection parameter is set to RegionOut and the ID of the target instance is the ID of an instance in this region.

 |
|DestinationInstanceIdsReverseMatch|Boolean|No|false|The match method of the DestinationInstanceIds match condition. Valid values:

 -   **false** \(default\): If the target instance's ID contained in a route is included in `DestinationInstanceIds`, the route is permitted.
-   **true**: If the target instance's ID contained in a route is not included in `DestinationInstanceIds`, the route is permitted.

 |
|SourceRouteTableIds.N|RepeatList|No|vtb-a|A match statement that indicates the ID of the source route table. Up to 32 route table IDs can be entered.

 |
|DestinationRouteTableIds.N|RepeatList|No|vtb-a|A match statement that indicates the ID of the target route table. Up to 32 route table IDs can be entered.

 This parameter is valid only when the TransmitDirection parameter is set to RegionOut and the target route table is a route table in this region.

 |
|SourceChildInstanceTypes.N|RepeatList|No|VPC|A match statement that indicates the type of the source instance. Valid values: **VPC**|**VBR**|**CCN**.

 |
|DestinationChildInstanceTypes.N|RepeatList|No|VPC|A match statement that indicates the type of the target instance. Valid values: **VPC**|**VBR**|**CCN**.

 This parameter is valid only when the TransmitDirection parameter is set to RegionOut and the type of the target instance is the type of an instance in this region.

 |
|DestinationCidrBlocks.N|RepeatList|No|1.1.1.0/10|A match statement that indicates the prefix list. The prefix is in the CIDR format. Up to 32 CIDR blocks can be entered.

 |
|CidrMatchMode|String|No|Include|A match statement. It indicates the mode in which the prefix attribute is matched. Valid values:

 -   **Include**: indicates fuzzy match. If the prefix of a route is contained in the prefix in the match condition, the route matches the condition.

For example, if the prefix in the match condition is set to 1.1.0.0/16 and the match method is set to Fuzzy Match, the route with the prefix of 1.1.1.0/24 matches the condition.

-   **Complete**: indicates exact match. A route matches the condition only when the prefix of the route is the same as the prefix in the match condition.

For example, if the prefix in the match condition is set to 1.1.0.0/16 and the match method is set to Exact Match, only the route with the prefix of 1.1.1.0/16 matches the condition.


 |
|RouteTypes.N|RepeatList|No|System|A match statement that indicates the list of route types. Valid values:

 -   **System**: indicates routes generated by the system.
-   **Custom**: indicates routes added by users.
-   **BGP**: indicates routes advertised to BGP.

 Multiple route types can be entered.

 |
|MatchAsns.N|RepeatList|No|65501|A match statement that indicates the As path list. The AS path is a well-known mandatory attribute, which describes the numbers of the ASs that a BGP route passes through during transmission.

 Only AS SEQUENCE is supported. AS SET, AS CONFED SEQUENCE, or AS CONFED SET are not supported. Specifically, only a list of AS numbers are supported. Sets or sub-lists are not supported.

 |
|AsPathMatchMode|String|No|Include|A match statement. It indicates the mode in which the as-path attribute is matched. Valid values:

 -   **Include**: indicates fuzzy match. A route matches the condition if the AS path in the route overlaps the AS path in the match condition.
-   **Complete**: indicates exact match. A route matches the condition only when the AS path of the route is the same as the AS path in the match condition.

 |
|MatchCommunitySet.N|RepeatList|No|65501:1|A match statement that indicates the community set. The format of each community is nn:nn, which ranges from **1** to **65535**. Up to 32 communities can be entered. Communities must comply with RFC 1997. Large communities \(RFC 8092\) are not supported.

 **Note:** Community configuration errors may cause a problem that the route cannot be published to the on-premises data center.

 |
|CommunityMatchMode|String|No|Include|A match statement. It indicates the mode in which the community attribute is matched. Valid values:

 -   **Include**: indicates fuzzy match. A route matches the condition if the community of the route overlaps the community in the match condition.
-   **Complete**: indicates exact match. A route matches the condition only when the community of the route is the same as the community in the match condition.

 |
|CommunityOperateMode|String|No|Additive|An action statement. It indicates the mode in which the community attribute is operated. Valid values:

 -   **Additive**: sets a value for the community attribute.
-   **Replace**: modifies the value of the community attribute.

 |
|OperateCommunitySet.N|RepeatList|No|65501:1|An action statement that operates the community attribute. The format of each community is nn:nn, which ranges from **1** to **65535**. Up to 32 communities can be entered. Communities must comply with RFC 1997. Large communities \(RFC 8092\) are not supported.

 **Note:** Community configuration errors may cause a problem that the route cannot be published to the on-premises data center.

 |
|Preference|Integer|No|22|An action statement that modifies the preference of the route. Value range: **1** to **100**. The default preference of a route is **50**. A lower value indicates a higher preference.

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
&Priority=10
&RouteMapId=cenrmap-abcdedfghij****
&<CommonParameters>

```

Response example

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

