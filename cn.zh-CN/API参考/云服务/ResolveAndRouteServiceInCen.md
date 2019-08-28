# ResolveAndRouteServiceInCen {#doc_api_Cbn_ResolveAndRouteServiceInCen .reference}

调用ResolveAndRouteServiceInCen设置云服务。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=ResolveAndRouteServiceInCen&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessRegionIds.N|RepeatList|是|cn-hangzhou|云服务的访问所在地。

 |
|CenId|String|是|cen-ckwa2hhmuislse\*\*\*\*|云企业网ID。

 |
|Host|String|是|100.64.1.0/24|服务域名或IP。

 |
|HostRegionId|String|是|cn-beijing|云服务的服务所在地。

 |
|Action|String|否|ResolveAndRouteServiceInCen|要执行的操作，取值：**ResolveAndRouteServiceInCen**。

 |
|ClientToken|String|否|02fb3da4-130e-11e9-8e44-0016e04115b|客户端token，用于保证请求的幂等性。由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII字符。

 |
|HostVpcId|String|否|vpc-o6woh5s494zueq40v\*\*\*\*|服务关联的VPC。

 |
|UpdateInterval|Long|否|5|更新间隔，默认值为**5**，不支持修改。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C0245BEF-52AC-44A8-A776-EF96FD26A5CA|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ResolveAndRouteServiceInCen
&AccessRegionIds.1=cn-hangzhou
&CenId=cen-ckwa2hhmuislse****
&Host=100.64.1.0/24
&HostRegionId=cn-beijing
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ResolveAndRouteServiceInCenResponse>
         <RequestId>17A57456-EF48-419D-9AE6-9B03D9996018</RequestId>
</ResolveAndRouteServiceInCenResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C0245BEF-52AC-44A8-A776-EF96FD26A5CA"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

