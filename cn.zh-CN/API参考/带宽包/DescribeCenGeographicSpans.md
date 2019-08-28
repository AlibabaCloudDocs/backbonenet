# DescribeCenGeographicSpans {#doc_api_Cbn_DescribeCenGeographicSpans .reference}

调用DescribeCenGeographicSpans查询互通区域信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenGeographicSpans&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeCenGeographicSpans|要执行的操作，取值：**DescribeCenGeographicSpans**。

 |
|GeographicSpanId|String|否|china-china|互通区域。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|GeographicSpanModels| | |互通区域的详细信息。

 |
|GeographicSpanId|String|china-china|互通区域。

 |
|LocalGeoRegionId|String|china|互通区域A。

 |
|OppositeGeoRegionId|String|china|互通区域B。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|12|每页包含的条目数。

 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。

 |
|TotalCount|Integer|20|互通区域对的总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenGeographicSpans
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenGeographicSpansResponse>
	  <PageNumber>1</PageNumber>
	  <TotalCount>1</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>09780287-BC24-4164-8334-773432E32696</RequestId>
	  <GeographicSpanModels>
		    <GeographicSpanModel>
			      <OppositeGeoRegionId>china</OppositeGeoRegionId>
			      <LocalGeoRegionId>asia-pacific</LocalGeoRegionId>
			      <GeographicSpanId>china_asia-pacific</GeographicSpanId>
		    </GeographicSpanModel>
	  </GeographicSpanModels>
</DescribeCenGeographicSpansResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"09780287-BC24-4164-8334-773432E32696",
	"GeographicSpanModels":{
		"GeographicSpanModel":[
			{
				"OppositeGeoRegionId":"china",
				"GeographicSpanId":"china_asia-pacific",
				"LocalGeoRegionId":"asia-pacific"
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

