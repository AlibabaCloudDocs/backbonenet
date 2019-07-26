# ModifyCenBandwidthPackageSpec {#doc_api_Cbn_ModifyCenBandwidthPackageSpec .reference}

调用ModifyCenBandwidthPackageSpec更改带宽包的带宽值。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=ModifyCenBandwidthPackageSpec&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Bandwidth|Integer|是|2|带宽包的带宽峰值，单位为Mbps，最小为**2**。

 |
|CenBandwidthPackageId|String|是|cenbwp-4c2zaavbvh5x\*\*\*\*|带宽包的ID。

 |
|Action|String|否|ModifyCenBandwidthPackageSpec|要执行的操作，取值：**ModifyCenBandwidthPackageSpec**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyCenBandwidthPackageSpec
&Bandwidth=2
&CenBandwidthPackageId=cenbwp-4c2zaavbvh5x****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyCenBandwidthPackageSpecResponse>
       <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
</ModifyCenBandwidthPackageSpecResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

