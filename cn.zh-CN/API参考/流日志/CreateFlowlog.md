# CreateFlowlog {#doc_api_Cbn_CreateFlowlog .reference}

调用CreateFlowlog接口创建流日志。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cbn&api=CreateFlowlog)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmcxxxx|云企业网实例ID。

 |
|LogStoreName|String|是|FlowLogStore|存储捕获到的流量的LogStore。

 |
|ProjectName|String|是|FlowLogProject|存储捕获到的流量的Project。

 |
|RegionId|String|是|cn-hangzhou|流日志的所属地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|Action|String|否|CreateFlowlog|要执行的操作，取值：**CreateFlowLog**。

 |
|Description|String|否|This is my Flowlog.|流日志的描述。长度为2-256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

 |
|FlowLogName|String|否|myFlowlog|流日志名称。长度为2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-），但不能以`http://`或`https://`开头。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|FlowLogId|String|flowlog-m5evbtbptxxxx|流日志ID。

 |
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B457|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateFlowlog
&CenId=cen-7qthudw0ll6jmcxxxx
&LogStoreName=FlowLogStore
&ProjectName=FlowLogProject
&RegionId=cn-qingdao
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateFlowlogResponse>
  <RequestId>62172DD5-6BAC-45DF-8D44-xxxxxxxx</RequestId>
  <FlowLogId>flowlog-m5evbtbptxxxxxxxxxxxx</FlowLogId>
</CreateFlowlogResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"62172DD5-6BAC-45DF-8D44-xxxxxxxx",
	"FlowLogId":"flowlog-m5evbtbptxxxx"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cbn)

