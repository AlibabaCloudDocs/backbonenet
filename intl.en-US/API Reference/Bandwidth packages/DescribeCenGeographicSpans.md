# DescribeCenGeographicSpans {#doc_api_Cbn_DescribeCenGeographicSpans .reference}

Queries the connected areas.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeCenGeographicSpans&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|DescribeCenGeographicSpans|Optional. The name of this action. Value: **DescribeCenGeographicSpans**

 |
|GeographicSpanId|String|No|china-china|Optional. The connected areas.

 |
|PageNumber|Integer|No|1|Optional. The page number. Default value: **1**

 |
|PageSize|Integer|No|10|Optional. The number of entries per page. Maximum value: **50**. Default value: **10**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|GeographicSpanModels| | |The details of the connected areas.

 |
|GeographicSpanId|String|china-china|The connected areas.

 |
|LocalGeoRegionId|String|china|One of the two connected areas.

 |
|OppositeGeoRegionId|String|china|The other area.

 |
|PageNumber|Integer|1|The current page number.

 |
|PageSize|Integer|12|The number of entries per page.

 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|The request ID.

 |
|TotalCount|Integer|20|The total number of area connections.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCenGeographicSpans
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeCenGeographicSpansResponse>
	  <PageNumber>1</PageNumber>
	  <TotalCount>1</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>09780287-BC24-4164-8334-773432E32696</RequestId>
	  <GeographicSpanModels>
		    <GeographicSpanModel>
			      <OppositeGeoRegionId>china</OppositeGeoRegionId>
			      <LocalGeoRegionId>asia-pacific</LocalGeoRegionId>
			      <GeographicSpanId>china_asia-pacific</GeographicSpanId>
		    </GeographicSpanModel>
	  </GeographicSpanModels>
</DescribeCenGeographicSpansResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"09780287-BC24-4164-8334-773432E32696",
	"GeographicSpanModels":{
		"GeographicSpanModel":[
			{
				"OppositeGeoRegionId":"china",
				"GeographicSpanId":"china_asia-pacific",
				"LocalGeoRegionId":"asia-pacific"
			}
		]
	}
}
```

## Errors { .section}

