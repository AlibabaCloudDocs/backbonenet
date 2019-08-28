# DeleteRouteServiceInCen {#doc_api_Cbn_DeleteRouteServiceInCen .reference}

调用DeleteRouteServiceInCen删除云服务。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DeleteRouteServiceInCen&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessRegionId|String|是|cn-hangzhou|云服务的访问所在地。

 |
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网实例ID。

 |
|Host|String|是|100.64.0.0/8|云服务的IP地址或域名。

 |
|HostRegionId|String|是|cn-shanghai|云服务的服务所在地。

 |
|Action|String|否|DeleteRouteServiceInCen|要执行的操作，取值：**DeleteRouteServiceInCen**。

 |
|HostVpcId|String|否|vpc-bp1t36rn9l53iwbsf\*\*\*\*|服务关联的VPC。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|2315DEB7-5E92-423A-91F7-4C1EC9AD97C3|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteRouteServiceInCen
&AccessRegionId=cn-hangzhou
&CenId=cen-7qthudw0ll6jmc****
&Host=100.64.0.0/8
&HostRegionId=cn-shanghai
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteRouteServiceInCenResponse>
    <RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
</DeleteRouteServiceInCenResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

