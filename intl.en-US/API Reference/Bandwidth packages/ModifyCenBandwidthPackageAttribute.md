# ModifyCenBandwidthPackageAttribute {#doc_api_Cbn_ModifyCenBandwidthPackageAttribute .reference}

Modifies the name and description of a bandwidth package.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=ModifyCenBandwidthPackageAttribute&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenBandwidthPackageId|String|Yes|cenbwp-4c2zaavbvh5fx\*\*\*\*|The ID of the bandwidth package.

 |
|Action|String|No|ModifyCenBandwidthPackageAttribute|Optional. The name of this action. Value: **ModifyCenBandwidthPackageAttribute**

 |
|Description|String|No|Bandwidth packages|Optional. The description of the bandwidth package. The description must be 2 to 256 characters in length. It must start with a letter or a Chinese character, and cannot start with `http://` or `https://`.

 |
|Name|String|No|test|Optional. The name of the bandwidth package. The name must be 2 to 128 characters in length and can contain letters, numbers, periods \(.\), underscores \(\_\), and hyphens \(-\). The name must start with a letter or a Chinese character. It cannot start with `http://` or `https://`.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|13526224-5780-4426-8ADF-BC8B08700F23|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=ModifyCenBandwidthPackageAttribute
&CenBandwidthPackageId=cenbwp-4c2zaavbvh5fx****
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<ModifyCenBandwidthPackageAttributeResponse>
       <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
</ModifyCenBandwidthPackageAttributeResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"13526224-5780-4426-8ADF-BC8B08700F23"
}
```

## Errors { .section}

