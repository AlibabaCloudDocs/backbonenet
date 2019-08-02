# AssociateCenBandwidthPackage {#doc_api_Cbn_AssociateCenBandwidthPackage .reference}

Associates a bandwidth package with a CEN instance.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=AssociateCenBandwidthPackage&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenBandwidthPackageId|String |Yes|Cenbwp-4c2zaavbvh5fx \*\*\*\*|The ID of the bandwidth package.

 |
|CenId|String |Yes|cen-7qthudw0ll6jmc\*\*\*\*|The ID of the CEN instance.

 |
|Action|String|No|AssociateCenBandwidthPackage|Optional. The name of this action. Value: **AssociateCenBandwidthPackage**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=AssociateCenBandwidthPackage
&CenBandwidthPackageId=cenbwp-4c2zaavbvh5fx****
&CenId=cen-7qthudw0ll6jmc****
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<AssociateCenBandwidthPackageResponse>
      <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
</AssociateCenBandwidthPackageResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
}
```

## Errors { .section}

