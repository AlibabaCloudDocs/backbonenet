# DescribeCenBandwidthPackages {#reference_i4w_xmt_ndb .reference}

Query the purchased bandwidth packages.

## Request parameters {#section_rny_k3p_tdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|是| The action to perform.  Valid value:

 DescribeCenBandwidthPackages

 |
|Filter.n.Key|String|No| Filter keys. Up to 5 filters can be specified. Valid value for n is \[1,5\].

 Each filter \(Filter Key\) You can provide multiple values, and there is an "or" Relationship between multiple values, that is, as long as it matches one of its values, it is considered a filter condition that meets the parameter.

 The logical relationship between filter keys is "and, that is, it meets all the parameters of the filter conditions, will be found out.

 The following filter conditions are supported: CenId \(ID of the cloud Enterprise Network instance\), Status \(The State of the bandwidth packet being used, idle/use \), \(CenBandwidthPackageIdID of bandwidth package\), nameName \(Name of bandwidth package\)

-   CenId: ID of the cloud Enterprise Network instance.

-   Status: the status used by the bandwidth package \(idle/ Inuse \).

-   CenBandwidthPackageIdMAID: ID of the bandwidth package.

-   Name: the name of the bandwidth package.


 |
|Filter.n.Value.m|String|No| The value of the corresponding filter key. Valid value for m is \[1,5\].

 |
|PageNumber|Integer|No| The number of pages to return. Default value is 1.

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
|CenIds|List|The ID of the CEN instance.|
|Name|String|The name of the bandwidth package.|
|Description|String|The description of the bandwidth package.|
|BusinessStatus|String|The billing status of the bandwidth package, including Normal, FinancialLocked, and SecurityLocked.|
|Status|String|The status of the bandwidth package in the CEN instance,  including Idle and InUse.|
|Bandwidth|Integer|The peak bandwidth of the bandwidth package.|
|CreationTime|String|The time at which the bandwidth package is created in the format of YYYY-MM-DDThh:mmZ.|
|BandwidthPackageChargeType|String| The billing method of the bandwidth package, including POSTPAY and PREPAY.|
|GeographicRegionAId|String|The interconnection area selected for the bandwidth package.|
|GeographicRegionBId|String|The other interconnection area selected for the bandwidth package.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenBandwidthPackage
&Common parameters
```

**Return example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
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
                <Businessstatus> normal </businessstatus>
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


