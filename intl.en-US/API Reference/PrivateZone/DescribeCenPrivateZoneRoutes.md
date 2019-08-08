# DescribeCenPrivateZoneRoutes {#doc_api_Cbn_DescribeCenPrivateZoneRoutes .reference}

Queries the details of the PrivateZone service.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeCenPrivateZoneRoutes&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-7qthudw0ll6jmc\*\*\*\*| The ID of the CEN instance.

 |
|AccessRegionId|String|No|cn-hangzhou| Optional. The access region.

 The access region is the region of the cloud resource that accesses the PrivateZone service through CEN.

 |
|Action|String|No|DescribeCenPrivateZoneRoutes| Optional. The name of this action. Value: **DescribeCenPrivateZoneRoutes**

 |
|HostRegionId|String|No|cn-hangzhou| Optional. The service region.

 The service region is the target region of the PrivateZone service accessed through CEN.

 |
|PageNumber|Integer|No|10| Optional. The page number. Default value: **1**

 |
|PageSize|Integer|No|10| Optional. The number of entries per page in the case of a paged query result. Maximum value: **50**. Default value: **10**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|CenId|String|cen-7qthudw0ll6jmc\*\*\*\*| The ID of the CEN instance.

 |
|PageNumber|Integer|10| The current page number.

 |
|PageSize|Integer|10| The number of entries per page.

 |
|PrivateZoneDnsServers|String|100.100.xx.136/32,100.100.xx.138/32| The DNS IP addresses of the PrivateZone service.

 |
|PrivateZoneInfos| | | The details of the PrivateZone service.

 |
|AccessRegionId|String|cn-hangzhou| The access region.

 The access region is the region of the cloud resource that accesses the PrivateZone service through CEN.

 |
|HostRegionId|String|cn-hangzhou| The service region.

 The service region is the target region of the PrivateZone service accessed through CEN.

 |
|HostVpcId|String|vpc-bp18sth14qii3pnvo\*\*\*\*| The VPC that belongs to the service region.

 |
|Status|String|Active| The status of the PrivateZone service.

 |
|RequestId|String|C0245BEF-52AC-44A8-A776-EF96FD26A5CA| The ID of the request.

 |
|TotalCount|Integer|10| The total number of queried entries.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCenPrivateZoneRoutes
&CenId=cen-7qthudw0ll6jmc****	
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeCenPrivateZoneRoutesResponse>
	  <PrivateZoneInfos>
		    <PrivateZoneInfo>
			      <Status>Active</Status>
			      <HostVpcId>vpc-bp18sth14qii3pnvo****</HostVpcId>
			      <AccessRegionId>ccn-cn-shanghai</AccessRegionId>
			      <HostRegionId>cn-hangzhou</HostRegionId>
		    </PrivateZoneInfo>
		    <PrivateZoneInfo>
			      <Status>Active</Status>
			      <HostVpcId>vpc-bp18sth14qii3pnvo****</HostVpcId>
			      <AccessRegionId>cn-hangzhou</AccessRegionId>
			      <HostRegionId>cn-hangzhou</HostRegionId>
		    </PrivateZoneInfo>
	  </PrivateZoneInfos>
	  <PageNumber>1</PageNumber>
	  <TotalCount>2</TotalCount>
	  <PageSize>10</PageSize>
	  <PrivateZoneDnsServers>100.100.xx.136/32,100.100.xx.138/32</PrivateZoneDnsServers>
	  <RequestId>461EC1B5-04A8-4706-8764-8F5BCEF48A6F</RequestId>
</DescribeCenPrivateZoneRoutesResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"PrivateZoneInfos":{
		"PrivateZoneInfo":[
			{
				"Status":"Active",
				"HostVpcId":"vpc-bp18sth14qii3pnvo****",
				"AccessRegionId":"ccn-cn-shanghai",
				"HostRegionId":"cn-hangzhou"
			},
			{
				"Status":"Active",
				"HostVpcId":"vpc-bp18sth14qii3pnvo****",
				"AccessRegionId":"cn-hangzhou",
				"HostRegionId":"cn-hangzhou"
			}
		]
	},
	"PageNumber":1,
	"TotalCount":2,
	"PrivateZoneDnsServers":"100.100.xx.136/32,100.100.xx.138/32",
	"PageSize":10,
	"RequestId":"461EC1B5-04A8-4706-8764-8F5BCEF48A6F"
}
```

## Errors {#section_ngk_zhn_1wt .section}

