# DescribeGrantRulesToCen {#doc_api_Cbn_DescribeGrantRulesToCen .reference}

调用DescribeGrantRulesToCen查看网络实例对云企业网实例的授权关系。

**说明：** 该接口是VPC的API，所以调用该接口必须使用`vpc.aliyuncs.com`域名。API version为2016-04-28。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeGrantRulesToCen&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmxx\*\*\*\*|云企业网实例的ID。

 |
|ProductType|String|是|VPC|产品类型。

 |
|RegionId|String|是|cn-hangzou|网络实例所在的地域。

 |
|Action|String|否|DescribeGrantRulesToCen|要执行的操作，取值：**DescribeGrantRulesToCen**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|GrantRules| | |授权关系。

 |
|CenId|String|cen-7qthudw0ll6jmccc\*\*\*\*|指定云企业网实例的ID。

 |
|ChildInstanceId|String|vpc-bp18sth14qii3pnvc\*\*\*\*|加载的网络实例ID。

 |
|ChildInstanceOwnerId|Long|1231579085529123|网络实例所属账号的UID。

 |
|ChildInstanceRegionId|String|cn-hangzhou|网络实例所在的地域。

 |
|ChildInstanceType|String|VPC|加载的网络实例类型，取值：

 -   **VPC**。
-   **VBR**。
-   **CCN**。

 |
|RequestId|String|330714D1-F335-4CE2-9D29-F54445937387|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeGrantRulesToCen
&CenId=cen-7qthudw0ll6jmxx****
&ProductType=VPC
&RegionId=cn-hangzou
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
                  <CbnInstanceId>cbn-6ugox0vl0zff4g****</CbnInstanceId>
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
				"CbnInstanceId":"cbn-6ugox0vl0zff4g****",
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

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cbn)查看更多错误码。

