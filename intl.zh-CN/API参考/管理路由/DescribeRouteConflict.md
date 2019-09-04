# DescribeRouteConflict {#doc_api_Cbn_DescribeRouteConflict .reference}

调用DescribeRouteConflict查看指定路由器（VRouter或VBR）中存在冲突的路由条目。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeRouteConflict&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ChildInstanceId|String|是|vpc-bp18sth14qii3pn\*\*\*\*|网络实例的ID。

 |
|ChildInstanceRegionId|String|是|cn-hangzhou|指定地域的ID。

 |
|ChildInstanceRouteTableId|String|是|vtb-bp174d1gje79u1g4t\*\*\*\*|路由表的ID。

 |
|ChildInstanceType|String|是|VBR|指定路由器类型，取值：

 -   **VRouter**：虚拟路由器。
-   **VBR**：边界路由器。

 |
|Action|String|否|DescribeRouteConflict|要执行的操作，取值：**DescribeRouteConflict**。

 |
|DestinationCidrBlock|String|否|172.16.xx.xx/24|目标网段的CIDR地址块。

 |
|PageNumber|Integer|否|1|当前页码。

 |
|PageSize|Integer|否|2|每页包含的条目数。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|1|每页包含的条目数。

 |
|RequestId|String|B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0|请求ID。

 |
|RouteConflicts| | |冲突路由条目的详细信息。

 |
|DestinationCidrBlock|String|172.16.xx.xx/24|路由条目的目标网段。

 |
|InstanceId|String|vbr-bp174d1gje79u1\*\*\*\*|路由器的ID。

 |
|InstanceType|String|VBR|路由器的类型，取值：

 -   **VRouter**：虚拟路由器。
-   **VBR**：边界路由器。

 |
|RegionId|String|cn-hangzhou|地域的ID。

 |
|Status|String|conflict|产生路由异常的原因： 取值：

 -   **conflict**：路由冲突。
-   **overflow**：其他网络实例路由表路由数量超出限制。
-   **prohibited**：VBR策略不允许的默认路由。

 |
|TotalCount|Integer|2|列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeRouteConflict
&ChildInstanceId=vpc-bp18sth14qii3pn****
&ChildInstanceRegionId=cn-hangzhou
&ChildInstanceRouteTableId=vtb-bp174d1gje79u1g4t****
&ChildInstanceType=VBR
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeRouteConflictResponse>
      <PageNumber>1</PageNumber>
      <PageSize>10</PageSize>
      <RequestId>B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0</RequestId>
      <RouteConflicts>
            <RouteConflict></RouteConflict>
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

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cbn)查看更多错误码。

