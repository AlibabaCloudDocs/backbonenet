# ModifyFlowLogAttribute {#doc_api_Cbn_ModifyFlowLogAttribute .reference}

调用ModifyFlowLogAttribute接口编辑流日志的名称和描述。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=ModifyFlowLogAttribute&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网实例ID。

 |
|FlowLogId|String|是|flowlog-m5evbtbpt\*\*\*\*|流日志ID。

 |
|RegionId|String|是|cn-hangzhou|流日志的所属地域ID。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|Action|String|否|ModifyFlowLogAttribute|要执行的操作，取值：**ModifyFlowLogAttribute**。

 |
|Description|String|否|This is my Flowlog.|流日志描述。长度为2~256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

 |
|FlowLogName|String|否|myFlowlog|流日志名称。长度为2~128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-），但不能以`http://`或`https://`开头。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyFlowLogAttribute
&CenId=cen-7qthudw0ll6jmc****
&FlowLogId=flowlog-m5evbtbpt****
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyFlowLogAttributeResponse>
	  <RequestId>F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1</RequestId>
</ModifyFlowLogAttributeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

