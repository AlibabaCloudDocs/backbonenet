# DescribeCenAttachedChildInstances {#doc_api_Cbn_DescribeCenAttachedChildInstances .reference}

Queries the networks associated with a CEN instance.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeCenAttachedChildInstances&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-7qthudw0ll6jmcx\*\*\*\*| The ID of the CEN instance.

 |
|Action|String|No|DescribeCenAttachedChildInstances| Optional. The name of this action. Value: **DescribeCenAttachedChildInstances**

 |
|ChildInstanceRegionId|String|No|us-west-1| Optional. The region to which the network to be queried belongs.

 |
|ChildInstanceType|String|No|VPC| Optional. The type of the associated network. Valid values:

 -   **VPC**
-   **VBR**
-   **CCN**

 |
|PageNumber|Integer|No|1| Optional. The page number. Default value: **1**

 |
|PageSize|Integer|No|10| Optional. The number of entries per page in the case of a paged query result. Maximum value: **50**. Default value: **10**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|ChildInstances| | | A list of networks associated with the CEN instance.

 |
|CenId|String|cen-7qthudw0ll6jmx\*\*\*\*| The ID of the CEN instance.

 |
|ChildInstanceAttachTime|String|2018-10-16T08:47Z| The time when the network is associated with the CEN instance.

 |
|ChildInstanceId|String|vpc-m5ex5mr548eb5f6\*\*\*\*| The ID of the network.

 |
|ChildInstanceOwnerId|Long|123456789| The ID of the account to which the network belongs.

 |
|ChildInstanceRegionId|String|cn-qingdao| The ID of the region to which the network belongs.

 |
|ChildInstanceType|String|VPC| The type of the network. Valid values:

 -   **VPC**
-   **VBR**
-   **CCN**

 |
|Status|String|attaching| The status of the network. Valid values:

 -   **attaching**: The network is being associated.
-   **attached**: The network is already associated with the CEN instance.
-   **detaching**: The network is being disassociated from the CEN instance.

 |
|PageNumber|Integer|1| The current page number.

 |
|PageSize|Integer|12| The number of entries per page.

 |
|RequestId|String|CDE065A6-D24D-4CE9-A45D-3BBD45B22311| The ID of the request.

 |
|TotalCount|Integer|1| The total number of queried entries.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCenAttachedChildInstances
&CenId=cen-7qthudw0ll6jmcx****
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeCenAttachedChildInstancesResponse>
	  <PageNumber>1</PageNumber>
	  <ChildInstances>
		    <ChildInstance>
			      <Status>Attached</Status>
			      <ChildInstanceOwnerId>123456789</ChildInstanceOwnerId>
			      <ChildInstanceId>vpc-hp3kz27b1uv9hsmm9****</ChildInstanceId>
			      <ChildInstanceRegionId>cn-huhehaote</ChildInstanceRegionId>
			      <CenId>cen-kojok19x3j0q6k****</CenId>
			      <ChildInstanceType>VPC</ChildInstanceType>
		    </ChildInstance>
		    <ChildInstance>
			      <Status>Attached</Status>
			      <ChildInstanceOwnerId>123456789</ChildInstanceOwnerId>
			      <ChildInstanceId>vpc-gw85r5kr8urw957sz****</ChildInstanceId>
			      <ChildInstanceRegionId>eu-central-1</ChildInstanceRegionId>
			      <CenId>cen-kojok19x3j0q6k****</CenId>
			      <ChildInstanceType>VPC</ChildInstanceType>
		    </ChildInstance>
	  </ChildInstances>
	  <TotalCount>3</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>50F8E0AB-A225-41C0-AC88-FFB51A4F5C72</RequestId>
</DescribeCenAttachedChildInstancesResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"ChildInstances":{
		"ChildInstance":[
			{
				"Status":"Attached",
				"ChildInstanceOwnerId":"123456789",
				"ChildInstanceId":"vpc-hp3kz27b1uv9hsmm9****",
				"ChildInstanceRegionId":"cn-huhehaote",
				"CenId":"cen-kojok19x3j0q6k****",
				"ChildInstanceType":"VPC"
			},
			{
				"Status":"Attached",
				"ChildInstanceOwnerId":"123456789",
				"ChildInstanceId":"vpc-gw85r5kr8urw957sz****",
				"ChildInstanceRegionId":"eu-central-1",
				"CenId":"cen-kojok19x3j0q6k****",
				"ChildInstanceType":"VPC"
			}
		]
	},
	"TotalCount":3,
	"PageSize":10,
	"RequestId":"50F8E0AB-A225-41C0-AC88-FFB51A4F5C72"
}
```

## Errors {#section_mt7_cgg_70t .section}

