# DescribeFlowlogs {#doc_api_Cbn_DescribeFlowlogs .reference}

调用DescribeFlowlogs接口查询流日志。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeFlowlogs&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeFlowlogs|要执行的操作，取值：**DescribeFlowlogs**。

 |
|CenId|String|否|cen-7qthudw0ll6jmc\*\*\*\*|云企业网实例ID。

 |
|ClientToken|String|否|02fb3da4-130e-11e9-8e44-0016e04115b|客户端token，用于保证请求的幂等性。由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII字符。

 |
|Description|String|否|This is my Flowlog.|流日志描述。长度为2~256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

 |
|FlowLogId|String|否|flowlog-m5evbtbpt\*\*\*\*|流日志ID。

 |
|FlowLogName|String|否|myFlowlog|流日志名称。

 |
|LogStoreName|String|否|LogStore|存储捕获流量的LogStore。

 |
|PageNumber|Integer|否|1|当前页码。

 |
|PageSize|Integer|否|10|每页包含的条目数。

 |
|ProjectName|String|否|Project|存储捕获流量的Project。

 |
|RegionId|String|否|cn-hangzhou|流日志的所属地域ID。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|Status|String|否|Active|流日志的状态，取值：

 -   **Active**：已启动。
-   **InActive**：未启动。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|FlowLogs| | |流日志的详细信息。

 |
|CenId|String|cen-7qthudw0ll6jmc\*\*\*\*|云企业网实例ID。

 |
|CreationTime|String|2018-07-24T13:00:52Z|创建时间。

 |
|Description|String|abc|流日志的描述信息。

 |
|FlowLogId|String|flowlog-m5evbtbpt\*\*\*\*|流日志ID。

 |
|FlowLogName|String|myFlowlog|流日志名称。

 |
|LogStoreName|String|FlowLogStore|存储捕获到的流量的LogStore。

 |
|ProjectName|String|FlowLogProject|存储捕获到的流量的Project。

 |
|RegionId|String|cn-hangzhou|地域。

 |
|Status|String|Active|流日志的状态，取值：

 -   **Active**：已启动。
-   **InActive**：未启动。

 |
|PageNumber|String|1|当前页码。

 |
|PageSize|String|10|每页包含的条目数。

 |
|RequestId|String|F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1|请求ID。

 |
|Success|String|true|操作是否成功，取值：

 -   **true**：操作成功。
-   **false**：操作未成功。

 |
|TotalCount|String|3|列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeFlowlogs
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeFlowlogsResponse>
      <RequestId>04F0F334-1335-436C-A1D7-6C044FExxxxx</RequestId>
</DescribeFlowlogsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FExxxxx"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cbn)查看更多错误码。

