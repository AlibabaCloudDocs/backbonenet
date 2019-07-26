# SetCenInterRegionBandwidthLimit {#doc_api_Cbn_SetCenInterRegionBandwidthLimit .reference}

调用SetCenInterRegionBandwidthLimit设置带宽包中两个地域间的跨地域互通带宽。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=SetCenInterRegionBandwidthLimit&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|BandwidthLimit|Long|是|8|两个地域之间的跨地域互通带宽。

 |
|CenId|String|是|cen-7qthudw0ll6jmx\*\*\*\*|云企业网实例的ID。

 |
|LocalRegionId|String|是|cn-hangzhou|本端地域的ID。

 |
|OppositeRegionId|String|是|us-west-1|对端地域的ID。

 |
|Action|String|否|SetCenInterRegionBandwidthLimit|要执行的操作，取值：**SetCenInterRegionBandwidthLimit**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|530BC816-F575-412A-AAB2-435125D26328|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=SetCenInterRegionBandwidthLimit
&BandwidthLimit=8
&CenId=cen-7qthudw0ll6jmx****
&LocalRegionId=cn-hangzhou
&OppositeRegionId=us-west-1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetCenInterRegionBandwidthLimitResponse>
     <RequestId>530BC816-F575-412A-AAB2-435125D26328</RequestId>
</SetCenInterRegionBandwidthLimitResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"530BC816-F575-412A-AAB2-435125D26328"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

