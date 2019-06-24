# DeleteFlowlog {#doc_api_Cbn_DeleteFlowlog .reference}

调用DeleteFlowlog接口删除流日志。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cbn&api=DeleteFlowlog)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmcxxxx|云企业网ID。

 |
|FlowLogId|String|是|flowlog-m5evbtbptxxxx|流日志ID。

 |
|RegionId|String|是|cn-hangzhou|流日志的所属地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|Action|String|否|DeleteFlowlog|要执行的操作，取值：**DeleteFlowlog**。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteFlowlog
&CenId=cen-7qthudw0ll6jmcxxxx
&FlowLogId=flowlog-m5evbtbptxxxx
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteFlowLogResponse>
  <RequestId>04F0F334-1335-436C-A1D7-6C044FExxxxx</RequestId>
</DeleteFlowLogResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FExxxxx"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cbn)

