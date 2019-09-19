# UntagResources {#doc_api_Cbn_UntagResources .reference}

调用UntagResources为指定的资源列表统一解绑并删除标签。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=UntagResources&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|ResourceId.N|RepeatList|是|cen-7qthudw0ll6jmc\*\*\*\*|资源ID，N的取值范围为**1**~**50**。

 |
|ResourceType|String|是|cen|资源类型，取值：**cen**。

 |
|Action|String|否|UntagResources|要执行的操作，取值：**UntagResources**。

 |
|TagKey.N|RepeatList|否|FinanceDept|资源的标签值。N的取值范围：**1**~**20**。一旦传入该值，可以为空字符串。最多支持128个字符，不能以`aliyun`和`acs:`开头，不能包含`http://`或者`https://`。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C46FF5A8-C5F0-4024-8262-B16B639225A0|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=UntagResources
&ResourceId.1=cen-7qthudw0ll6jmc****
&ResourceType=cen
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UntagResourcesResponse>
      <RequestId>C46FF5A8-C5F0-4024-8262-B16B639225A0</RequestId>
</UntagResourcesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C46FF5A8-C5F0-4024-8262-B16B639225A0"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

