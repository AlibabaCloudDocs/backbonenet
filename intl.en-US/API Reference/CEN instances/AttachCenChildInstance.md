# AttachCenChildInstance {#reference_i4w_xmt_ndb .reference}

Attach a network \(VPC or VBR\) to a CEN instance. The attached networks \(VPC or VBR\) can communicate with each other.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform.  Valid value:

 AttachCenChildInstance

 |
|CenId|String|Yes|The ID of the CEN instance.|
|ChildInstanceId|String|Yes|The ID of the network to attach.|
|ChildInstanceType|String|Yes|The type of the network to attach.|
|ChildInstanceRegionId|String|Yes|The ID of the region where the network is located. The ID of the region where the network is located.|
|ChildInstanceOwnerId|String|No|The account ID to which the network belongs.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=AttachCenChildInstance
& Cenid = vpc-hp3kz27b1uv9hsmm9vqiv
&ChildInstanceId=vpc-2zeki1et77fssihllb9s7
&ChildInstanceRegionId=cn-beijing
&ChildInstanceType=vpc
&Common parameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <AttachCenChildInstanceResponse>
        <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
    </AttachCenChildInstanceResponse>
    ```

-   JSON format

    ```
    
        "RequestId":"A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A"
    
    ```


