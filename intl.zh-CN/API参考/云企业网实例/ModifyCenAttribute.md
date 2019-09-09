# ModifyCenAttribute {#doc_api_Cbn_ModifyCenAttribute .reference}

调用ModifyCenAttribute编辑云企业网实例的名称和描述信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=ModifyCenAttribute&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网实例的ID。

 |
|Action|String|否|ModifyCenAttribute|要执行的操作，取值：**ModifyCenAttribute**。

 |
|Description|String|否|cen|云企业网实例的描述信息。长度为2~256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

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
|RequestId|String|455AC20C-7061-446A-BDBD-B3BEE0856304|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyCenAttribute
&CenId=cen-7qthudw0ll6jmc****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyCenAttributeResponse>
       <RequestId>13526224-5780-4426-8BDF-BC8B08700F22</RequestId>
</ModifyCenAttributeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"13526224-5780-4426-8BDF-BC8B08700F22"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidOperation.EnhanceProtectionLevel|Your request to enhance CBN protection level cannot be processed. Please contact customer support to continue this operation.|增强CBN的保护级别的操作不能处理，如果您强烈需要执行此操作，请联系客户支持服务。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cbn)查看更多错误码。

