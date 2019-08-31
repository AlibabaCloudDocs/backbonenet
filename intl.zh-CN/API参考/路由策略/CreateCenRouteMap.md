# CreateCenRouteMap {#doc_api_Cbn_CreateCenRouteMap .reference}

调用CreateCenRouteMap接口创建路由策略。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=CreateCenRouteMap&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网的ID。

 |
|CenRegionId|String|是|cn-hangzhou|云企业网所在的地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|Priority|Integer|是|3|路由策略的优先级，取值：**1**~**100**。优先级数字越小，优先级越高。

 **说明：** 同地域同策略应用方向的路由策略优先级唯一。执行路由策略时，系统从优先级数字最小的路由策略开始匹配条件语句，因此在指定路由策略优先级时，要注意符合期望的匹配顺序。

 |
|TransmitDirection|String|是|RegionIn|路由策略应用的方向，取值：

 -   **RegionIn**：路由传入云企业网地域网关的方向。

例如路由从本地域网络实例发布到本地域网关，或其他地域的路由发布到本地域网关。

-   **RegionOut**：路由传出云企业网地域网关的方向。

例如路由从本地域网关发布到本地域下其他网络实例，或发布到其他地域网关。


 |
|MapResult|String|是|Permit|所有匹配条件通过后的策略行为，取值：

 -   **Permit**：允许通过被匹配的路由。
-   **Deny**：拒绝通过被匹配的路由。

 |
|Action|String|否|CreateCenRouteMap|要执行的操作，取值：**CreateCenRouteMap**。

 |
|NextPriority|Integer|否|20|关联的下一条路由策略的优先级，取值：**1**~**100**。

 -   当未配置关联优先级时，路由策略无关联的下一条路由策略。
-   当关联优先级取值为1时，路由策略关联当前路由策略的下一条路由策略。
-   当关联优先级取值非1时，路由策略关联优先级必须大于当前路由策略的优先级。

 仅**MapResult**取值为**Permit**时，匹配通过的路由才会继续匹配关联的下一条路由策略。

 |
|Description|String|否|abc|路由策略的描述。

 |
|SourceRegionIds.N|RepeatList|否|cn-beijing|匹配路由的源地域ID列表，为match语句。最多可输入32个地域ID。

 |
|SourceInstanceIds.N|RepeatList|否|vpc-a|匹配路由的源实例ID列表，为match语句。最多可输入32个实例ID。

 |
|SourceInstanceIdsReverseMatch|Boolean|否|false|路由传递源实例ID列表排除匹配模式，取值：

 -   **false**（默认）：路由传递源实例ID在`SourceInstanceIds`中时，匹配通过。
-   **true**：路由传递源实例ID不在`SourceInstanceIds`中时，匹配通过。

 |
|DestinationInstanceIds.N|RepeatList|否|vpc-a|匹配路由的目的实例ID列表，为match语句。最多可输入32个实例ID。

 目的实例ID列表仅策略应用方向为出地域网关方向且目的实例ID为本地域下实例时有效。

 |
|DestinationInstanceIdsReverseMatch|Boolean|否|false|路由传递目的实例ID列表排除匹配模式，取值：

 -   **false**（默认）：路由传递目的实例ID在`DestinationInstanceIds`中时，匹配通过。
-   **true**：路由传递目的实例ID不在`DestinationInstanceIds`中时，匹配通过。

 |
|SourceRouteTableIds.N|RepeatList|否|vtb-a|匹配路由的源路由表ID列表，为match语句。最多可输入32个路由表ID。

 |
|DestinationRouteTableIds.N|RepeatList|否|vtb-a|匹配路由的目的路由表ID列表，为match语句。最多可输入32个路由表ID。

 目的路由表仅策略应用方向为出地域网关方向且目的路由表为本地域下路由表时有效。

 |
|SourceChildInstanceTypes.N|RepeatList|否|VPC|匹配路由的源实例类型列表，为match语句，取值：**VPC**|**VBR**|**CCN**。

 |
