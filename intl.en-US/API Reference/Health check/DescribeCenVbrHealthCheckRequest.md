# DescribeCenVbrHealthCheckRequest {#reference_i4w_xmt_ndb .reference}

Queries the status of a health check for a physical line within a specified region.

## Request Parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required or not|Description|
|:---|:---|:--------------|:----------|
|Action|String|是| The operation to perform. Value:

 DescribeCenVbrHealthCheckRequest

 |
|VbrInstanceRegionId|String|Yes| The region where the VBR is located.

 You can query the Region ID by calling the descriptions interface.

 |
|CenId|String|No|ID of the cloud Enterprise Network instance.|
|VbrInstanceId|String|No|ID of the VBR.|
|VbrInstanceOwnerId|Long|No|UID of the account to which the VBR belongs.|
|PageNumber|Integer|No| The page number of the list. Default: 1.

 |
|PageSize|Integer|No| Maximum: 50，Default: 10。

 |

## Return Parameters {#section_ugs_f1g_cz .section}

|Parameters|Type|Description|
|:---------|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|Number of entries in the list.|
|Pagenumber|Integer|Current page.|
|PageSize|String|How many entries each page contains.|
|HealthChecks|List|Details of the health check.|

|Name|Type|Description|
|:---|:---|:----------|
|CenId|String|ID of the cloud Enterprise Network instance.|
|VbrInstanceId|String|ID of the VBR.|
|Healthchecksourceip|String|The source IP address of the health check.|
|HealthCheckTargetIp|String|The destination IP address of the health check.|
|Delay|Camel|Delay.|
|Packetloss|Camel|Packet Loss Rate.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenVbrHealthCheck
&CenId=cen-kojok19x3j0q6kx5qf
&VbrInstanceRegionId=cn-shenzhen
&VbrInstanceId=vbr-wz95o9aylj181n5mzk8za
&Public request parameter
```

**Return example**

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
        <Pagenumber> 1 </pagenumber>
        <TotalCount>1</TotalCount>
        <PageSize>10</PageSize>
        <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
    </DescribeCenVbrHealthCheckCheckResponse >
    ```

-   JSON format

    ```
    
       "PageNumber":1,
       "TotalCount":1,
       "PageSize":10,
       "RequestId":"4D5E0433-363C-40DB-9A85-CF051ED1EB0F",
       "VbrHealthChecks":{
          "VbrHealthCheck":[
             
                "VbrInstanceId":"vbr-wz95o9aylj181n5mzk8za",
                "CenId":"cen-kojok19x3j0q6kx5qf",
                "Healthchecksourceip": "192.168.1.2 ",
                "HealthCheckTargetIp":"10.0.0.2"
             
          
       
    
    ```


