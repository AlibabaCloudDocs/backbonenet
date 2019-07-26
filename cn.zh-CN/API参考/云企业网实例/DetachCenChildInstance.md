# DetachCenChildInstance {#doc_api_Cbn_DetachCenChildInstance .reference}

调用DetachCenChildInstance从云企业网实例中解绑指定的网络实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DetachCenChildInstance&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmx\*\*\*\*|云企业网实例的ID。

 |
|ChildInstanceId|String|是|vpc-bp18sth14qii3pnvx\*\*\*\*|指定待解绑的网络实例ID。

 |
|ChildInstanceRegionId|String|是|cn-hangzhou|网络实例所在的地域。

 |
|ChildInstanceType|String|是|VPC|网络实例的类型，取值：

 -   **VPC**。
-   **VBR**。
-   **CCN**。

 |
|Action|String|否|DetachCenChildInstance|要执行的操作，取值：**DetachCenChildInstance**。

 |
|CenOwnerId|Long|否|123456789|CEN实例所属账号的UID。

 |
|ChildInstanceOwnerId|Long|否|1234567890|网络实例所属账号的UID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DetachCenChildInstance
&CenId=cen-7qthudw0ll6jmx****
&ChildInstanceId=vpc-bp18sth14qii3pnvx****
&ChildInstanceRegionId=cn-hangzhou
&ChildInstanceType=VPC
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DetachCenChildInstanceResponse>
       <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
</DetachCenChildInstanceResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

