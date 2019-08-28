# DescribeCenChildInstanceRouteEntries {#doc_api_Cbn_DescribeCenChildInstanceRouteEntries .reference}

调用DescribeCenChildInstanceRouteEntries查询云企业网的网络实例路由条目。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenChildInstanceRouteEntries&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网ID。

 |
|ChildInstanceId|String|是|vpc-bp18sth14qii3pnvo\*\*\*\*|网络实例ID。

 |
|ChildInstanceRegionId|String|是|cn-hangzhou|网络实例所在的地域。

 |
|ChildInstanceType|String|是|vpc|网络实例的类型，取值：

 -   **VPC**：专有网络。
-   **VBR**：边界路由器。
-   **CCN**：云连接网。

 |
|Action|String|否|DescribeCenChildInstanceRouteEntries|要执行的操作，取值：**DescribeCenChildInstanceRouteEntries**。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|Status|String|否|Active|路由的状态，取值：

 -   **Active**：可用。
-   **Backup**：备份。
-   **Rejected**：拒绝。
-   **Prohibited**：禁止。
-   **All**：所有状态。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CenRouteEntries| | |路由条目的详细信息。

 |
|AsPaths| |65501|AS Path，为BGP路由属性。

 |
|CenRouteMapRecords| | |路由策略的详细信息。

 |
|RegionId|String|cn-hangzhou|地域ID。

 |
|RouteMapId|String|cenrmap-w4yf7toozfol3q\*\*\*\*|路由策略的ID。

 |
|Communities| |65501:1|Communities，为BGP路由属性。

 |
|Conflicts| | |冲突的路由信息。

 |
|DestinationCidrBlock|String|192.168.1.0/24|冲突路由的目标网段地址。

 |
|InstanceId|String|ecs-xxdjakjdakhfkfka\*\*\*\*|冲突实例ID。

 |
|InstanceType|String|ECS|网络实例类型。

 |
|RegionId|String|cn-hangzhou|地域ID。

 |
|Status|String|conflict|异常原因，取值：

 -   **conflict**：路由发生冲突。
-   **overflow**：其他网络实例路由表路由数量超出限制。
-   **prohibited**：VBR策略不允许的默认路由。

 |
|DestinationCidrBlock|String|192.168.3.0/24|路由条目的目标网段。

 |
|NextHopInstanceId|String|vpc-o6woh5s494zueq40v\*\*\*\*|下一跳网络实例（VPC或VBR）的ID。

 |
|NextHopRegionId|String|cn-hangzhou|下一跳网络实例所属地域的ID。

 |
|NextHopType|String|VPC|下一跳网络实例的类型，取值：

 -   **VPC**：专有网络。
-   **VBR**：边界路由器。

 |
|OperationalMode|Boolean|true|是否允许发布或撤销该路由到云企业网，取值：

 -   **true**：允许发布或撤销。
-   **false**：不允许发布或撤销。

 |
|PublishStatus|String|Published|在云企业网中的发布状态：

 -   **Published**：已发布。
-   **NonPublished**：未发布。

 |
|RouteTableId|String|vtb-bp1r9pvl4xen8s9ju\*\*\*\*|路由表ID。

 |
|Status|String|Active|路由的状态。

 |
|Type|String|CBN|路由条目的类型。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页包含的条目数。

 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。

 |
