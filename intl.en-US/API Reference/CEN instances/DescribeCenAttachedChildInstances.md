# DescribeCenAttachedChildInstances {#reference_i4w_xmt_ndb .reference}

Query the networks attached to a CEN instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type| Required|Description|
|:---|:---|:--------|:----------|
|Action|String|Yes| The action to perform.  Valid value:

 DescribeCenAttachedChildInstances

 |
|CenId|String|Yes| The ID of the CEN instance.

 |
|ChildInstanceType|String|否|The type of the network instance. Valid value: VPC|VBR|CCN.|
|ChildInstanceRegionId|String|No|The region ID of the attached network.|
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|ChildInstances|List|A list of the attached networks.|

|Name|Type|Description|
|:---|:---|:----------|
|CenId|String|The ID of the CEN instance.|
|ChildInstanceId|String|The ID of the network.|
|ChildInstanceType|String|The type of the network.|
|ChildInstanceRegionId|String|The ID of the region where the network is located.|
|Status|Status|The status of the network: attaching, attached, and detaching.|
|ChildInstanceOwnerId|Long|The account ID to which the network belongs.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenAttachedChildInstances
&CenId=cen-kojok19x3j0q6kx
&Common parameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DescribeCenAttachedChildInstancesResponse>
       <ChildInstances <ChildInstance>
                <CenId>cen-kojok19x3j0q6kx5qf</CenId>
                <ChildInstanceId>vpc-hp3kz27b1uv9hsmm9vqiv</ChildInstanceId>
                <ChildInstanceOwnerId>1894573272823690</ChildInstanceOwnerId>
                <ChildInstanceRegionId>cn-huhehaote</ChildInstanceRegionId>
                <ChildInstanceType>VPC</ChildInstanceType>
                <Status>Attached</Satus>
            </ChildIntance>
            <ChildInstance>
                <CenId>cen-kojok19x3j0q6kx5qf</CenId>
                <ChildInstanceId>vpc-gw85r5kr8urw957szm455</ChildInstanceId>
                <ChildInstanceOwnerId>1894573272823690</ChildInstanceOwnerId>
                <ChildInstanceRegionId>eu-central-1</ChildInstanceRegionId>
                <ChildInstanceType>VPC</ChildInstanceType>
                <Status>Attched</Status>
        e>
          </ChildInstance>
       </ChildInstances>
       <PageNumber>1</PageNumber>
       <PageSize>10</PageSize>
       <RequestId>50F8E0AB-A225-41C0-AC88-FFB51A4F5C72</RequestId>
       <TotalCount>3</TotalCount>
    </DescribeCenAttachedChildInstancesResponse>
    ```

-   JSON format

    ```
    {
       "PageNumber":1,
       "ChildInstances":{
          "ChildInstance":[
             {
                "Status":"Attached",
                "ChildInstanceOwnerId":"1894573272823690",
                "ChildInstanceId":"vpc-hp3kz27b1uv9hsmm9vqiv",
                "ChildInstanceRegionId":"cn-huhehaote",
                "CenId":"cen-kojok19x3j0q6kx5qf",
                "ChildInstanceType":"VPC"
             },
             {
                "Status":"Attached",
                "ChildInstanceOwnerId":"1894573272823690",
                "ChildInstanceId":"vpc-gw85r5kr8urw957szm455",
                "ChildInstanceRegionId":"eu-central-1",
                "CenId":"cen-kojok19x3j0q6kx5qf",
                "ChildInstanceType":"VPC"
             }
          ]
       },
       "TotalCount":3,
       "PageSize":10,
       "RequestId":"50F8E0AB-A225-41C0-AC88-FFB51A4F5C72"
    }
    ```


