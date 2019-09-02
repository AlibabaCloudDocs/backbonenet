# DescribeCenChildInstanceRouteEntries {#doc_api_Cbn_DescribeCenChildInstanceRouteEntries .reference}

Queries the route entries of a network instance.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeCenChildInstanceRouteEntries&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-7qthudw0ll6jmc\*\*\*\*|The ID of the CEN instance.

 |
|ChildInstanceId|String|Yes|vpc-bp18sth14qii3pnvo\*\*\*\*|The ID of the network instance.

 |
|ChildInstanceRegionId|String|Yes|cn-hangzhou|The ID of the region to which the network instance belongs.

 |
|ChildInstanceType|String|Yes|vpc|The type of the network instance. Valid values:

 -   **VPC**: Virtual Private Cloud
-   **VBR**: Virtual Border Router
-   **CCN**: Cloud Connect Network

 |
|Action|String|No|DescribeCenChildInstanceRouteEntries|Optional. The name of this action. Value: **DescribeCenRegionDomainRouteEntries**

 |
|PageNumber|Integer|No|1|Optional. The page number. Default value: **1**

 |
|PageSize|Integer|No|10|Optional. The number of entries per page. Maximum value: **50**. Default value: **10**

 |
|Status|String|No|Active|Optional. The status of the route entry. Valid values:

 -   **Active**: Indicates that the route entry is available.
-   **Backup**: Indicates that the route entry works as a backup.
-   **Rejected**: Indicates that the route entry is rejected.
-   **Prohibited**: Indicates that the route entry is prohibited.
-   **All**: Indicates a route in any state.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|CenRouteEntries| | |A list of route entries.

 |
|AsPaths| |65501|The AS Path of the route entry. It is a BGP route attribute.

 |
|CenRouteMapRecords| | |The details of the route map.

 |
|RegionId|String|cn-hangzhou|The ID of the region to which the route map is applied.

 |
|RouteMapId|String|cenrmap-w4yf7toozfol3q\*\*\*\*|The ID of the route map.

 |
|Communities| |65501:1|The communities of the route entry. It is a BGP route attribute.

 |
|Conflicts| | |The details of conflicting route entries.

 |
|DestinationCidrBlock|String|192.168.1.0/24|The destination CIDR block of the conflicting route entries.

 |
|InstanceId|String|ecs-xxdjakjdakhfkfka\*\*\*\*|The ID of the conflicting network instance.

 |
|InstanceType|String|ECS|The type of the conflicting network instance.

 |
|RegionId|String|cn-hangzhou|The ID of the region to which the conflicting instance belongs.

 |
|Status|String|conflict|The cause of the conflict. Valid values:

 -   **conflict**: The route entry conflicts with other route entries.
-   **overflow**: The number of route entries in the route table of other network instances exceeds the limit.
-   **prohibited**: The route entry is not allowed by VBR policies.

 |
|DestinationCidrBlock|String|192.168.3.0/24|The destination CIDR block of the route entry.

 |
|NextHopInstanceId|String|vpc-o6woh5s494zueq40v\*\*\*\*|The instance ID of the next hop.

 |
|NextHopRegionId|String|cn-hangzhou|The ID of the region to which the next hop instance belongs.

 |
|NextHopType|String|VPC|The type of the next hop instance. Valid values:

 -   **VPC**: Virtual Private Cloud
-   **VBR**: Virtual Border Router

 |
|OperationalMode|Boolean|true|Indicates whether the route entry is allowed to be published to or withdrawn from CEN. Valid value:

 -   **true**: The route entry is allowed to be published to or withdrawn from CEN.
-   **False**: The route entry is not allowed to be published to or withdrawn from CEN.

 |
|PublishStatus|String|Published|Indicates whether the route entry is published to CEN.

 -   **Published**: The route entry is published to CEN.
-   **NonPublished**: The route entry is not published to CEN.

 |
|RouteTableId|String|vtb-bp1r9pvl4xen8s9ju\*\*\*\*|The ID of the route table.

 |
|Status|String|Active|The status of the route entry.

 |
|Type|String|CBN|The type of the route entry.

 |
|PageNumber|Integer|1|The current page number.

 |
|PageSize|Integer|10|The number of entries per page.

 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|The request ID.

 |
