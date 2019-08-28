# DescribeCenRouteMaps {#doc_api_Cbn_DescribeCenRouteMaps .reference}

调用DescribeCenRouteMaps接口查询路由策略。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenRouteMaps&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网实例ID。

 |
|Action|String|否|DescribeCenRouteMaps|要执行的操作，取值：**DescribeCenRouteMaps**。

 |
|CenRegionId|String|否|cn-beijing|云企业网所在的地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|RouteMapId|String|否|cenrmap-abcdedfghij\*\*\*\*|路由策略的ID。

 |
|TransmitDirection|String|否|RegionIn|路由策略应用的方向，取值：

 -   **RegionIn**：路由传入云企业网地域网关的方向。

例如路由从本地域网络实例发布到本地域网关，或其他地域的路由发布到本地域网关。

-   **RegionOut**：路由传出云企业网地域网关的方向。

例如路由从本地域网关发布到本地域下其他网络实例，或发布到其他地域网关。


 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RouteMaps| | |路由策略信息。

 |
|AsPathMatchMode|String|Include|匹配as-path模式，为match语句，取值：

 -   **Include**：模糊匹配，匹配条件中的AS Path与被匹配路由的AS Path有重叠即判定为匹配成功。
-   **Complete**：精确匹配，匹配条件中的AS Path必须与被匹配路由的AS Path一致，才判定为匹配成功。

 |
|CenId|String|cen-7qthudw0ll6jmc\*\*\*\*|云企业网的ID。

 |
|CenRegionId|String|cn-hangzhou|云企业网所在的地域。

 |
|CidrMatchMode|String|Include|匹配前缀模式，为match语句，取值：

 -   **Include**：模糊匹配。匹配条件中的路由前缀包含被匹配路由的路由前缀即判定为匹配成功。

例如：定义1.1.0.0/16的策略可以模糊匹配到1.1.1.0/24的路由。

-   **Complete**：精确匹配。匹配条件中的路由前缀必须与被匹配路由的路由前缀一致，才判定为匹配成功。

例如：定义1.1.0.0/16的策略仅可以精确匹配到1.1.0.0/16的路由。


 |
|CommunityMatchMode|String|Include|匹配community模式，为match语句，取值：

 -   **Include**：模糊匹配，匹配条件中的Community与被匹配路由的Community有重叠即判定为匹配成功。
-   **Complete**：精确匹配，匹配条件中的Community必须与被匹配路由的Community一致，才判定为匹配成功。

 |
|CommunityOperateMode|String|Additive|操作community的模式，为action语句，取值：

 -   **Additive**：添加。
-   **Replace**：替换。

 |
|Description|String|abc|路由策略的描述信息。

 |
|DestinationChildInstanceTypes| |VPC|匹配路由的目的实例类型列表，为match语句，取值：**VPC**|**VBR**|**CCN**。

 目的实例类型仅策略应用方向为出地域网关方向且目的实例类型为本地域下实例类型时有效。

 |
|DestinationCidrBlocks| |1.1.1.0/10|匹配路由的前缀列表，为match语句。

 |
|DestinationInstanceIds| |vpc-a|匹配路由的目的实例ID列表，为match语句。

 目的实例ID列表仅策略应用方向为出地域网关方向且目的实例ID为本地域下实例时有效。

 |
|DestinationInstanceIdsReverseMatch|Boolean|false|路由传递目的实例ID列表排除匹配模式，取值：

 -   **false**（默认）：路由传递目的实例ID在`DestinationInstanceIds`中时，匹配通过。
-   **true**：路由传递目的实例ID不在`DestinationInstanceIds`中时，匹配通过。

 |
|DestinationRouteTableIds| |vtb-a|匹配路由的目的路由表ID列表，为match语句。

 目的路由表仅策略应用方向为出地域网关方向且目的路由表为本地域下路由表时有效。

 |
|MapResult|String|Permit|所有匹配条件通过后的策略行为，取值：

 -   **Permit**：允许通过被匹配的路由。
-   **Deny**：拒绝通过被匹配的路由。

 |
|MatchAsns| |65501|匹配路由的as-path列表，为match语句。

 |
|MatchCommunitySet| |65501:1|匹配community集合，为match语句。

 |
|NextPriority|Integer|33|关联的下一条路由策略的优先级，取值：**1**~**100**。

 -   当未配置关联优先级时，路由策略无关联的下一条路由策略。
-   当关联优先级取值为1时，路由策略关联当前路由策略的下一条路由策略。
-   当关联优先级取值非1时，路由策略关联优先级必须大于当前路由策略的优先级。

 仅**MapResult**取值为**Permit**时，匹配通过的路由才会继续匹配关联的下一条路由策略。

 |
|OperateCommunitySet| |65501:1|修改community的属性值，为action语句。

 |
|Preference|Integer|20|修改路由的优先级，为action语句。

 |
|Priority|Integer|22|路由策略的优先级，取值：**1**~**100**。优先级数字越小，优先级越高。

 |
|RouteMapId|String|cenrmap-abcdedfghij\*\*\*\*|路由策略的ID。

 |
|RouteTypes| |System|匹配路由的类型列表，为match语句，取值：

 -   **System**：系统路由，由系统自动生成的路由。
-   **Custom**：用户路由，由用户手动添加的自定义路由。
-   **BGP**：BGP路由，通告至BGP中的路由。

 |
|SourceChildInstanceTypes| |VPC|匹配路由的源实例类型列表，为match语句，取值：**VPC**|**VBR**|**CCN**。

 |
|SourceInstanceIds| |vpc-a|匹配路由的源实例ID列表，为match语句。

 |
|SourceInstanceIdsReverseMatch|Boolean|false|路由传递源实例ID列表排除匹配模式，取值：

 -   **false**（默认）：路由传递源实例ID在`SourceInstanceIds`中时，匹配通过。
-   **true**：路由传递源实例ID不在`SourceInstanceIds`中时，匹配通过。

 |
|SourceRegionIds| |cn-beijing|匹配路由的源地域ID列表，为match语句。

 |
|SourceRouteTableIds| |vtb-a|匹配路由的源路由表ID列表，为match语句。

 |
|Status|String|Active|路由策略的状态，取值：

 -   **Active**：可用。
-   **Creating**：创建中。

 |
|TransmitDirection|String|RegionIn|路由策略应用的方向，取值：

 -   **RegionIn**：路由传入云企业网地域网关的方向。

例如路由从本地域网络实例发布到本地域网关，或其他地域的路由发布到本地域网关。

-   **RegionOut**：路由传出云企业网地域网关的方向。

例如路由从本地域网关发布到本地域下其他网络实例，或发布到其他地域网关。


 |
|PageSize|Integer|10|每页包含的条目数。

 |
|PageNumber|Integer|1|当前页码。

 |
|TotalCount|Integer|10|列表条目数。

 |
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B45|请求ID。

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

