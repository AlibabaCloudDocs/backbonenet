# AssociateCenBandwidthPackage {#doc_api_Cbn_AssociateCenBandwidthPackage .reference}

调用AssociateCenBandwidthPackage将带宽包绑定到指定的云企业网实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=AssociateCenBandwidthPackage&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenBandwidthPackageId|String|是|cenbwp-4c2zaavbvh5fx\*\*\*\*|带宽包的ID。

 |
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网实例的ID。

 |
|Action|String|否|AssociateCenBandwidthPackage|要执行的操作，取值：**AssociateCenBandwidthPackage**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=AssociateCenBandwidthPackage
&CenBandwidthPackageId=cenbwp-4c2zaavbvh5fx****
&CenId=cen-7qthudw0ll6jmc****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AssociateCenBandwidthPackageResponse>
      <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
</AssociateCenBandwidthPackageResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cbn)查看更多错误码。

