# DescribeCenPrivateZoneRoutes {#doc_api_Cbn_DescribeCenPrivateZoneRoutes .reference}

调用DescribeCenPrivateZoneRoutes查询PrivateZone。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenPrivateZoneRoutes&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网ID。

 |
|AccessRegionId|String|否|cn-hangzhou|访问所在地。

 访问所在地是指通过CEN访问PrivateZone服务的源地域。

 |
|Action|String|否|DescribeCenPrivateZoneRoutes|要执行的操作，取值：**DescribeCenPrivateZoneRoutes**。

 |
|HostRegionId|String|否|cn-hangzhou|服务所在地。

 服务所在地是指通过CEN访问PrivateZone服务的目的地域。

 |
|PageNumber|Integer|否|10|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CenId|String|cen-7qthudw0ll6jmc\*\*\*\*|云企业网ID。

 |
|PageNumber|Integer|10|当前页码。

 |
|PageSize|Integer|10|每页包含的条目数。

 |
|PrivateZoneDnsServers|String|100.100.xx.136/32,100.100.xx.138/32|PrivateZone的DNS IP。

 |
|PrivateZoneInfos| | |PrivateZone的详细信息。

 |
|AccessRegionId|String|cn-hangzhou|访问所在地。

 访问所在地是指通过CEN访问PrivateZone服务的源地域。

 |
|HostRegionId|String|cn-hangzhou|服务所在地。

 服务所在地是指通过CEN访问PrivateZone服务的目的地域。

 |
|HostVpcId|String|vpc-bp18sth14qii3pnvo\*\*\*\*|服务所在地的VPC。

 |
|Status|String|Active|PrivateZone的状态。

 |
|RequestId|String|C0245BEF-52AC-44A8-A776-EF96FD26A5CA|请求ID。

 |
|TotalCount|Integer|10|列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenPrivateZoneRoutes
&CenId=cen-7qthudw0ll6jmc****	
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenPrivateZoneRoutesResponse>
	  <PrivateZoneInfos>
		    <PrivateZoneInfo>
			      <Status>Active</Status>
			      <HostVpcId>vpc-bp18sth14qii3pnvo****</HostVpcId>
			      <AccessRegionId>ccn-cn-shanghai</AccessRegionId>
			      <HostRegionId>cn-hangzhou</HostRegionId>
		    </PrivateZoneInfo>
		    <PrivateZoneInfo>
			      <Status>Active</Status>
			      <HostVpcId>vpc-bp18sth14qii3pnvo****</HostVpcId>
			      <AccessRegionId>cn-hangzhou</AccessRegionId>
			      <HostRegionId>cn-hangzhou</HostRegionId>
		    </PrivateZoneInfo>
	  </PrivateZoneInfos>
	  <PageNumber>1</PageNumber>
	  <TotalCount>2</TotalCount>
	  <PageSize>10</PageSize>
	  <PrivateZoneDnsServers>100.100.xx.136/32,100.100.xx.138/32</PrivateZoneDnsServers>
	  <RequestId>461EC1B5-04A8-4706-8764-8F5BCEF48A6F</RequestId>
</DescribeCenPrivateZoneRoutesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PrivateZoneInfos":{
		"PrivateZoneInfo":[
			{
				"Status":"Active",
				"HostVpcId":"vpc-bp18sth14qii3pnvo****",
				"AccessRegionId":"ccn-cn-shanghai",
				"HostRegionId":"cn-hangzhou"
			},
			{
				"Status":"Active",
				"HostVpcId":"vpc-bp18sth14qii3pnvo****",
				"AccessRegionId":"cn-hangzhou",
				"HostRegionId":"cn-hangzhou"
			}
		]
	},
	"PageNumber":1,
	"TotalCount":2,
	"PrivateZoneDnsServers":"100.100.xx.136/32,100.100.xx.138/32",
	"PageSize":10,
	"RequestId":"461EC1B5-04A8-4706-8764-8F5BCEF48A6F"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

