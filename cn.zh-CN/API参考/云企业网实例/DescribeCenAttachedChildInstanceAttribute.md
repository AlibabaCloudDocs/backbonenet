# DescribeCenAttachedChildInstanceAttribute {#doc_api_Cbn_DescribeCenAttachedChildInstanceAttribute .reference}

调用DescribeCenAttachedChildInstanceAttribute查看加载到CEN中的网络实例（VPC，VBR，CCN）的详细信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenAttachedChildInstanceAttribute&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-3cub0ges01xmvm\*\*\*\*|指定云企业网实例的ID。

 |
|ChildInstanceId|String|是|vpc-sa17uy0itvgxiq9gb\*\*\*\*|要查询的已加载网络实例的ID。

 |
|ChildInstanceRegionId|String|是|cn-hangzhou|已加载网络实例的 Region ID。

 |
|ChildInstanceType|String|是|VPC|已加载的网络实例的类型。

 |
|Action|String|否|DescribeCenAttachedChildInstanceAttribute|要执行的操作，取值：**DescribeCenAttachedChildInstances**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CenId|String|cen-5mv960yjhja0dh\*\*\*\*|云企业网实例的ID。

 |
|ChildInstanceAttachTime|String|2018-07-30T07:53Z|网络实例的加载时间。

 |
|ChildInstanceId|String|vpc-2zebdboka7d7t37vo\*\*\*\*|网络实例的ID。

 |
|ChildInstanceName|String|defaultvpc|网络实例的名称。

 |
|ChildInstanceOwnerId|Long|123456789|网络实例所属的用户的ID。

 |
|ChildInstanceRegionId|String|cn-beijing|网络实例的Region ID。

 |
|ChildInstanceType|String|VPC|网络实例的类型。

 |
|RequestId|String|ADD98358-D265-4060-87CB-A2427F5A8944|请求ID。

 |
|Status|String|Attached|网络实例的加载状态。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenAttachedChildInstanceAttribute
&CenId=cen-3cub0ges01xmvm****
&ChildInstanceId=vpc-sa17uy0itvgxiq9gb****
&ChildInstanceRegionId=cn-hangzhou
&ChildInstanceType=VPC
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenAttachedChildInstanceAttribute>
    <Status>Attached</Status>
    <ChildInstanceOwnerId>123456789</ChildInstanceOwnerId>
    <ChildInstanceId>vpc-2zebdboka7d7t37vo****</ChildInstanceId>
    <RequestId>ADD98358-D265-4060-87CB-A2427F5A8944</RequestId>
    <ChildInstanceName>defaultvpc</ChildInstanceName>
    <ChildInstanceRegionId>cn-beijing</ChildInstanceRegionId>
    <CenId>cen-5mv960yjhja0dh****</CenId>
    <ChildInstanceAttachTime>2018-07-30T07:53Z</ChildInstanceAttachTime>
    <ChildInstanceType>VPC</ChildInstanceType>
</DescribeCenAttachedChildInstanceAttribute>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Status":"Attached",
	"ChildInstanceOwnerId":"123456789",
	"ChildInstanceId":"vpc-2zebdboka7d7t37vo****",
	"RequestId":"ADD98358-D265-4060-87CB-A2427F5A8944",
	"ChildInstanceName":"defaultvpc",
	"ChildInstanceRegionId":"cn-beijing",
	"CenId":"cen-5mv960yjhja0dh****",
	"ChildInstanceAttachTime":"2018-07-30T07:53Z",
	"ChildInstanceType":"VPC"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|ParameterError|The parameter is error.|该参数错误|

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

