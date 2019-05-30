# DescribeRouteConflict {#doc_api_1064632 .reference}

调用DescribeRouteConflict查看指定路由器（VRouter或VBR）中存在冲突的路由条目。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cbn&api=DescribeRouteConflict)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ChildInstanceId|String|是|vpc-bp18sth14qii3pnxxxxx|网络实例的ID。

 |
|ChildInstanceRegionId|String|是|cn-hangzhou|指定地域的ID。

 |
|ChildInstanceRouteTableId|String|是|vtb-bp174d1gje79u1g4txxxx|路由表的ID。

 |
|ChildInstanceType|String|是|VBR|指定路由器类型，包括VRouter和VBR。

 |
|Action|String|否|DescribeRouteConflict|要执行的操作。

 取值： **DescribeRouteConflict**

 |
|DestinationCidrBlock|String|否|172.16.xx.xx/24|目标网段的CIDR地址块。

 |
|PageNumber|Integer|否|1|当前页码。

 |
|PageSize|Integer|否|2|每页包含多少条目。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|1|每页包含多少条目。

 |
|RequestId|String|B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0|请求ID。

 |
|RouteConflicts| | |冲突路由条目的详细信息。

 |
|└DestinationCidrBlock|String|172.16.xx.xx/24|路由条目的目标网段。

 |
|└InstanceId|String|vbr-bp174d1gje79u1xxxxx|路由器的ID。

 |
|└InstanceType|String|VBR|路由器的类型，VRouter或VBR。

 |
|└RegionId|String|cn-hangzhou|地域的ID。

 |
|└Status|String|conflict|产生路由异常的原因：

 -   conflict：路由冲突。
-   overflow：其他网络实例路由表路由数量超出限制。
-   prohibited：VBR策略不允许的默认路由。

 |
|TotalCount|Integer|2|列表条条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://cbn.aliyuncs.com/?Action=DescribeRouteConflict
&ChildInstanceId=vpc-wz9fldmuq4v3g8gyp1qqy
&ChildInstanceType=VPC
&ChildInstanceRegionId=cn-shenzhen
&ChildInstanceRouteTableId=vrt-wz93gtdvt87w7cpff071n
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeRouteConflictResponse>
  <PageNumber>1</PageNumber>
  <PageSize>10</PageSize>
  <RequestId>B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0</RequestId>
  <RouteConflicts>
    <RouteConflict/>
  </RouteConflicts>
  <TotalCount>0</TotalCount>
</DescribeRouteConflictResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":0,
	"PageSize":10,
	"RequestId":"B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0",
	"RouteConflicts":{
		"RouteConflict":[]
	}
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cbn)

