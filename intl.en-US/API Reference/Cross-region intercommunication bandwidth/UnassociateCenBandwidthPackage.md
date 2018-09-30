# UnassociateCenBandwidthPackage {#reference_i4w_xmt_ndb .reference}

Unbind a bandwidth package from a CEN instance.  You can bind the bandwidth package to another CEN instance after it is unbounded.

## Request Parameters {#section_cch_pjg_mdb .section}

|Delete

Name|Type|Required|Description|
|:-----------|:---|:-------|:----------|
|Action|String|是| The action to perform: Valid value:

 UnassociateCenBandwidthPackage

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
https://cbn.aliyuncs.com/?Action=UnassociateCenBandwidthPackage
&CenId=cen-04sgjpvkc062ahzd26
&CenBandwidthPackageId=Cenbwp-stb2axpqzzko2ja
&Common parameters
```

**Return example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <UnassociateCenBandwidthPackageResponse>
        <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </UnassociateCenBandwidthPackageResponse>
    ```

-   JSON format

    ```
    {
      "RequestId": "0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    }
    ```


