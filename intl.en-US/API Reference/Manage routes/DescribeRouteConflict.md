# DescribeRouteConflict {#doc_api_Cbn_DescribeRouteConflict .reference}

Queries conflicting route entries in a specified router \(VRouter or VBR\).

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeRouteConflict&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|ChildInstanceId|String|Yes|vpc-bp18sth14qii3pn\*\*\*\*| The ID of the network.

 |
|ChildInstanceRegionId|String|Yes|cn-hangzhou| The ID of the region to which the network belongs.

 |
|ChildInstanceRouteTableId|String|Yes|vtb-bp174d1gje79u1g4t\*\*\*\*| The ID of the route table.

 |
|ChildInstanceType|String|Yes|VBR| The type of the router. Valid values:

 -   **VRouter**: Virtual routers
-   **VBR**: Virtual Border Routers

 |
|Action|String|No|DescribeRouteConflict| Optional. The name of this action. Value: **DescribeRouteConflict**

 |
|DestinationCidrBlock|String|No|172.16.xx.xx/24| Optional. The destination CIDR block.

 |
|PageNumber|Integer|No|1| Optional. The current page number.

 |
|PageSize|Integer|No|2| Optional. The number of entries per page.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|PageNumber|Integer|1| The current page number.

 |
|PageSize|Integer|1| The number of entries per page.

 |
|RequestId|String|B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0| The ID of the request.

 |
|RouteConflicts| | | The details of conflicting route entries.

 |
|DestinationCidrBlock|String|172.16.xx.xx/24| The destination CIDR block of the route entry.

 |
|InstanceId|String|vbr-bp174d1gje79u1\*\*\*\*| The ID of the router.

 |
|InstanceType|String|VBR| The type of the router. Valid values:

 -   **VRouter**: Virtual routers
-   **VBR**: Virtual Border Routers

 |
|RegionId|String|cn-hangzhou| The region ID.

 |
|Status|String|conflict| The cause of route exceptions. Valid values:

 -   **conflict**: The route entry is in conflict with other route entries.
-   **overflow**: The number of router entries in other networks exceeds the limit.
-   **prohibited**: The route entry is not allowed by VBR.

 |
|TotalCount|Integer|2| The total number of queried entries.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeRouteConflict
&ChildInstanceId=vpc-bp18sth14qii3pn****
&ChildInstanceRegionId=cn-hangzhou
&ChildInstanceRouteTableId=vtb-bp174d1gje79u1g4t****
&ChildInstanceType=VBR
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeRouteConflictResponse>
      <PageNumber>1</PageNumber>
      <PageSize>10</PageSize>
      <RequestId>B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0</RequestId>
      <RouteConflicts>
            <RouteConflict></RouteConflict>
      </RouteConflicts>
      <TotalCount>0</TotalCount>
</DescribeRouteConflictResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":0,
	"PageSize":10,
	"RequestId":"B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0",
	"RouteConflicts":{
		"RouteConflict":[]
	}
}
```

## Errors {#section_flm_o34_hqa .section}

