# SetCenInterRegionBandwidthLimit {#reference_i4w_xmt_ndb .reference}

设置带宽包中两个地域间的跨地域互通带宽。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 SetCenInterRegionBandwidthLimit

 |
|CenId|String|是|云企业网实例的ID。|
|LocalRegionId|String|是|本端地域的ID。|
|OppositeRegionId|String|是|对端地域的ID。|
|BandWidthLimit|Long|是|指定地域间互连的带宽峰值。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=SetCenInterRegionBandwidthLimit
&CenId=cen-mkljagz6auhbzo7ayx
&LocalRegionId=cn-beijing
&OppositeRegionId=cn-shenzhen
&BandwidthLimit=1
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <SetCenInterRegionBandwidthLimitResponse>
       <RequestId>530BC816-F575-412A-AAB2-435125D26328</RequestId>
    </SetCenInterRegionBandwidthLimitResponse>
    ```

-   JSON格式

    ```
    {
       "RequestId":"530BC816-F575-412A-AAB2-435125D26328",
    }
    ```


