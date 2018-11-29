# DescribeCenVbrHealthCheckRequest {#reference_i4w_xmt_ndb .reference}

Query the health check status of the leased line in a region.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeCenVbrHealthCheckRequest

 |
|VbrInstanceRegionId|String|Yes| The region of the VBR.

 You can query the region ID by calling the DescribeRegions API.

 |
|CenId|String|No|The ID of the CEN instance.|
|VbrInstanceId|String|No|The ID of the VBR.|
|VbrInstanceOwnerId|Long|No|The UID of the VBR.|
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
|HealthChecks|List|The detailed information of the health check.|

|Name|Type|Description|
|:---|:---|:----------|
|CenId|String|The ID of the CEN instance.|
|VbrInstanceId|String|The ID of the VBR.|
|HealthCheckSourceIp|String|The source IP address of the health check.|
|HealthCheckTargetIp|String|The destination IP address of the health check.|
|Delay|Camel|The delay.|
|Packetloss|Camel|The packet loss rate.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenVbrHealthCheck
&CenId=cen-kojok19x3j0q6kx5qf
&VbrInstanceRegionId=cn-shenzhen
&VbrInstanceId=vbr-wz95o9aylj181n5mzk8za
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DescribeCenVbrHealthCheckResponse>
        <HealthChecks>
            <HealthCheck>
                <CenId>Cen-atlpf6evc5kqchpma5</CenId>
                <VbrInstanceId>vbr-il7ldy0ux6rb15lc2snrw </VbrInstanceId >
                <HealthCheckSourceIp>10.10.10.10</HealthCheckSourceIp>
                <HealthCheckTargetIp>10.10.10.11</HealthCheckTargetIp>
                <Delay>3ms</Delay>
                <Packetloss>5%</Packetloss>
            </HealthCheck>
        </HealthChecks>
        <PageNumber>1</PageNumber>
        <TotalCount>1</TotalCount>
        <PageSize>10</PageSize>
        <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
    </DescribeCenVbrHealthCheckCheckResponse >
    ```

-   JSON format

    ```
    {
       "PageNumber":1,
       "TotalCount":1,
       "PageSize":10,
       "RequestId":"4D5E0433-363C-40DB-9A85-CF051ED1EB0F",
       "VbrHealthChecks":{
          "VbrHealthCheck":[
             {
                "VbrInstanceId":"vbr-wz95o9aylj181n5mzk8za",
                "CenId":"cen-kojok19x3j0q6kx5qf",
                "HealthCheckSourceIp":"192.168.1.2",
                "HealthCheckTargetIp":"10.0.0.2"
             }
          ]
       }
    }
    ```


