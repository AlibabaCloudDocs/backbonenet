# ModifyCenAttribute {#reference_i4w_xmt_ndb .reference}

Modify the name and description of a CEN instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|是| The action to perform. Valid value:

 ModifyCenAttribute

 |
|CenId|String|Yes| The ID of the CEN instance.

 |
|Name|String|No| The name of the instance.

 The name can contain \[2,128\] characters and numbers, underlines, and hyphens, and the name must start with English letters, but cannot start with `http://` or `https://`.

 |
|Description|String|No| The description of the instance.

 The description can contain \[2,256\] characters and must start with English letters, but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=ModifyCenAttribute
&CenId=cen-04sgjpvkc062ahzd26
&Name=cen1
&Common parameters
```

**Return example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <ModifyCenAttributeResponse>
         <RequestId>13526224-5780-4426-8BDF-BC8B08700F22</RequestId>
    </ModifyCenAttributeResponse>
    ```

-   JSON format

    ```
    
        "RequestId":"13526224-5780-4426-8BDF-BC8B08700F22"
    
    ```


