# DetachCenChildInstance {#reference_i4w_xmt_ndb .reference}

Detach a specified network from a CEN instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String |Required| The action to perform. Valid value: 

 DetachCenChildInstance

 |
|CenId|String |Required|The ID of the CEN instance.|
|Childinstanceid|String|Yes|The ID of the network to attach.|
|ChildInstanceType|String |Required|The type of the network to attach.|
|ChildInstanceRegionId|String |Required|The ID of the region where the network is located.|
|ChildInstanceOwnerId|Long|No|The account ID to which the network belongs.|
|ChildInstanceOwnerId|Long|No|The account ID to which the CEN instance belongs.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name |Type|Required|
|:----|:---|:-------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DetachCenChildInstance
&CenId=vpc-hp3kz27b1uv9hsmm9vqiv
&ChildInstanceId=vpc-2zeki1et77fssihllb9s7
&ChildInstanceRegionId=cn-beijing
&ChildInstanceType=vpc
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DetachCenChildInstanceResponse>
         <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </DetachCenChildInstanceResponse>
    ```

-   JSON format

    ```
    {
      "RequestId": "0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    }
    ```


