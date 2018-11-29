# DescribeCenBandwidthPackages {#reference_i4w_xmt_ndb .reference}

Query all bandwidth packages under an account.

## Request parameters {#section_rny_k3p_tdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeCenBandwidthPackages

 |
|Filter.n.Key|String|No| Filter keys. Up to five filter keys are supported. The valid value of n is \[1,5\].

 You can provide multiple values for each filter key. The multiple values are of the "or" relation, that is, the filtering key is met as long as one value is met.

 The filter keys are of the "and" relation, that is, a result is found only when all filtering keys are met.

 The following filter conditions are supported: CenId \(the ID of the CEN instance\), Status \(The status of the bandwidth package, Idle/InUse \), CenBandwidthPackageId \(the ID of bandwidth package\) Name \(the name of the bandwidth package\)

-   CenId: The ID of the CEN instance.

-   Status: The status of the bandwidth package \(Idle/ InUse \).

-   CenBandwidthPackageId: The ID of the bandwidth package.

-   Name: The name of the bandwidth package.


 |
|Filter.n.Value.m|String|No| The value of the corresponding filter key. The valid value of m is \[1, 5\].

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|CenBandwidthPackages|List|A list of bandwidth packages.|

|Name|Type|Description|
|:---|:---|:----------|
|CenBandwidthPackageId|String|The ID of the bandwidth package.|
|CenIds|List|A list of CEN instances corresponding to the bandwidth package.|
|Name|String|The name of the bandwidth package.|
|Description|String|The description of the bandwidth package.|
|BusinessStatus|String|The billing status of the bandwidth package, including Normal, FinancialLocked, and SecurityLocked.|
|Status|String|The status of the bandwidth package in the CEN instance, including Idle and InUse.|
|Bandwidth|Integer|The peak bandwidth of the bandwidth package.|
|CreationTime|String|The time when the bandwidth package was created in the format of YYYY-MM-DDThh:mmZ.|
|BandwidthPackageChargeType|String|The billing method of the bandwidth package, including POSTPAY and PREPAY.|
|GeographicRegionAId|String|The interconnected area A associated with the bandwidth package.|
|GeographicRegionBId|String|The interconnected area B associated with the bandwidth package.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenBandwidthPackage
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DescribeCenBandwidthPackageResponse>
        <PageNumber>1</PageNumber>
        <TotalCount>1</TotalCount>
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
                <CenBandwidthPackageId>cenbwp-oq2ehpxq4zhwp790l7</CenBandwidthPackageId>
                <CenIds>
                    <CenId>cen-kojok19x3j0q6kx5qf</CenId>
                </CenIds>
                <ExpiredTime>2018-03-07T16:00Z</ExpiredTime>
                <Bandwidth>1</Bandwidth>
            </CnBandwidthPackage>
        </DescribeCenBandwidthPackageResponse>
    ```

-   JSON format

    ```
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
                "BusinessStatus":"Normal",
                "BandwidthPackageChargeType":"PREPAY",
                "GeographicRegionAId":"china",
                "CenBandwidthPackageId":"cenbwp-oq2ehpxq4zhwp790l7",
                "Cenids ":{
                   "Cenid ":[
                      "cen-kojok19x3j0q6kx5qf"
                   ]
                },
                "ExpiredTime":"2018-03-07T16:00Z",
                "Bandwidth":1
             }
          ]
       }
    }
    ```


