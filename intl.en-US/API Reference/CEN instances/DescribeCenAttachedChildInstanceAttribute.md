# DescribeCenAttachedChildInstanceAttribute {#reference_i4w_xmt_ndb .reference}

Query the detailed information of networks \(VPC, VBR, CCN\) attached to the CEN instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeCenAttachedChildInstances

 |
|CenId|String|Yes| The ID of the CEN instance.

 |
|ChildInstanceRegionId|String|Yes| The region ID of the attached network.

 |
|ChildInstanceId|String|Yes| The ID of the attached network to query.

 |
|ChildInstanceType|String|Yes| The type of the attached network.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|CenId|String|The ID of the CEN instance.|
|ChildInstanceId|String|The ID of the network.|
|ChildInstanceType|String|The type of the network.|
|ChildInstanceRegionId|String|The region ID of the network.|
|ChildInstanceOwnerId|String|The ID of the user to whom the network belongs.|
|Status|String|The attaching status of the network.|
|ChildInstanceAttachTime|String|The time when the network was attached.|
|ChildInstanceName|String|The name of the network.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}

http://cen.aliyuncs.com/?Action= DescribeCenAttachedChildInstanceAttribute
&ChildInstanceRegionId=cn-hangzhou-test-306
&CenId=cen-3cub0ges01xmvmefma
&ChildInstanceType=VPC
&ChildInstanceId=vpc-sa17uy0itvgxiq9gbmiju
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
    <DescribeCenAttachedChildInstanceAttribute>
      <Status>Attached</Status>
      <ChildInstanceOwnerId>1196226963299553</ChildInstanceOwnerId>
      <ChildInstanceId>vpc-2zebdboka7d7t37vo2i7n</ChildInstanceId>
      <RequestId>ADD98358-D265-4060-87CB-A2427F5A8944</RequestId>
      <ChildInstanceName>defaultvpc</ChildInstanceName>
      <ChildInstanceRegionId>cn-beijing</ChildInstanceRegionId>
      <CenId>cen-5mv960yjhja0dh7qsb</CenId>
      <ChildInstanceAttachTime>2018-07-30T07:53Z</ChildInstanceAttachTime>
      <ChildInstanceType>VPC</ChildInstanceType>
    </DescribeCenAttachedChildInstanceAttribute>
    
    ```

-   JSON format

    ```
    {
        "Status": "Attached", 
        "ChildInstanceOwnerId": "1196226963299553", 
        "ChildInstanceId": "vpc-2zebdboka7d7t37vo2i7n", 
        "RequestId": "ADD98358-D265-4060-87CB-A2427F5A8944", 
        "ChildInstanceName": "defaultvpc", 
        "ChildInstanceRegionId": "cn-beijing", 
        "CenId": "cen-5mv960yjhja0dh7qsb", 
        "ChildInstanceAttachTime": "2018-07-30T07:53Z", 
        "ChildInstanceType": "VPC"
    }}
    
    ```


