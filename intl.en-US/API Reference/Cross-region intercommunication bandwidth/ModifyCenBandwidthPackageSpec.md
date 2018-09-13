# ModifyCenBandwidthPackageSpec {#reference_i4w_xmt_ndb .reference}

Modify the bandwidth of a bandwidth package.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|是| The action to perform. Valid value:

 ModifyCenBandwidthPackageSpec

 |
|CenBandwidthPackageId|String|Yes|The ID of the bandwidth package.|
|Bandwidth|String|Yes|The bandwidth in Mbps set for the bandwidth package. The minimum value is 2 Mbps.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=ModifyCenBandwidthPackageSpec
&CenBandwidthPackageId=cenbwp-oq2ehpxq4zhwp790l7
&Bandwidth=10
&Common parameters
```

**Return example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <ModifyCenBandwidthPackageSpecResponse>
         <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </ModifyCenBandwidthPackageSpecResponse>
    ```

-   JSON format

    ```
    
      "RequestId": "0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    
    ```


