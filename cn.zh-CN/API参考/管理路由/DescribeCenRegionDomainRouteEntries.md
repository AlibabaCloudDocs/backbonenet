# DescribeCenRegionDomainRouteEntries {#doc_api_Cbn_DescribeCenRegionDomainRouteEntries .reference}

调用DescribeCenRegionDomainRouteEntries查询云企业网实例中某个地域内路由条目的详细信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenRegionDomainRouteEntries&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6j\*\*\*\*|指定待查询的云企业网实例的ID。

 |
|CenRegionId|String|是|cn-hangzhou|指定待查询的地域的ID。

 |
|Action|String|否|DescribeCenRegionDomainRouteEntries|要执行的操作，取值：**DescribeCenRegionDomainRouteEntries**。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|1|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CenRouteEntries| | |路由条目的详细信息。

 |
|CenOutRouteMapRecords| | |云企业网出方向路由策略。

 |
|RegionId|String|cn-hangzhou|地域ID。

 |
|RouteMapId|String|cenrmap-w4yf7toozfol3q\*\*\*\*|路由策略ID。

 |
|CenRouteMapRecords| | |云企业网入方向路由策略。

 |
|RegionId|String|cn-hangzhou|地域ID。

 |
|RouteMapId|String|cenrmap-w4yf7toozfol3q\*\*\*\*|路由策略的ID。

 |
|DestinationCidrBlock|String|192.168.1.0/24|路由条目的目标网段。

 |
|NextHopInstanceId|String|pc-rj9gt5nll27onu7\*\*\*\*|下一跳的网络实例（VPC或VBR）的ID。

 |
|NextHopRegionId|String|us-west-1|下一跳的网络实例所属地域的ID。

 |
|NextHopType|String|VPC|下一跳的网络实例的类型，VBR或VPC。

 |
|Type|String|CBN|路由条目的类型。

 |
|PageNumber|Integer|2|当前页码。

 |
|PageSize|Integer|2|每页包含的条目数。

 |
|RequestId|String|73C834EF-82EF-4721-952E-75291F169A64|请求ID。

 |
|TotalCount|Integer|1|列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenRegionDomainRouteEntries
&CenId=cen-7qthudw0ll6j****
&CenRegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenRegionDomainRouteEntries>
      <PageNumber>1</PageNumber>
	  <TotalCount>2</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>73C834EF-82EF-4721-952E-75291F169A64</RequestId>
	  <CenRouteEntries>
		    <CenRouteEntry>
			      <NextHopInstanceId>vpc-m5ex5mr548eb5f6te****</NextHopInstanceId>
			      <Type>CBN</Type>
			      <NextHopRegionId>cn-qingdao</NextHopRegionId>
			      <NextHopType>VPC</NextHopType>
			      <DestinationCidrBlock>192.168.0.0/24</DestinationCidrBlock>
		    </CenRouteEntry>
		    <CenRouteEntry>
			      <NextHopInstanceId>vpc-rj9gt5nll27onu7wj****</NextHopInstanceId>
			      <Type>CBN</Type>
			      <NextHopRegionId>us-west-1</NextHopRegionId>
			      <NextHopType>VPC</NextHopType>
			      <DestinationCidrBlock>192.168.1.0/24</DestinationCidrBlock>
		    </CenRouteEntry>
	  </CenRouteEntries>
    </DescribeCenRegionDomainRouteEntries>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":2,
	"PageSize":10,
	"RequestId":"73C834EF-82EF-4721-952E-75291F169A64",
	"CenRouteEntries":{
		"CenRouteEntry":[
			{
				"NextHopInstanceId":"vpc-m5ex5mr548eb5f6te****",
				"Type":"CBN",
				"NextHopType":"VPC",
				"NextHopRegionId":"cn-qingdao",
				"DestinationCidrBlock":"192.168.0.0/24"
			},
			{
				"NextHopInstanceId":"vpc-rj9gt5nll27onu7wj****",
				"Type":"CBN",
				"NextHopType":"VPC",
				"NextHopRegionId":"us-west-1",
				"DestinationCidrBlock":"192.168.1.0/24"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

