# DescribeCenBandwidthPackage {#doc_api_Cbn_DescribeCenBandwidthPackages .reference}

调用DescribeCenBandwidthPackage查看账户下所有带宽包的详细信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenBandwidthPackages&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeCenBandwidthPackages|要执行的操作，取值：**DescribeCenBandwidthPackages**。

 |
|Filter.N.Key|String|否|Filter.1.status|第n个过滤条件的类型，n的取值范围：**1**~**5**。

 |
|Filter.N.Value.N|RepeatList|否|Filter.1.Active|第n个过滤器的第m个值，m的取值范围：**1**~**5**。

 |
|IsOrKey|Boolean|否|false|过滤条件之间的关系，取值：

 -   **false**：过滤值之间是**与**关系。
-   **true**：过滤值之间是**或**关系。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|2|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CenBandwidthPackages| | |带宽包的详细信息。

 |
|Bandwidth|Long|2|带宽包的峰值带宽。

 |
|BandwidthPackageChargeType|String|POSTPAY|带宽包的付费类型，取值：

 -   **POSTPAY**：后付费。
-   **PREPAY**：预付费。

 |
|BusinessStatus|String|Normal|带宽包的状态，取值：

 -   **Normal**：正常状态。
-   **FinancialLocked**：欠费锁定状态。
-   **SecurityLocked**：安全风控锁定状态。

 |
|CenBandwidthPackageId|String|cenbwp-4c2zaavbvh5x\*\*\*\*|带宽包的ID。

 |
|CenIds| |cen-xxjsjfkffkfkfjkf\*\*\*\*|带宽包对应的云企业网实例的列表。

 |
|CreationTime|String|2019-02-01T11:14Z|带宽包的创建时间，采用ISO8601格式表示，格式为：YYYY-MM-DDThh:mmZ。

 |
|Description|String|cen|带宽包描述。

 |
|ExpiredTime|String|2999-09-08T16:00Z|带宽包超时时间。

 |
|GeographicRegionAId|String|china|参与互连的区域。

 |
|GeographicRegionBId|String|north-america|参与互连的区域。

 |
|GeographicSpanId|String|north-america\_china|区域对应的ID。

 |
|IsCrossBorder|Boolean|false|是否是跨境带宽包，取值：

 -   **false**：不是跨境带宽包。
-   **true**：是跨境带宽包。

 |
|Name|String|test|带宽包的名称。

 |
|Status|String|InUse|带宽包在云企业网中的状态，取值：

 -   **Idle**：空闲。
-   **InUse**：使用中。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|2|每页包含的条目数。

 |
|RequestId|String|9D7E2400-2755-4AF5-9B73-12565E4F73A0|请求ID。

 |
|TotalCount|Integer|2|列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenBandwidthPackages
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenBandwidthPackageResponse>
	  <PageNumber>1</PageNumber>
	  <TotalCount>5</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>9D7E2400-2755-4AF5-9B73-12565E4F73A0</RequestId>
	  <CenBandwidthPackages>
		    <CenBandwidthPackage>
			      <CreationTime>2018-02-07T02:19Z</CreationTime>
			      <Status>InUse</Status>
			      <GeographicRegionBId>china</GeographicRegionBId>
			      <BusinessStatus>Normal</BusinessStatus>
			      <BandwidthPackageChargeType>PREPAY</BandwidthPackageChargeType>
			      <GeographicRegionAId>china</GeographicRegionAId>
			      <CenBandwidthPackageId>cenbwp-oq2ehpxq4zhwp7****</CenBandwidthPackageId>
			      <CenIds>
				        <CenId>cen-kojok19x3j0q6k****</CenId>
			      </CenIds>
			      <ExpiredTime>2018-03-07T16:00Z</ExpiredTime>
			      <Bandwidth>1</Bandwidth>
		    </CenBandwidthPackage>
	  </CenBandwidthPackages>
</DescribeCenBandwidthPackageResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":5,
	"PageSize":10,
	"RequestId":"9D7E2400-2755-4AF5-9B73-12565E4F73A0",
	"CenBandwidthPackages":{
		"CenBandwidthPackage":[
			{
				"CreationTime":"2018-02-07T02:19Z",
				"Status":"InUse",
				"GeographicRegionBId":"china",
				"BandwidthPackageChargeType":"PREPAY",
				"BusinessStatus":"Normal",
				"GeographicRegionAId":"china",
				"CenBandwidthPackageId":"cenbwp-oq2ehpxq4zhwp7****",
				"ExpiredTime":"2018-03-07T16:00Z",
				"CenIds":{
					"CenId":[
						"cen-kojok19x3j0q6k****"
					]
				},
				"Bandwidth":1
			}
		]
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

