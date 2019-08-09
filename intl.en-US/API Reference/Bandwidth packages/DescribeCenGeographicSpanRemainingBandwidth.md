# DescribeCenGeographicSpanRemainingBandwidth {#doc_api_Cbn_DescribeCenGeographicSpanRemainingBandwidth .reference}

Queries the remaining available bandwidth of a bandwidth package.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeCenGeographicSpanRemainingBandwidth&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-nh98vzx8gfhlwn\*\*\*\*| The ID of the CEN instance to which the bandwidth package belongs.

 |
|GeographicRegionAId|String|Yes|China| One area connected through the bandwidth package. Valid values: **China** | **North-America** | **Asia-Pacific** | **Europe** | **Middle-East**

 |
|GeographicRegionBId|String|Yes|North-America| The other area connected through the bandwidth package. Valid values: **China** | **North-America** | **Asia-Pacific** | **Europe** | **Middle-East**

 |
|Action|String|No|DescribeCenGeographicSpanRemainingBandwidth| Optional. The name of this action. Value: **DescribeCenGeographicSpanRemainingBandwidth**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RemainingBandwidth|Long|2| The remaining bandwidth of the bandwidth package.

 |
|RequestId|String|E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B| The ID of the request.

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

Response examples

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

## Errors {#section_rwg_3ix_ssu .section}

