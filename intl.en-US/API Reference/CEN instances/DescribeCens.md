# DescribeCens {#reference_i4w_xmt_ndb .reference}

Query all CEN instances under an account.

## Request parameters {#section_erd_vfp_tdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeCens

 |
|Filter.n.Key|String|No| Filter keys. Up to five filter keys are supported. The valid value of n is \[1,5\].

 You can provide multiple values for each filter key. The multiple values are of the "or" relation, that is, the filtering key is met as long as one value is met.

 The filter keys are of the "and" relation, that is, a result is found only when all filtering keys are met.

 The following are available filter keys:

-   CenId: The ID of the CEN instance.

-   Name: The name of the CEN instance.

-   CenBandwidthPackageId: The ID of the bandwidth package.


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
|Cens|List|A list of CEN instances.|

|Name|Type|Description|
|:---|:---|:----------|
|CenId|String|The ID of the CEN instance.|
|Name|String|The name of the CEN instance.|
|Status|String|The status of the CEN instance, including Creating, Active, and Deleting.|
|CenBandwidthPackageIds|List|A list of bandwidth packages.|
|Description|String|The description of the CEN instance.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCens
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DescribeCensResponse>
    <Cens>
          <Cen>
                <CenBandwidthPackageIds>
                   <CenBandwidthPackageId>
                      <CenBandwidthPackageId>cenbwp-oq2ehpxq4zhwp790l7</CenBandwidthPackageId>
                      <CenBandwidthPackageId>cenbwp-18qmj0bahl3yskktho</CenBandwidthPackageId>
                   </CenBandwidthPackageId>
                </CenBandwidthPackageIds>
                <CenId>cen-kojok19x3j0q6kx5qf</CenId>
                <Description>jzwne 0207</Description>
                <Name>jzwen_0207_01</Name>
                <Status>Active</Status>
             </Cen>
             <Cen>
                <CenBandwidthPackageIds>
                   <CenBandwidthPackageId>
                      <CenBandwidthPackageId>cenbwp-3o2zy4s6jig88pn325</CenBandwidthPackageId>
                      <CenBandwidthPackageId>cenbwp-hq2ad760htrr7r5vlp</CenBandwidthPackageId>
                   </CenBandwidthPackageId>
                </CenBandwidthPackageIds>
                <CenId>cen-mkljagz6auhbzo7ayx</CenId>
                <Name>jzwen_crossaccount_01</Name>
                <Status>Active</Status>
             </Cen>
    </Cens>
    <PageNumber>1</PageNumber>
    <PageSize>10</PageSize>
    <RequestId>145F96AB-3EE9-4DCA-991C-726F96CC5703</RequestId>
    <TotalCount>4</TotalCount>
    </DescribeCensResponse>
    ```

-   JSON format

    ```
    {
      "PageNumber": 1,
      "Cens": {
        "Cen": [
          {
            "Name": "jzwen_0207_01",
            "Status": "Active",
            "Description": "jzwne 0207",
            "CenBandwidthPackageIds": {
              "CenBandwidthPackageId": [
                "cenbwp-oq2ehpxq4zhwp790l7",
                "cenbwp-18qmj0bahl3yskktho"
              ]
            },
            "CenId": "cen-kojok19x3j0q6kx5qf"
          },
          {
            "Name": "jzwen_crossaccount_01",
            "Status": "Active",
            "CenBandwidthPackageIds": {
              "CenBandwidthPackageId": [
                "cenbwp-3o2zy4s6jig88pn325",
                "cenbwp-hq2ad760htrr7r5vlp"
              ]
            },
            "CenId": "cen-mkljagz6auhbzo7ayx"
          }
        ]
      },
      "TotalCount": 4,
      "PageSize": 10,
      "RequestId": "145F96AB-3EE9-4DCA-991C-726F96CC5703"
    }
    ```


