# DescribeChildInstanceRegions {#doc_api_Cbn_DescribeChildInstanceRegions .reference}

调用DescribeChildInstanceRegions查询支持加载到云企业网中的网络实例的地域。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeChildInstanceRegions&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeChildInstanceRegions|要执行的操作，取值：**DescribeChildInstanceRegions**。

 |
|ProductType|String|否|VPC|实例类型，取值：

 -   **VPC**：专有网络。
-   **VBR**：边界路由器。
-   **CCN**：云连接网。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Regions| | |地域信息。

 |
|LocalName|String|华东 1|地域名称

 |
|RegionId|String|cn-hangzhou|地域ID。

 |
|RequestId|String|A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeChildInstanceRegions
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeChildInstanceRegionsResponse>
	  <RequestId>D5CEED59-36AA-47CC-9D81-16F71C46BD80</RequestId>
	  <Regions>
		    <Region>
			      <RegionId>cccn-hangzhou</RegionId>
			      <LocalName>华东 1</LocalName>
		    </Region>
	  </Regions>
</DescribeChildInstanceRegionsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"D5CEED59-36AA-47CC-9D81-16F71C46BD80",
	"Regions":{
		"Region":[
			{
				"RegionId":"cn-hangzhou",
				"LocalName":"华东 1"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

