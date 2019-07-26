# DescribeCenInterRegionBandwidthLimits {#doc_api_Cbn_DescribeCenInterRegionBandwidthLimits .reference}

调用DescribeCenInterRegionBandwidthLimits查询各个地域之间的跨地域互通带宽。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenInterRegionBandwidthLimits&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeCenInterRegionBandwidthLimits|要执行的操作，取值：**DescribeCenInterRegionBandwidthLimits**。

 |
|CenId|String|否|cen-7qthudw0ll6jm\*\*\*\*|指定查询该云企业网实例内的跨地域互通带宽。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|1|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CenInterRegionBandwidthLimits| | |跨地域互连的详细信息。

 |
|BandwidthLimit|Long|2|两个地域之间的跨地域互通带宽。

 |
|CenId|String|cen-7qthudw0ll6j\*\*\*\*|云企业网实例的ID。

 |
|GeographicSpanId|String|north-america\_china|区域对应的ID。

 |
|LocalRegionId|String|cn-hangzhou|本端地域的ID。

 |
|OppositeRegionId|String|us-west-1|对端地域的ID。

 |
|Status|String|Active|跨地域互通带宽的状态，取值：

 -   **Active**：运行状态。
-   **Modifying**：修改中。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|1|每页包含的条目数。

 |
|RequestId|String|613A45FA-DAAD-441E-BC68-0ABB1A4ABEE8|请求ID。

 |
|TotalCount|Integer|1|列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenInterRegionBandwidthLimits
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenInterRegionBandwidthLimitsResponse>
          <CenInterRegionBandwidthLimits>
                <CenInterRegionBandwidthLimit>
                  <Status> Active </Status>
                      <LocalRegionId>cn-hangzhou-667</LocalRegionId>
                          <CenId>Cen-to55jjgdqd4pfv****</CenId>
                          <OppositeRegionId>cn-hangzhou-668</OppositeRegionId>
                          <BandwidthLimit>1000</BandwidthLimit>
                    </CenInterRegionBandwidthLimit>
              </CenInterRegionBandwidthLimits>
          <PageNumber>1</PageNumber>
          <TotalCount>1</TotalCount>
          <PageSize>10</PageSize>
      <RequestId>C4CF2E97-5C04-4A9E-B908-BE95FF68C7B2</RequestId>
</DescribeCenInterRegionBandwidthLimitsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DescribeCenInterRegionBandwidthLimitsResponse":{
		"PageNumber":"1",
		"TotalCount":"1",
		"PageSize":"10",
		"RequestId":"C4CF2E97-5C04-4A9E-B908-BE95FF68C7B2",
		"CenInterRegionBandwidthLimits":{
			"CenInterRegionBandwidthLimit":{
				"Status":" Active ",
				"LocalRegionId":"cn-hangzhou-667",
				"OppositeRegionId":"cn-hangzhou-668",
				"CenId":"Cen-to55jjgdqd4pfv****",
				"BandwidthLimit":"1000"
			}
		}
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

