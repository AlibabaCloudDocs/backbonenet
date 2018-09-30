# DeleteCen {#reference_i4w_xmt_ndb .reference}

Delete a CEN instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|是| The action to perform. Valid value:

 DeleteCen

 |
|CenId|String|Yes| The ID of the CEN instance.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DeleteCen
&CenId=cen-04sgjpvkc062ahzd26
&Common parameters
```

**Return example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DeleteCenResponse>
        <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </DeleteCenResponse>
    ```

-   JSON format

    ```
    
        "RequestId":"5903EE99-D542-4E14-BC65-AAC1CB2D3D03"
    
    ```


