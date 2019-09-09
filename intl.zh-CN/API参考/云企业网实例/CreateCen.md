# CreateCen {#doc_api_Cbn_CreateCen .reference}

调用CreateCen接口创建云企业网实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=CreateCen&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|CreateCen|要执行的操作，取值：**CreateCen**。

 |
|ClientToken|String|否|123e4567-e89b-12d3-a456-426655440000|客户端token，用于保证请求的幂等性。由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII 字符。

 |
|Description|String|否|云企业网|云企业网实例的描述信息。长度为2~256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

 |
|Name|String|否|test|云企业网实例的名称。长度为2~128个字符，必须以字母或中文开头，可包含数字、点号（.）、下划线（\_）和短横线（-），但不能以`http://`或`https://`开头。

 |
|ProtectionLevel|String|否|FULL|设置网段重叠冲突的级别，取值：

 -   **FULL**：不能有网段重叠。
-   **REDUCE**：可以有网段重叠，但是不能完全相等。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CenId|String|cen-7qthudw0ll6jmc\*\*\*\*|新创建的云企业网实例的ID。

 |
|RequestId|String|455AC20C-7061-446A-BDBD-B3BEE0856304|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateCen
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateCenResponse>
       <CenId> Cen-dc4vwznpwbobrl**** </CenId>
       <RequestId>0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50</RequestId>
</CreateCenResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50",
	"CenId":"Cen-dc4vwznpwbobrl****"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cbn)查看更多错误码。

