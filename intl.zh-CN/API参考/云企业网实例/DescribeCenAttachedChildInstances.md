# DescribeCenAttachedChildInstances {#doc_api_Cbn_DescribeCenAttachedChildInstances .reference}

调用DescribeCenAttachedChildInstances查看云企业网实例下已加载的网络实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenAttachedChildInstances&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmcx\*\*\*\*|指定云企业网实例的ID。

 |
|Action|String|否|DescribeCenAttachedChildInstances|要执行的操作，取值：**DescribeCenAttachedChildInstances**。

 |
|ChildInstanceRegionId|String|否|us-west-1|网络实例的所属地域。

 |
|ChildInstanceType|String|否|VPC|加载的网络实例类型，取值：

 -   **VPC**。
-   **VBR**。
-   **CCN**。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ChildInstances| | |云企业网实例加载的网络实例列表。

 |
|CenId|String|cen-7qthudw0ll6jmx\*\*\*\*|云企业网实例的ID。

 |
|ChildInstanceAttachTime|String|2018-10-16T08:47Z|网络实例的加载时间。

 |
|ChildInstanceId|String|vpc-m5ex5mr548eb5f6\*\*\*\*|网络实例的ID。

 |
|ChildInstanceOwnerId|Long|123456789|网络实例所属账号的UID。

 |
|ChildInstanceRegionId|String|cn-qingdao|网络实例所在的地域。

 |
|ChildInstanceType|String|VPC|网络实例的类型，取值：

 -   **VPC**。
-   **VBR**。
-   **CCN**。

 |
|Status|String|attaching|网络实例的状态，取值：

 -   **attaching**：加载中。
-   **attached**：已加载。
-   **detaching**：卸载中。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|12|每页包含的条目数。

 |
|RequestId|String|CDE065A6-D24D-4CE9-A45D-3BBD45B22311|请求ID。

 |
|TotalCount|Integer|1|列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenAttachedChildInstances
&CenId=cen-7qthudw0ll6jmcx****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenAttachedChildInstancesResponse>
	  <PageNumber>1</PageNumber>
	  <ChildInstances>
		    <ChildInstance>
			      <Status>Attached</Status>
			      <ChildInstanceOwnerId>123456789</ChildInstanceOwnerId>
			      <ChildInstanceId>vpc-hp3kz27b1uv9hsmm9****</ChildInstanceId>
			      <ChildInstanceRegionId>cn-huhehaote</ChildInstanceRegionId>
			      <CenId>cen-kojok19x3j0q6k****</CenId>
			      <ChildInstanceType>VPC</ChildInstanceType>
		    </ChildInstance>
		    <ChildInstance>
			      <Status>Attached</Status>
			      <ChildInstanceOwnerId>123456789</ChildInstanceOwnerId>
			      <ChildInstanceId>vpc-gw85r5kr8urw957sz****</ChildInstanceId>
			      <ChildInstanceRegionId>eu-central-1</ChildInstanceRegionId>
			      <CenId>cen-kojok19x3j0q6k****</CenId>
			      <ChildInstanceType>VPC</ChildInstanceType>
		    </ChildInstance>
	  </ChildInstances>
	  <TotalCount>3</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>50F8E0AB-A225-41C0-AC88-FFB51A4F5C72</RequestId>
</DescribeCenAttachedChildInstancesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"ChildInstances":{
		"ChildInstance":[
			{
				"Status":"Attached",
				"ChildInstanceOwnerId":"123456789",
				"ChildInstanceId":"vpc-hp3kz27b1uv9hsmm9****",
				"ChildInstanceRegionId":"cn-huhehaote",
				"CenId":"cen-kojok19x3j0q6k****",
				"ChildInstanceType":"VPC"
			},
			{
				"Status":"Attached",
				"ChildInstanceOwnerId":"123456789",
				"ChildInstanceId":"vpc-gw85r5kr8urw957sz****",
				"ChildInstanceRegionId":"eu-central-1",
				"CenId":"cen-kojok19x3j0q6k****",
				"ChildInstanceType":"VPC"
			}
		]
	},
	"TotalCount":3,
	"PageSize":10,
	"RequestId":"50F8E0AB-A225-41C0-AC88-FFB51A4F5C72"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cbn)查看更多错误码。

