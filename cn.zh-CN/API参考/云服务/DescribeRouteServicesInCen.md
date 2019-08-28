# DescribeRouteServicesInCen {#doc_api_Cbn_DescribeRouteServicesInCen .reference}

调用DescribeRouteServicesInCen查询云服务。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeRouteServicesInCen&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessRegionId|String|否|cn-beijing|云服务的访问所在地。

 |
|Action|String|否|DescribeRouteServicesInCen|要执行的操作，取值：**DescribeRouteServicesInCen**。

 |
|CenId|String|否|cen-7qthudw0ll6jmc\*\*\*\*|云企业网ID。

 |
|Host|String|否|100.64.0.0/24|服务的域名或IP。

 |
|HostRegionId|String|否|cn-hangzhou|云服务的服务所在地。

 |
|HostVpcId|String|否|vpc-bp1t36rn9l53iwbsf\*\*\*\*|服务关联的VPC。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页包含的条目数。

 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。

 |
|RouteServiceEntries| | |云服务详细信息。

 |
|AccessRegionId|String|cn-beijing|云服务的访问所在地。

 |
|CenId|String|cen-xxx|云企业网ID。

 |
|Cidrs| |0.0.0.0 /0|服务的IP。如果入参**Host**是IP，则**Cidrs**为IP，如果Host是域名，则**Cidrs**为域名解析后的IP。

 |
|Host|String|0.0.0.0/0|服务的域名或IP。

 |
|HostRegionId|String|cn-hangzhou|云服务的服务所在地。

 |
|Status|String|Active|云服务的状态。

 |
|UpdateInterval|String|5|更新间隔，默认值为**5**，不支持调整。

 |
|TotalCount|Integer|10|云服务的总条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeRouteServicesInCen
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeRouteServicesInCenResponse>
	  <TotalCount>3</TotalCount>
	  <PageNumber>1</PageNumber>
	  <PageSize>10</PageSize>
	  <RouteServiceEntries>
		    <RouteServiceEntry>
			      <Status>Active</Status>
			      <CenId>cen-xxxx</CenId>
			      <Cidrs>
				        <Cidr>11.161.18.0/25</Cidr>
			      </Cidrs>
			      <HostRegionId>cn-hangzhou</HostRegionId>
			      <AccessRegionId>cn-hangzhou</AccessRegionId>
			      <Host>11.161.18.0/25</Host>
		    </RouteServiceEntry>
		    <RouteServiceEntry>
			      <Status>Active</Status>
			      <CenId>cen-xxxx</CenId>
			      <Cidrs>
				        <Cidr>11.161.19.0/25</Cidr>
			      </Cidrs>
			      <HostRegionId>cn-hangzhou</HostRegionId>
			      <AccessRegionId>cn-hangzhou</AccessRegionId>
			      <Host>11.161.19.0/25</Host>
		    </RouteServiceEntry>
		    <RouteServiceEntry>
			      <Status>Active</Status>
			      <CenId>cen-xxxx</CenId>
			      <Cidrs>
				        <Cidr>11.161.20.0/25</Cidr>
			      </Cidrs>
			      <HostRegionId>cn-hangzhou</HostRegionId>
			      <AccessRegionId>cn-hangzhou</AccessRegionId>
			      <Host>11.161.20.0/25</Host>
		    </RouteServiceEntry>
	  </RouteServiceEntries>
</DescribeRouteServicesInCenResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":3,
	"PageSize":10,
	"RouteServiceEntries":{
		"RouteServiceEntry":[
			{
				"Status":"Active",
				"Cidrs":{
					"Cidr":[
						"11.161.18.0/25"
					]
				},
				"Host":"11.161.18.0/25",
				"AccessRegionId":"cn-hangzhou",
				"HostRegionId":"cn-hangzhou",
				"CenId":"cen-xxxx"
			},
			{
				"Status":"Active",
				"Cidrs":{
					"Cidr":[
						"11.161.19.0/25"
					]
				},
				"Host":"11.161.19.0/25",
				"AccessRegionId":"cn-hangzhou",
				"HostRegionId":"cn-hangzhou",
				"CenId":"cen-xxxx"
			},
			{
				"Status":"Active",
				"Cidrs":{
					"Cidr":[
						"11.161.20.0/25"
					]
				},
				"Host":"11.161.20.0/25",
				"AccessRegionId":"cn-hangzhou",
				"HostRegionId":"cn-hangzhou",
				"CenId":"cen-xxxx"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

