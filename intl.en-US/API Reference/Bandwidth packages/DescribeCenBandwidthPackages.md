# DescribeCenBandwidthPackages {#doc_api_Cbn_DescribeCenBandwidthPackages .reference}

Queries bandwidth packages under your account.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeCenBandwidthPackages&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|DescribeCenBandwidthPackages|The name of this action. Value: **DescribeCenBandwidthPackages**

 |
|Filter.N.Key|String|No|status|The filter key \(filter condition\). You can specify up to five filter keys. The following filter keys are supported.

 -   **CenId**: Cloud Enterprise Network \(CEN\) instance ID
-   **Status**: bandwidth package status. Valid values: Idle | InUse
-   **CenBandwidthPackageId**: bandwidth package ID
-   **Name**: bandwidth package name

 |
|Filter.N.Value.N|RepeatList|No|Idle|The value of the**filter key**. You can specify multiple values for a **filter key**. These multiple values are of the **OR** relation, which means that this filter condition is met when one of the specified values is matched.

 |
|IncludeReservationData|Boolean|No|true|Indicates whether to include renewal data. Valid values:

 -   **true**: Return renewal data in the response.
-   **false**: Do not return renewal data in the response.

 |
|IsOrKey|Boolean|No|false|The relationship between filter keys. Valid values:

 -   **false** \(default\): The filter keys are of the **AND** relation, which means that a bandwidth package is returned only when it matches all the filter conditions.
-   **true**: The filter keys are of the **OR** relation, which means that a bandwidth package is returned as long as it matches one of the filter conditions.

 |
|PageNumber|Integer|No|1|The page number. Default value: **1**

 |
|PageSize|Integer|No|2|The number of entries per page in the case of a paged query result. Maximum value: **50**. Default value: **10**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|CenBandwidthPackages| | |The list of bandwidth packages.

 |
|CenBandwidthPackage| | |The details of the bandwidth package.

 |
|Bandwidth|Long|2|The peak bandwidth of the bandwidth package.

 |
|BandwidthPackageChargeType|String|PREPAY|The billing method of the bandwidth package.

 |
|BusinessStatus|String|Normal|The status of the bandwidth package.

 -   **Normal**: The bandwidth package is normal.
-   **FinancialLocked**: The bandwidth package is locked because of an overdue bill.
-   **SecurityLocked**: The bandwidth package is locked for security reasons.

 |
|CenBandwidthPackageId|String|cenbwp-4c2zaavbvh5x\*\*\*\*|The ID of the bandwidth package.

 |
|CenIds| |cen-xxjsjfkffkfkfjkf\*\*\*\*|The list of CEN instances associated with the bandwidth package.

 |
|CenId| | |The details of the CEN instance associated with the bandwidth package.

 |
|CreationTime|String|2019-02-01T11:14Z|The time when the bandwidth package was created. This parameter takes the ISO 8601 format. Format: YYYY-MM-DDThh:mmZ

 |
|Description|String|cen|The description of the bandwidth package.

 |
|ExpiredTime|String|2999-09-08T16:00Z|The time when the bandwidth package expires.

 |
|GeographicRegionAId|String|china|One of the connected areas of the bandwidth package.

 |
|GeographicRegionBId|String|north-america|The other connected area of the bandwidth package.

 |
|GeographicSpanId|String|north-america\_china|The area ID of the cross-area connection.

 |
|HasReservationData|String|false|Indicates whether renewal data is involved.

 -   **true**: Renewal data is involved.
-   **false**: No renewal data is involved.

 |
|IsCrossBorder|Boolean|false|Indicates whether the bandwidth package is a cross-border bandwidth package.

 -   **false**: The bandwidth package is not a cross-border bandwidth package.
-   **true**: The bandwidth package is a cross-border bandwidth package.

 |
|Name|String|test|The name of the bandwidth package.

 |
|OrginInterRegionBandwidthLimits| | |The list of of the connected regions.

 |
|OrginInterRegionBandwidthLimit| | |The details of the connected regions.

 |
|BandwidthLimit|String|1|The peak bandwidth of the connected regions.

 |
|GeographicSpanId|String|north-america\_china|The area ID of the cross-area connection to which the connected regions belong.

 |
|LocalRegionId|String|cn-hangzhou|The ID of the local region.

 |
|OppositeRegionId|String|us-west-1|The ID of the peer region.

 |
|Status|String|InUse|The association status of the bandwidth package.

 -   **Idle**: The bandwidth package is not associated with any CEN instance.
-   **InUse**: The bandwidth package is associated with one or more CEN instances.

 |
|PageNumber|Integer|1|The current page number.

 |
|PageSize|Integer|2|The number of entries per page.

 |
|RequestId|String|9D7E2400-2755-4AF5-9B73-12565E4F73A0|The ID of the request.

 |
|TotalCount|Integer|2|The total number of entries.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeCenBandwidthPackages
&<CommonParameters>

```

Response example

`XML` format

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

`JSON` format

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

## Errors { .section}