|DestinationChildInstanceTypes.N|RepeatList|否|VPC|匹配路由的目的实例类型列表，为match语句，取值：**VPC**|**VBR**|**CCN**。

 目的实例类型仅策略应用方向为出地域网关方向且目的实例类型为本地域下实例类型时有效。

 |
|DestinationCidrBlocks.N|RepeatList|否|1.1.1.0/10|匹配路由的前缀列表，为match语句。使用CIDR格式，最多可输入32个CIDR。

 |
|CidrMatchMode|String|否|Include|匹配前缀模式，为match语句，取值：

 -   **Include**：模糊匹配。匹配条件中的路由前缀包含被匹配路由的路由前缀即判定为匹配成功。

例如：定义1.1.0.0/16的策略可以模糊匹配到1.1.1.0/24的路由。

-   **Complete**：精确匹配。匹配条件中的路由前缀必须与被匹配路由的路由前缀一致，才判定为匹配成功。

例如：定义1.1.0.0/16的策略仅可以精确匹配到1.1.0.0/16的路由。


 |
|RouteTypes.N|RepeatList|否|System|匹配路由的类型列表，为match语句，取值：

 -   **System**：系统路由，由系统自动生成的路由。
-   **Custom**：用户路由，由用户手动添加的自定义路由。
-   **BGP**：BGP路由，通告至BGP中的路由。

 支持输入多种类型。

 |
|MatchAsns.N|RepeatList|否|65501|匹配路由的as-path列表，为match语句。as-path是公认强制属性，描述了一条BGP路由在传递过程中所经过的AS的号码。

 仅支持AS SEQUENCE，不支持AS SET、AS CONFED SEQUENCE和AS CONFED SET，即只能是AS号列表，不支持集合和子列表。

 |
|AsPathMatchMode|String|否|Include|匹配as-path模式，为match语句，取值：

 -   **Include**：模糊匹配，匹配条件中的AS Path与被匹配路由的AS Path有重叠即判定为匹配成功。
-   **Complete**：精确匹配，匹配条件中的AS Path必须与被匹配路由的AS Path一致，才判定为匹配成功。

 |
|MatchCommunitySet.N|RepeatList|否|65501:1|匹配community集合，为match语句。每个community格式为nn:nn，nn取值范围为**1**~**65535**，最多输入32个community。community需要符合RFC 1997，不支持Large community（RFC 8092）。

 **说明：** community配置错误可能导致路由不能发布到IDC侧。

 |
|CommunityMatchMode|String|否|Include|匹配community模式，为match语句，取值：

 -   **Include**：模糊匹配，匹配条件中的Community与被匹配路由的Community有重叠即判定为匹配成功。
-   **Complete**：精确匹配，匹配条件中的Community必须与被匹配路由的Community一致，才判定为匹配成功。

 |
|CommunityOperateMode|String|否|Additive|操作community的模式，为action语句，取值：

 -   **Additive**：添加。
-   **Replace**：替换。

 |
|OperateCommunitySet.N|RepeatList|否|65501:1|操作community的集合，为action语句。每个community格式为nn:nn，nn取值范围为**1**~**65535**，最多输入32个community。community需要符合RFC 1997，不支持Large community（RFC 8092）。

 **说明：** community配置错误可能导致路由不能发布到IDC侧。

 |
|Preference|Integer|否|22|修改路由的优先级，为action语句，取值：**1**~**100**，路由默认优先级为**50**，取值越小优先级越高。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B457|请求ID。

 |
|RouteMapId|String|cenrmap-w4yf7toozfol3q\*\*\*\*|路由策略的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateCenRouteMap
&CenId=cen-7qthudw0ll6jmc****
&CenRegionId=cn-hangzhou
&Priority=3
&TransmitDirection=RegionIn
&MapResult=Permit
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateCenRouteMapResponse>
    <RequestId>62172DD5-6BAC-45DF-8D44-6DFG456BAC</RequestId>
    <RouteMapId>rmap-df12d22sd23****</RouteMapId>
</CreateCenRouteMapResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RouteMapId":"cenrmap-w4yf7toozfol3q****",
	"RequestId":"62172DD5-6BAC-45DF-8D44-56SDF467BAC"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cbn)查看更多错误码。

