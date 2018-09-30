# SetCenInterRegionBandwidthLimit {#reference_i4w_xmt_ndb .reference}

Configure the cross-regional interconnection bandwidth. Ensure that you have added the interconnection regions to the CEN instance before configuring the bandwidth.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|是| The action to perform. Valid value:

 SetCenInterRegionBandwidthLimit

 |
|CenId|String|Yes| The ID of the CEN instance.|
|LocalRegionId|String|Yes|The ID of the local region.|
|OppositeRegionId|String|Yes|The ID of the other interconnected region.|
|BandWidthLimit|Long|Yes|The bandwidth configured for the interconnected regions communication.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=SetCenInterRegionBandwidthLimit
&CenId=cen-mkljagz6auhbzo7ayx
&LocalRegionId=cn-beijing
&OppositeRegionId=cn-shenzhen
&BandwidthLimit=1
&CommonParameters
```

**Return example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <SetCenInterRegionBandwidthLimitResponse>
       <RequestId>530BC816-F575-412A-AAB2-435125D26328</RequestId>
    </SetCenInterRegionBandwidthLimitResponse>
    ```

-   JSON format

    ```
    
       "RequestId":"530BC816-F575-412A-AAB2-435125D26328",
    
    ```


