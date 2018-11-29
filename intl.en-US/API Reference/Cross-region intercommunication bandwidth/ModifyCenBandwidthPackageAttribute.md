# ModifyCenBandwidthPackageAttribute {#reference_i4w_xmt_ndb .reference}

Modify the name and description of a bandwidth package.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 ModifyCenBandwidthPackageAttribute

 |
|CenBandwidthPackageId|String|Yes| The ID of the bandwidth package.

 |
|Name|String|No| The name of the bandwidth package.

 The name can contain \[2,128\] characters and numbers, underscores, and hyphens, and the name must start with English letters, but cannot start with `http://` or `https://`.

 |
|Description|String|No| The description of the bandwidth package.

 The description can contain \[2,256\] characters, numbers, underscores, and hyphens, and the name must start with English letters, but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=ModifyCenBandwidthPackageAttribute
&CenBandwidthPackageId=cenbwp-oq2ehpxq4zhwp790l7
&Name=china
&Common parameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
    <ModifyCenBandwidthPackageAttributeResponse>
         <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </ModifyCenBandwidthPackageAttributeResponse>
    ```

-   JSON format

    ```
    
        "RequestId":"13526224-5780-4426-8ADF-BC8B08700F23"
    
    ```


