# EnableCenVbrHealthCheck {#reference_i4w_xmt_ndb .reference}

Enable the health check of VBR to timely detect faulty physical connections.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|是| The action to perform. Valid value:

 EnableCenVbrHealthCheck

 |
|CenId|String|Yes|The ID of the CEN instance.|
|VbrInstanceRegionId|String|Yes| The region of the VBR.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|VbrInstanceId|String|Yes|The ID of the VBR.|
|HealthCheckSourceIp|String|Yes|The source IP address of the health check.|
|HealthCheckTargetIp|String|Yes|The destination IP address of the health check.|
|VbrInstanceOwnerId|Long|No|The UID of the VBR.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=EnableCenVbrHealthCheck
&CenId=cen-kojok19x3j0q6kx5qf
&VbrInstanceRegionId=cn-shenzhen
&VbrInstanceId=vbr-wz95o9aylj181n5mzk8za
&HealthCheckSourceIp=192.168.1.2
&HealthCheckTargetIp=10.0.0.2
&CommonParameters
```

**Return example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <EnableCenVbrHealthCheckResponse>
        <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
        <CenId>Cen-atlpf6evc5kqchpma5</CenId>
        <VbrId>vbr-il7ldy0ux6rb15lc2snrw </VbrId>
        <RegionId>cn-hangzhou</RegionId>
        <SourceIp>10.10.10.10</SourceIp>
        <TargetIp>10.10.10.11</TargetIp>
        <PacketNum>3</PacketNum>
        <Status>Enable </Status>
    </EnableCenVbrHealthCheckResponse>
    ```

-   JSON format

    ```
    
      "RequestId": "A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A",
      "CenId": "Cen-atlpf6evc5kqchpma5",
      "VbrId": "vbr-il7ldy0ux6rb15lc2snrw",
      "RegionId": "cn-hangzhou",
      "SourceIp": "10.10.10.10",
      "TargetIp": "10.10.10.11",
      "PacketNum": "3",
      "Status": "Enable"
    
    ```