|TotalCount|Integer|30|路由条目的总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenChildInstanceRouteEntries
&CenId=cen-7qthudw0ll6jmc****
&ChildInstanceId=vpc-bp18sth14qii3pnvo****
&ChildInstanceRegionId=cn-hangzhou
&ChildInstanceType=vpc
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenChildInstanceRouteEntriesResponse>
	  <PageNumber>1</PageNumber>
	  <TotalCount>4</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>17A57456-EF48-419D-9AE6-9B03D9996018</RequestId>
	  <CenRouteEntries>
		    <CenRouteEntry>
			      <NextHopInstanceId>vbr-bp13gtbhdp0pfqg6s****</NextHopInstanceId>
			      <CenRouteMapRecords>
				        <CenRouteMapRecord>
					          <RouteMapId>cenrmap-4lcjxzo2zyqjd3****</RouteMapId>
					          <RegionId>cn-hangzhou</RegionId>
				        </CenRouteMapRecord>
			      </CenRouteMapRecords>
			      <OperationalMode>false</OperationalMode>
			      <Status>Active</Status>
			      <AsPaths></AsPaths>
			      <Communities></Communities>
			      <Type>CEN</Type>
			      <RouteTableId>vtb-bp1r9pvl4xen8s9ju****</RouteTableId>
			      <NextHopRegionId>cn-hangzhou</NextHopRegionId>
			      <NextHopType>VBR</NextHopType>
			      <Conflicts></Conflicts>
			      <DestinationCidrBlock>10.0.0.0/24</DestinationCidrBlock>
		    </CenRouteEntry>
		    <CenRouteEntry>
			      <CenRouteMapRecords></CenRouteMapRecords>
			      <OperationalMode>false</OperationalMode>
			      <Status>Active</Status>
			      <AsPaths></AsPaths>
			      <Communities></Communities>
			      <Type>System</Type>
			      <RouteTableId>vtb-bp1r9pvl4xen8s9ju****</RouteTableId>
			      <NextHopType>service</NextHopType>
			      <Conflicts></Conflicts>
			      <DestinationCidrBlock>100.64.0.0/10</DestinationCidrBlock>
			      <PublishStatus>NonPublished</PublishStatus>
		    </CenRouteEntry>
		    <CenRouteEntry>
			      <CenRouteMapRecords></CenRouteMapRecords>
			      <OperationalMode>true</OperationalMode>
			      <Status>Active</Status>
			      <AsPaths></AsPaths>
			      <Communities></Communities>
			      <Type>System</Type>
			      <RouteTableId>vtb-bp1r9pvl4xen8s9ju****</RouteTableId>
			      <NextHopType>local</NextHopType>
			      <Conflicts></Conflicts>
			      <DestinationCidrBlock>172.16.0.0/24</DestinationCidrBlock>
			      <PublishStatus>Published</PublishStatus>
		    </CenRouteEntry>
		    <CenRouteEntry>
			      <NextHopInstanceId>vbr-bp13gtbhdp0pfqg6s****</NextHopInstanceId>
			      <CenRouteMapRecords>
				        <CenRouteMapRecord>
					          <RouteMapId>cenrmap-4lcjxzo2zyqjd3****</RouteMapId>
					          <RegionId>cn-hangzhou</RegionId>
				        </CenRouteMapRecord>
			      </CenRouteMapRecords>
			      <OperationalMode>false</OperationalMode>
			      <Status>Active</Status>
			      <AsPaths></AsPaths>
			      <Communities></Communities>
			      <Type>CEN</Type>
			      <RouteTableId>vtb-bp1r9pvl4xen8s9ju****</RouteTableId>
			      <NextHopRegionId>cn-hangzhou</NextHopRegionId>
			      <NextHopType>VBR</NextHopType>
			      <Conflicts></Conflicts>
			      <DestinationCidrBlock>192.168.2.0/24</DestinationCidrBlock>
		    </CenRouteEntry>
	  </CenRouteEntries>
</DescribeCenChildInstanceRouteEntriesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":4,
	"PageSize":10,
	"RequestId":"17A57456-EF48-419D-9AE6-9B03D9996018",
	"CenRouteEntries":{
		"CenRouteEntry":[
			{
				"NextHopInstanceId":"vbr-bp13gtbhdp0pfqg6s****",
				"Status":"Active",
				"OperationalMode":false,
				"CenRouteMapRecords":{
					"CenRouteMapRecord":[
						{
							"RouteMapId":"cenrmap-4lcjxzo2zyqjd3****",
							"RegionId":"cn-hangzhou"
						}
					]
				},
				"AsPaths":{
					"AsPath":[]
				},
				"Communities":{
					"Community":[]
				},
				"Type":"CEN",
				"NextHopType":"VBR",
				"NextHopRegionId":"cn-hangzhou",
				"RouteTableId":"vtb-bp1r9pvl4xen8s9ju****",
				"DestinationCidrBlock":"10.0.0.0/24",
				"Conflicts":{
					"Conflict":[]
				}
			},
			{
				"Status":"Active",
				"OperationalMode":false,
				"CenRouteMapRecords":{
					"CenRouteMapRecord":[]
				},
				"AsPaths":{
					"AsPath":[]
				},
				"Communities":{
					"Community":[]
				},
				"Type":"System",
				"NextHopType":"service",
				"RouteTableId":"vtb-bp1r9pvl4xen8s9ju****",
				"DestinationCidrBlock":"100.64.0.0/10",
				"Conflicts":{
					"Conflict":[]
				},
				"PublishStatus":"NonPublished"
			},
			{
				"Status":"Active",
				"OperationalMode":true,
				"CenRouteMapRecords":{
					"CenRouteMapRecord":[]
				},
				"AsPaths":{
					"AsPath":[]
				},
				"Communities":{
					"Community":[]
				},
				"Type":"System",
				"NextHopType":"local",
				"RouteTableId":"vtb-bp1r9pvl4xen8s9ju****",
				"DestinationCidrBlock":"172.16.0.0/24",
				"Conflicts":{
					"Conflict":[]
				},
				"PublishStatus":"Published"
			},
			{
				"NextHopInstanceId":"vbr-bp13gtbhdp0pfqg6s****",
				"Status":"Active",
				"OperationalMode":false,
				"CenRouteMapRecords":{
					"CenRouteMapRecord":[
						{
							"RouteMapId":"cenrmap-4lcjxzo2zyqjd3****",
							"RegionId":"cn-hangzhou"
						}
					]
				},
				"AsPaths":{
					"AsPath":[]
				},
				"Communities":{
					"Community":[]
				},
				"Type":"CEN",
				"NextHopType":"VBR",
				"NextHopRegionId":"cn-hangzhou",
				"RouteTableId":"vtb-bp1r9pvl4xen8s9ju****",
				"DestinationCidrBlock":"192.168.2.0/24",
				"Conflicts":{
					"Conflict":[]
				}
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

