# AssociateCenBandwidthPackage {#reference_i4w_xmt_ndb .reference}

Bind a bandwidth package to a specified CEN instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 AssociateCenBandwidthPackage

 |
|CenId|String|Yes|The ID of the CEN instance.|
|CenBandwidthPackageId|String|Yes|The ID of the bandwidth package.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=AssociateCenBandwidthPackage
&CenId=cen-04sgjpvkc062ahzd26
&CenBandwidthPackageId=Cenbwp-stb2axpqzzko2ja
&Common parameters
```

**Responce example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <AssociateCenBandwidthPackageResponse>
        <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </AssociateCenBandwidthPackageResponse>
    ```

-   JSON format

    ```
    {
      "RequestId": "0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    }
    ```


