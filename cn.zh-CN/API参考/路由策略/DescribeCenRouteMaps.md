# DescribeCenRouteMaps {#doc_api_Cbn_DescribeCenRouteMaps .reference}

调用DescribeCenRouteMaps接口查询路由策略。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cbn&api=DescribeCenRouteMaps)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网实例ID。

 |
|Action|String|否|DescribeCenRouteMaps|要执行的操作，取值：**DescribeCenRouteMaps**。

 |
|CenRegionId|String|否|cn-beijing|云企业网所在的地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为1。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为50，默认值为10。

 |
|RouteMapId|String|否|cenrmap-abcdedfghij\*\*\*\*|路由策略的ID。

 |
|TransmitDirection|String|否|RegionIn|策略生效方向，取值：

 -   **RegionIn**：流入云企业网节点的方向。
-   **RegionOut**：流出云企业网节点的方向。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页包含的条目数。

 |
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B45|请求ID。

 |
|RouteMaps| | |路由策略信息。

 |
|AsPathMatchMode|String|Include|匹配as-path模式，为match语句，取值：

 -   **Include**：模糊匹配。
-   **Complete**：精确匹配。

 |
|CenId|String|cen-7qthudw0ll6jmc\*\*\*\*|云企业网的ID。

 |
|CenRegionId|String|cn-hangzhou|云企业网所在的地域。

 |
|CidrMatchMode|String|Include|匹配前缀模式，为match语句，取值：

 -   **Include**：模糊匹配。
-   **Complete**：精确匹配。

 |
|CommunityMatchMode|String|Include|匹配community模式，为match语句，取值：

 -   **Include**：模糊匹配。
-   **Complete**：精确匹配。

 |
|CommunityOperateMode|String|Additive|操作community的模式，为action语句，取值：

 -   **Additive**：添加。
-   **Replace**：替换。

 |
|Description|String|abc|路由策略的描述信息。

 |
|DestinationChildInstanceTypes| |VPC,VBR|匹配路由的目的实例类型列表，为match语句，取值：**VPC**|**VBR**|**CCN**。

 |
|DestinationCidrBlocks| |1.1.1.0/10, 2.0.0.0/16|匹配路由的前缀列表，为match语句。

 |
|DestinationInstanceIds| |vpc-a, vpc-b, vbr-a|匹配路由的目的实例ID列表，为match语句。

 |
|DestinationInstanceIdsReverseMatch|Boolean|false|路由传递目的实例ID列表排除匹配模式，取值：

 -   **false**（默认）：路由传递目的实例ID在`DestinationInstanceIds`中时匹配不通过。
-   **true**：路由传递目的实例ID不在`DestinationInstanceIds`中时匹配通过。

 |
|DestinationRouteTableIds| |vtb-a, vtb-b|匹配路由的目的路由表ID列表，为match语句。

 |
|MapResult|String|Permit|策略结果模式，取值：

 -   **Permit**：当被匹配的路由满足节点中的所有match语句，则执行该节点中的执行语句并允许通过被匹配的路由，被匹配的路由不会再继续匹配下一个节点；当被匹配的路由与节点中有任何一个match语句不匹配 ，则被匹配的路由继续匹配下一个节点。
-   **Deny**：当被匹配的路由满足节点中的所有match语句，则拒绝通过被匹配的路由，被匹配的路由不会再继续匹配下一个节点，匹配过程立即结束；当被匹配的路由与节点中有任何一个match语句不匹配 ，则被匹配的路由继续匹配下一个节点。

 |
|MatchAsns| |65501|匹配路由的as-path列表，为match语句。

 |
|MatchCommunitySet| |65501:1,65001:2,60011|匹配community集合，为match语句。

 |
|NextPriority|Integer|33|关联的下一个路由策略节点的优先级，取值：**1**~**100**。

 |
|OperateCommunitySet| |65501:1,65001:2,60011|修改community的属性值，为action语句。

 |
|Preference|Integer|20|修改路由的优先级，为action语句。

 |
|Priority|Integer|22|策略节点的优先级，取值：**1**~**100**。

 |
|RouteMapId|String|cenrmap-abcdedfghij\*\*\*\*|路由策略的ID。

 |
|RouteTypes| |System,Custom,BGP|匹配路由的类型列表，为match语句，取值：

 -   **System**：系统路由。
-   **Custom**：用户路由。
-   **BGP**：BGP路由。

 |
|SourceChildInstanceTypes| |VPC,VBR,CCN|匹配路由的源实例类型列表，为match语句，取值：**VPC**|**VBR**|**CCN**。

 |
|SourceInstanceIds| |vpc-a, vpc-b, vbr-a|匹配路由的源实例ID列表，为match语句。

 |
|SourceInstanceIdsReverseMatch|Boolean|false|路由传递源实例ID列表排除匹配模式，取值：

 -   **false**（默认）：路由传递源实例ID在`SourceInstanceIds`中时匹配不通过。
-   **true**：路由传递源实例ID不在`SourceInstanceIds`中时匹配通过。

 |
|SourceRegionIds| |cn-beijing, cn-hangzhou|匹配路由的源地域ID列表，为match语句。

 |
|SourceRouteTableIds| |vtb-a, vtb-b|匹配路由的源路由表ID列表，为match语句。

 |
|TransmitDirection|String|RegionIn|策略生效方向，取值：

 -   **RegionIn**：流入云企业网节点的方向。
-   **RegionOut**：流出云企业网节点的方向。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenRouteMaps
&CenId=cen-7qthudw0ll6jmc****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenRouteMapsResponse>
  <RouteMaps>
    <RouteMap>
      <Status>Active</Status>
      <CenRegionId>cn-beijing</CenRegionId>
      <RouteMapId>cenrmap-jumdfzmj5sgggl****</RouteMapId>
      <MapResult>Permit</MapResult>
      <TransmitDirection>RegionIn</TransmitDirection>
      <CenId>cen-nh98vzx8gfhlwn****</CenId>
      <Priority>20</Priority>
    </RouteMap>
  </RouteMaps>
  <PageNumber>1</PageNumber>
  <TotalCount>1</TotalCount>
  <PageSize>10</PageSize>
</DescribeCenRouteMapsResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"RouteMaps":{
		"RouteMap":[
			{
				"Status":"Active",
				"RouteMapId":"cenrmap-jumdfzmj5sgggl****",
				"CenRegionId":"cn-beijing",
				"MapResult":"Permit",
				"TransmitDirection":"RegionIn",
				"CenId":"cen-nh98vzx8gfhlwn****",
				"Priority":20
			}
		]
	},
	"TotalCount":1,
	"PageSize":10
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

