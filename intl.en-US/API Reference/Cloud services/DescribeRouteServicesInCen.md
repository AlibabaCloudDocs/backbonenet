# DescribeRouteServicesInCen {#doc_api_Cbn_DescribeRouteServicesInCen .reference}

Queries the cloud service access settings in a Cloud Enterprise Network \(CEN\) instance.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeRouteServicesInCen&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|AccessRegionId|String|No|cn-beijing|Optional. The region of the network instances that access the cloud services.

 |
|Action|String|No|DescribeRouteServicesInCen|Optional. The name of this action. Value: **DescribeRouteServicesInCen**

 |
|CenId|String|No|cen-7qthudw0ll6jmc\*\*\*\*|Optional. The ID of the CEN instance.

 |
|Host|String|No|100.64.0.0/24|Optional. The domain name or IP address of the cloud service.

 |
|HostRegionId|String|No|cn-hangzhou|Optional. The region of the cloud service.

 |
|HostVpcId|String|No|vpc-bp1t36rn9l53iwbsf\*\*\*\*|Optional. The VPC associated with the cloud service.

 |
|PageNumber|Integer|No|1|Optional. The page number. Default value: **1**

 |
|PageSize|Integer|No|10|Optional. The number of entries per page in the case of a paged query result. Maximum value: **50**. Default value: **10**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|PageNumber|Integer|1|The current page number.

 |
|PageSize|Integer|10|The number of entries per page.

 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|The request ID.

 |
|RouteServiceEntries| | |The details of the cloud service access settings.

 |
|AccessRegionId|String|cn-beijing|The region of the network instances that access the cloud service.

 |
|CenId|String|cen-xxx|The ID of the CEN instance.

 |
|Cidrs| |0.0.0.0 /0|The IP address of the cloud service. If you set an IP address for the **Host** parameter, the value of the **Cidrs** parameter is an IP address. If you set a domain name for the **Host** parameter, the value of Cidrs is the IP address to which the domain name is resolved.

 |
|Host|String|0.0.0.0/0|The domain name or IP address of the cloud service.

 |
|HostRegionId|String|cn-hangzhou|The region of the cloud service.

 |
|Status|String|Active|The status of the cloud service.

 |
|UpdateInterval|String|5|The update interval. Default value: **5**. The value cannot be modified.

 |
|TotalCount|Integer|10|The total number of cloud service entries.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeRouteServicesInCen
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeRouteServicesInCenResponse>
	  <TotalCount>3</TotalCount>
	  <PageNumber>1</PageNumber>
	  <PageSize>10</PageSize>
	  <RouteServiceEntries>
		    <RouteServiceEntry>
			      <Status>Active</Status>
			      <CenId>cen-xxxx</CenId>
			      <Cidrs>
				        <Cidr>11.161.18.0/25</Cidr>
			      </Cidrs>
			      <HostRegionId>cn-hangzhou</HostRegionId>
			      <AccessRegionId>cn-hangzhou</AccessRegionId>
			      <Host>11.161.18.0/25</Host>
		    </RouteServiceEntry>
		    <RouteServiceEntry>
			      <Status>Active</Status>
			      <CenId>cen-xxxx</CenId>
			      <Cidrs>
				        <Cidr>11.161.19.0/25</Cidr>
			      </Cidrs>
			      <HostRegionId>cn-hangzhou</HostRegionId>
			      <AccessRegionId>cn-hangzhou</AccessRegionId>
			      <Host>11.161.19.0/25</Host>
		    </RouteServiceEntry>
		    <RouteServiceEntry>
			      <Status>Active</Status>
			      <CenId>cen-xxxx</CenId>
			      <Cidrs>
				        <Cidr>11.161.20.0/25</Cidr>
			      </Cidrs>
			      <HostRegionId>cn-hangzhou</HostRegionId>
			      <AccessRegionId>cn-hangzhou</AccessRegionId>
			      <Host>11.161.20.0/25</Host>
		    </RouteServiceEntry>
	  </RouteServiceEntries>
</DescribeRouteServicesInCenResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":3,
	"PageSize":10,
	"RouteServiceEntries":{
		"RouteServiceEntry":[
			{
				"Status":"Active",
				"Cidrs":{
					"Cidr":[
						"11.161.18.0/25"
					]
				},
				"Host":"11.161.18.0/25",
				"AccessRegionId":"cn-hangzhou",
				"HostRegionId":"cn-hangzhou",
				"CenId":"cen-xxxx"
			},
			{
				"Status":"Active",
				"Cidrs":{
					"Cidr":[
						"11.161.19.0/25"
					]
				},
				"Host":"11.161.19.0/25",
				"AccessRegionId":"cn-hangzhou",
				"HostRegionId":"cn-hangzhou",
				"CenId":"cen-xxxx"
			},
			{
				"Status":"Active",
				"Cidrs":{
					"Cidr":[
						"11.161.20.0/25"
					]
				},
				"Host":"11.161.20.0/25",
				"AccessRegionId":"cn-hangzhou",
				"HostRegionId":"cn-hangzhou",
				"CenId":"cen-xxxx"
			}
		]
	}
}
```

## Errors { .section}

