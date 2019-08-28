# CreateFlowlog {#doc_api_Cbn_CreateFlowlog .reference}

调用CreateFlowlog接口创建流日志。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=CreateFlowlog&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网实例ID。

 |
|LogStoreName|String|是|FlowLogStore|存储捕获到的流量的LogStore。

 |
|ProjectName|String|是|FlowLogProject|存储捕获到的流量的Project。

 |
|RegionId|String|是|cn-hangzhou|流日志的所属地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|Action|String|否|CreateFlowlog|要执行的操作，取值：**CreateFlowLog**。

 |
|ClientToken|String|否|02fb3da4-130e-11e9-8e44-0016e04115b|客户端token，用于保证请求的幂等性。由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII字符。

 |
|Description|String|否|This is my Flowlog.|流日志的描述。长度为2~256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

 |
|FlowLogName|String|否|myFlowlog|流日志名称。长度为2~128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-），但不能以`http://`或`https://`开头。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|FlowLogId|String|flowlog-m5evbtbpt\*\*\*\*|流日志ID。

 |
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B457|请求ID。

 |
|Success|String|true|操作是否成功，取值：

 -   **true**：操作成功。
-   **false**：操作未成功。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateFlowlog
&CenId=cen-7qthudw0ll6jmc****
&LogStoreName=FlowLogStore
&ProjectName=FlowLogProject
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateFlowlogResponse>
   	  <RequestId>3D6F9FD4-AE3E-416D-950F-FC3696E27977</RequestId>
	  <FlowLogId>flowlog-kklh24tcz044ne****</FlowLogId>
	  <Success>true</Success>
</CreateFlowlogResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"3D6F9FD4-AE3E-416D-950F-FC3696E27977",
	"FlowLogId":"flowlog-kklh24tcz044ne****",
	"Success":true
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