|TotalCount|Integer|30|The total number of route entries.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCenChildInstanceRouteEntries
&CenId=cen-7qthudw0ll6jmc****
&ChildInstanceId=vpc-bp18sth14qii3pnvo****
&ChildInstanceRegionId=cn-hangzhou
&ChildInstanceType=vpc
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeCenChildInstanceRouteEntriesResponse>
	  <PageNumber>1</PageNumber>
	  <TotalCount>4</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>17A57456-EF48-419D-9AE6-9B03D9996018</RequestId>
	  <CenRouteEntries>
		    <CenRouteEntry>
			      <NextHopInstanceId>vbr-bp13gtbhdp0pfqg6s****</NextHopInstanceId>
			      <CenRouteMapRecords>
				        <CenRouteMapRecord>
					          <RouteMapId>cenrmap-4lcjxzo2zyqjd3****</RouteMapId>
					          <RegionId>cn-hangzhou</RegionId>
				        </CenRouteMapRecord>
			      </CenRouteMapRecords>
			      <OperationalMode>false</OperationalMode>
			      <Status>Active</Status>
			      <AsPaths></AsPaths>
			      <Communities></Communities>
			      <Type>CEN</Type>
			      <RouteTableId>vtb-bp1r9pvl4xen8s9ju****</RouteTableId>
			      <NextHopRegionId>cn-hangzhou</NextHopRegionId>
			      <NextHopType>VBR</NextHopType>
			      <Conflicts></Conflicts>
			      <DestinationCidrBlock>10.0.0.0/24</DestinationCidrBlock>
		    </CenRouteEntry>
		    <CenRouteEntry>
			      <CenRouteMapRecords></CenRouteMapRecords>
			      <OperationalMode>false</OperationalMode>
			      <Status>Active</Status>
			      <AsPaths></AsPaths>
			      <Communities></Communities>
			      <Type>System</Type>
			      <RouteTableId>vtb-bp1r9pvl4xen8s9ju****</RouteTableId>
			      <NextHopType>service</NextHopType>
			      <Conflicts></Conflicts>
			      <DestinationCidrBlock>100.64.0.0/10</DestinationCidrBlock>
			      <PublishStatus>NonPublished</PublishStatus>
		    </CenRouteEntry>
		    <CenRouteEntry>
			      <CenRouteMapRecords></CenRouteMapRecords>
			      <OperationalMode>true</OperationalMode>
			      <Status>Active</Status>
			      <AsPaths></AsPaths>
			      <Communities></Communities>
			      <Type>System</Type>
			      <RouteTableId>vtb-bp1r9pvl4xen8s9ju****</RouteTableId>
			      <NextHopType>local</NextHopType>
			      <Conflicts></Conflicts>
			      <DestinationCidrBlock>172.16.0.0/24</DestinationCidrBlock>
			      <PublishStatus>Published</PublishStatus>
		    </CenRouteEntry>
		    <CenRouteEntry>
			      <NextHopInstanceId>vbr-bp13gtbhdp0pfqg6s****</NextHopInstanceId>
			      <CenRouteMapRecords>
				        <CenRouteMapRecord>
					          <RouteMapId>cenrmap-4lcjxzo2zyqjd3****</RouteMapId>
					          <RegionId>cn-hangzhou</RegionId>
				        </CenRouteMapRecord>
			      </CenRouteMapRecords>
			      <OperationalMode>false</OperationalMode>
			      <Status>Active</Status>
			      <AsPaths></AsPaths>
			      <Communities></Communities>
			      <Type>CEN</Type>
			      <RouteTableId>vtb-bp1r9pvl4xen8s9ju****</RouteTableId>
			      <NextHopRegionId>cn-hangzhou</NextHopRegionId>
			      <NextHopType>VBR</NextHopType>
			      <Conflicts></Conflicts>
			      <DestinationCidrBlock>192.168.2.0/24</DestinationCidrBlock>
		    </CenRouteEntry>
	  </CenRouteEntries>
</DescribeCenChildInstanceRouteEntriesResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":4,
	"PageSize":10,
	"RequestId":"17A57456-EF48-419D-9AE6-9B03D9996018",
	"CenRouteEntries":{
		"CenRouteEntry":[
			{
				"NextHopInstanceId":"vbr-bp13gtbhdp0pfqg6s****",
				"Status":"Active",
				"OperationalMode":false,
				"CenRouteMapRecords":{
					"CenRouteMapRecord":[
						{
							"RouteMapId":"cenrmap-4lcjxzo2zyqjd3****",
							"RegionId":"cn-hangzhou"
						}
					]
				},
				"AsPaths":{
					"AsPath":[]
				},
				"Communities":{
					"Community":[]
				},
				"Type":"CEN",
				"NextHopType":"VBR",
				"NextHopRegionId":"cn-hangzhou",
				"RouteTableId":"vtb-bp1r9pvl4xen8s9ju****",
				"DestinationCidrBlock":"10.0.0.0/24",
				"Conflicts":{
					"Conflict":[]
				}
			},
			{
				"Status":"Active",
				"OperationalMode":false,
				"CenRouteMapRecords":{
					"CenRouteMapRecord":[]
				},
				"AsPaths":{
					"AsPath":[]
				},
				"Communities":{
					"Community":[]
				},
				"Type":"System",
				"NextHopType":"service",
				"RouteTableId":"vtb-bp1r9pvl4xen8s9ju****",
				"DestinationCidrBlock":"100.64.0.0/10",
				"Conflicts":{
					"Conflict":[]
				},
				"PublishStatus":"NonPublished"
			},
			{
				"Status":"Active",
				"OperationalMode":true,
				"CenRouteMapRecords":{
					"CenRouteMapRecord":[]
				},
				"AsPaths":{
					"AsPath":[]
				},
				"Communities":{
					"Community":[]
				},
				"Type":"System",
				"NextHopType":"local",
				"RouteTableId":"vtb-bp1r9pvl4xen8s9ju****",
				"DestinationCidrBlock":"172.16.0.0/24",
				"Conflicts":{
					"Conflict":[]
				},
				"PublishStatus":"Published"
			},
			{
				"NextHopInstanceId":"vbr-bp13gtbhdp0pfqg6s****",
				"Status":"Active",
				"OperationalMode":false,
				"CenRouteMapRecords":{
					"CenRouteMapRecord":[
						{
							"RouteMapId":"cenrmap-4lcjxzo2zyqjd3****",
							"RegionId":"cn-hangzhou"
						}
					]
				},
				"AsPaths":{
					"AsPath":[]
				},
				"Communities":{
					"Community":[]
				},
				"Type":"CEN",
				"NextHopType":"VBR",
				"NextHopRegionId":"cn-hangzhou",
				"RouteTableId":"vtb-bp1r9pvl4xen8s9ju****",
				"DestinationCidrBlock":"192.168.2.0/24",
				"Conflicts":{
					"Conflict":[]
				}
			}
		]
	}
}
```

## Errors { .section}

