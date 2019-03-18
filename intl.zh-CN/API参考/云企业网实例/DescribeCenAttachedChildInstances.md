# DescribeCenAttachedChildInstances {#doc_api_1088780 .reference}

调用DescribeCenAttachedChildInstances查看云企业网实例下已加载的网络实例。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cbn&api=DescribeCenAttachedChildInstances)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmcxxxxx|指定云企业网实例的ID。

 |
|Action|String|否|DescribeCenAttachedChildInstances|要执行的操作。

 取值： **DescribeCenAttachedChildInstances**

 |
|ChildInstanceRegionId|String|否|us-west-1|网络实例的所属地域。

 |
|ChildInstanceType|String|否|VPC|加载的网络实例类型。取值：VPC|VBR|CCN

 |
|PageNumber|Integer|否|1|列表的页码，默认值为1。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ChildInstances| | |云企业网实例加载的网络实例列表。

 |
|└CenId|String|cen-7qthudw0ll6jmxxxxx|云企业网实例的ID。

 |
|└ChildInstanceId|String|vpc-m5ex5mr548eb5f6txxx|网络实例的ID。

 |
|└ChildInstanceOwnerId|Long|1231579085111111|网络实例所属账号的UID。

 |
|└ChildInstanceRegionId|String|cn-qingdao|网络实例所在的地域。

 |
|└ChildInstanceType|String|VPC|网络实例的类型。

 取值：**VPC|VBR|CCN**

 |
|└Status|String|attaching|网络实例的状态，包括**attaching**、**attached**和**detaching**。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|12|每页包含多少条目。

 |
|RequestId|String|CDE065A6-D24D-4CE9-A45D-3BBD45B22311|请求ID。

 |
|TotalCount|Integer|1|列表条条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://cbn.aliyuncs.com/?Action=DescribeCenAttachedChildInstances
&CenId=cen-kojok19x3j0q6kx
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenAttachedChildInstancesResponse>
  <PageNumber>1</PageNumber>
  <ChildInstances>
    <ChildInstance>
      <Status>Attached</Status>
      <ChildInstanceOwnerId>18945732728xxxxxx</ChildInstanceOwnerId>
      <ChildInstanceId>vpc-hp3kz27b1uv9hsmm9vqiv</ChildInstanceId>
      <ChildInstanceRegionId>cn-huhehaote</ChildInstanceRegionId>
      <CenId>cen-kojok19x3j0q6kx5qf</CenId>
      <ChildInstanceType>VPC</ChildInstanceType>
    </ChildInstance>
    <ChildInstance>
      <Status>Attached</Status>
      <ChildInstanceOwnerId>18945732728xxxxxx</ChildInstanceOwnerId>
      <ChildInstanceId>vpc-gw85r5kr8urw957szm455</ChildInstanceId>
      <ChildInstanceRegionId>eu-central-1</ChildInstanceRegionId>
      <CenId>cen-kojok19x3j0q6kx5qf</CenId>
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
				"ChildInstanceOwnerId":"18945732728xxxxxx",
				"ChildInstanceId":"vpc-hp3kz27b1uv9hsmm9vqiv",
				"ChildInstanceRegionId":"cn-huhehaote",
				"CenId":"cen-kojok19x3j0q6kx5qf",
				"ChildInstanceType":"VPC"
			},
			{
				"Status":"Attached",
				"ChildInstanceOwnerId":"18945732728xxxxxx",
				"ChildInstanceId":"vpc-gw85r5kr8urw957szm455",
				"ChildInstanceRegionId":"eu-central-1",
				"CenId":"cen-kojok19x3j0q6kx5qf",
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

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cbn)

