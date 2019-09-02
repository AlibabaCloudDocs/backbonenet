# DescribeChildInstanceRegions {#doc_api_Cbn_DescribeChildInstanceRegions .reference}

Queries the regions of the network instances of the same network type.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeChildInstanceRegions&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|DescribeChildInstanceRegions|Optional. The name of this action. Value: **DescribeChildInstanceRegions**

 |
|ProductType|String|No|VPC|Optional. The type of the network instances. Valid values:

 -   **VPC**: Virtual Private Cloud
-   **VBR**: Virtual Border Router
-   **CCN**: Cloud Connect Network

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|Regions| | |The details of the region.

 |
|LocalName|String|China \(Hangzhou\)|The name of the region.

 |
|RegionId|String|cn-hangzhou|The ID of the region.

 |
|RequestId|String|A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeChildInstanceRegions
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeChildInstanceRegionsResponse>
	  <RequestId>D5CEED59-36AA-47CC-9D81-16F71C46BD80</RequestId>
	  <Regions>
		    <Region>
			      <RegionId>cccn-hangzhou</RegionId>
			      <LocalName>China (Hangzhou)</LocalName>
		    </Region>
	  </Regions>
</DescribeChildInstanceRegionsResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"D5CEED59-36AA-47CC-9D81-16F71C46BD80",
	"Regions":{
		"Region":[
			{
				"RegionId":"cn-hangzhou",
				"LocalName":"China (Hangzhou)"
			}
		]
	}
}
```

## Errors { .section}

