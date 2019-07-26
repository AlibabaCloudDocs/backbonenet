# ModifyCenBandwidthPackageAttribute {#doc_api_Cbn_ModifyCenBandwidthPackageAttribute .reference}

调用ModifyCenBandwidthPackageAttribute编辑带宽包的名称和描述信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=ModifyCenBandwidthPackageAttribute&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenBandwidthPackageId|String|是|cenbwp-4c2zaavbvh5fx\*\*\*\*|带宽包的ID。

 |
|Action|String|否|ModifyCenBandwidthPackageAttribute|要执行的操作，取值：**ModifyCenBandwidthPackageAttribute**。

 |
|Description|String|否|带宽包|带宽包的描述信息。 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

 |
|Name|String|否|test|带宽包的名称。长度为2~128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-），但不能以`http://`或`https://`开头。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|13526224-5780-4426-8ADF-BC8B08700F23|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyCenBandwidthPackageAttribute
&CenBandwidthPackageId=cenbwp-4c2zaavbvh5fx****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyCenBandwidthPackageAttributeResponse>
       <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
</ModifyCenBandwidthPackageAttributeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"13526224-5780-4426-8ADF-BC8B08700F23"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

