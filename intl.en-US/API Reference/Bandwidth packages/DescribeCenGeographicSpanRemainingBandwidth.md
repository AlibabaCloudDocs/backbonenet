# DescribeCenGeographicSpanRemainingBandwidth {#doc_api_Cbn_DescribeCenGeographicSpanRemainingBandwidth .reference}

Queries the remaining bandwidth of a specified bandwidth package.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeCenGeographicSpanRemainingBandwidth&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-nh98vzx8gfhlwn\*\*\*\*|The ID of the CEN instance to which the bandwidth package belongs.

 |
|GeographicRegionAId|String|Yes|China|The first area to which the bandwidth package is used to connect. Valid values: **China**|**North-America**|**Asia-Pacific**|**Europe**|**Australia**.

 |
|GeographicRegionBId|String|Yes|North-America|The second area to which the bandwidth package is used to connect. Valid values: **China**|**North-America**|**Asia-Pacific**|**Europe**|**Australia**.

 |
|Action|String|No|DescribeCenGeographicSpanRemainingBandwidth|The name of this action. Value: **DescribeCenGeographicSpanRemainingBandwidth**.

 |
|PageNumber|Integer|No|1|The page number. Default value: **1**.

 |
|PageSize|Integer|No|10|The number of entries per page for a paged query. Maximum value: **50**. Default value: **10**.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RemainingBandwidth|Long|2|The remaining bandwidth of the bandwidth package.

 |
|RequestId|String|E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCenGeographicSpanRemainingBandwidth
&CenId=cen-nh98vzx8gfhlwn****
&GeographicRegionAId=China
&GeographicRegionBId=North-America
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeCenGeographicSpanRemainingBandwidthResponse>
      <RequestId>E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B</RequestId>
      <RemainingBandwidth>2</RemainingBandwidth>
</DescribeCenGeographicSpanRemainingBandwidthResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B",
	"RemainingBandwidth":"2"
}
```

## Errors { .section}

