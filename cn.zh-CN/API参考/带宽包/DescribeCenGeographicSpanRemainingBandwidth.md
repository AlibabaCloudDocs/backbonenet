# DescribeCenGeographicSpanRemainingBandwidth {#doc_api_Cbn_DescribeCenGeographicSpanRemainingBandwidth .reference}

调用DescribeCenGeographicSpanRemainingBandwidth查询指定带宽包的剩余可用带宽值。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenGeographicSpanRemainingBandwidth&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-nh98vzx8gfhlwn\*\*\*\*|带宽包所属的CEN实例ID。

 |
|GeographicRegionAId|String|是|China|带宽包的互通区域，取值：**China**|**North-America**|**Asia-Pacific**|**Europe**|**Australia**。

 |
|GeographicRegionBId|String|是|North-America|带宽包的另一个互通区域，取值：**China**|**North-America**|**Asia-Pacific**|**Europe**|**Australia**。

 |
|Action|String|否|DescribeCenGeographicSpanRemainingBandwidth|要执行的操作，取值：**DescribeCenGeographicSpanRemainingBandwidth**。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RemainingBandwidth|Long|2|带宽包剩余带宽值。

 |
|RequestId|String|E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenGeographicSpanRemainingBandwidth
&CenId=cen-nh98vzx8gfhlwn****
&GeographicRegionAId=China
&GeographicRegionBId=North-America
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenGeographicSpanRemainingBandwidthResponse>
      <RequestId>E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B</RequestId>
      <RemainingBandwidth>2</RemainingBandwidth>
</DescribeCenGeographicSpanRemainingBandwidthResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B",
	"RemainingBandwidth":"2"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

