# DescribeGrantRulesToCen {#doc_api_1088808 .reference}

调用DescribeGrantRulesToCen查看网络实例对云企业网实例的授权关系。

**说明：** 该接口是VPC的API，所以调用该接口必须使用`vpc.aliyuncs.com`域名。API version为2016-04-28。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cbn&api=DescribeGrantRulesToCen)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmxxxxxx|云企业网实例的ID。

 |
|ProductType|String|是|VPC|产品类型。

 |
|RegionId|String|是|cn-hangzou|网络实例所在的地域。

 |
|Action|String|否|DescribeGrantRulesToCen|要执行的操作。

 取值： **DescribeGrantRulesToCen**

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|GrantRules| | |授权关系。

 |
|└CenId|String|cen-7qthudw0ll6jmccccccc|指定云企业网实例的ID。

 |
|└ChildInstanceId|String|vpc-bp18sth14qii3pnvccccc|加载的网络实例ID。

 |
|└ChildInstanceOwnerId|Long|1231579085529123|网络实例所属账号的UID。

 |
|└ChildInstanceRegionId|String|cn-hangzhou|网络实例所在的地域。

 |
|└ChildInstanceType|String|VPC|加载的网络实例类型。取值：**VPC|VBR|CCN**

 |
|RequestId|String|330714D1-F335-4CE2-9D29-F54445937387|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?CenId=cen-7qthudw0ll6jmxxxxxx
&ProductType=VPC
&RegionId=455AC20C-7061-446A-BDBD-B3BEE0856304
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeGrantRulesToCenResponse>
  <TotalCount>1</TotalCount>
  <PageNumber>1</PageNumber>
  <CbnGrantRules>
    <CbnGrantRule>
      <CbnInstanceId>cbn-6ugox0vl0zff4gl0b8</CbnInstanceId>
      <CbnOwnerId>101664776xxxx</CbnOwnerId>
      <CreationTime>2018-01-18T11:49:09Z</CreationTime>
    </CbnGrantRule>
  </CbnGrantRules>
  <PageSize>10</PageSize>
  <RequestId>330714D1-F335-4CE2-9D29-F54445937387</RequestId>
</DescribeGrantRulesToCenResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"CbnGrantRules":{
		"CbnGrantRule":[
			{
				"CreationTime":"2018-01-18T11:49:09Z",
				"CbnInstanceId":"cbn-6ugox0vl0zff4gl0b8",
				"CbnOwnerId":"101664776xxxx"
			}
		]
	},
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"330714D1-F335-4CE2-9D29-F54445937387"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cbn)

