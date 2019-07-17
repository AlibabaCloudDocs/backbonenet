# DeleteCenRouteMap {#doc_api_Cbn_DeleteCenRouteMap .reference}

调用DeleteCenRouteMap接口删除路由策略。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cbn&api=DeleteCenRouteMap)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jm\*\*\*\*|云企业网的ID。

 |
|CenRegionId|String|是|cn-hangzhou|云企业网所在的地域。 您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|RouteMapId|String|是|cenrmap-abcdedfghij\*\*\*\*|路由策略的ID。

 |
|Action|String|否|DeleteCenRouteMap|要执行的操作，取值：**DeleteCenRouteMap**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|5903EE99-D542-4E14-BC65-AAC1CB2D3D03|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://cbn.aliyuncs.com/?Action=DeleteCenRouteMap
&CenId=cen-7qthudw0ll6jm****
&CenRegionId=cn-hangzhou
&RouteMapId=cenrmap-abcdedfghij****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteCenRouteMapResponse>
  <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
</DeleteCenRouteMapResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"5903EE99-D542-4E14-BC65-AAC1CB2D3D03"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

