# ActiveFlowLog {#doc_api_Cbn_ActiveFlowLog .reference}

调用ActiveFlowLog接口启动流日志，启动后开始捕获指定资源的流量。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=ActiveFlowLog&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网实例ID。

 |
|FlowLogId|String|是|flowlog-m5evbtbpt\*\*\*\*|流日志ID。

 |
|RegionId|String|是|cn-hangzhou|流日志的所属地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|Action|String|否|ActiveFlowLog|要执行的操作，取值：**ActiveFlowLog**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ActiveFlowLog
&CenId=cen-7qthudw0ll6jmc****
&FlowLogId=flowlog-m5evbtbpt****
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ActiveFlowLogResponse>   
     <RequestId>F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1</RequestId>
</ActiveFlowLogResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

