# GrantInstanceToCen {#reference_i4w_xmt_ndb .reference}

Authorize CEN to attach the network that belongs to another account.

**Note:** This API is an API of VPC. Therefore, the endpoint of the API is vpc.aliyuncs.com and  the API version is 2016-04-28.

## Request parameters {#section_av2_ghp_tdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|是| The action to perform.  Valid value:

 GrantInstanceToCen

 |
|RegionId|String|Yes|The ID of the region where the network is located.|
|InstanceId|String|Yes|The ID of the network to authorize.|
|InstanceType|String|Yes|The type of the network. Valid value: VPC | VBR|
|CenId|String|Yes|The ID of the CEN instance to which the network is attached.|
|CenOwnerId|String|Yes|The account ID of the CEN instance to which the authorized network is attached.|
|ClientToken|String|No| A client token used to ensure the idempotence of requests. 

 For more information, see Ensure idempotence.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=GrantInstanceToCen
&CenId=cen-wvzsvi8ujffj95h1i4
&CenOwnerId=1086496381294461
&InstanceId=vpc-t4nsmy2lskkven1nfawzg
&RegionId=ap-southeast-1
&InstanceType=VPC
&Common parameters
```

**Return example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <GrantInstanceToCenResponse>
        <RequestId>0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50</RequestId>
    </GrantInstanceToCenResponse>
    ```

-   JSON format

    ```
    {
      "RequestId": "0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    }
    ```


