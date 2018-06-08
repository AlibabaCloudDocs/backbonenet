# ModifyCenBandwidthPackageSpec {#reference_i4w_xmt_ndb .reference}

更改带宽包的带宽值。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyCenBandwidthPackageSpec

 |
|CenBandwidthPackageId|String|是|带宽包的ID。|
|Bandwidth|String|是|带宽包的带宽峰值，单位为Mbps。10Mbps起售。-   带宽峰值为10 - 100Mbps时，步长为10Mbps。
-   带宽峰值为100 - 2000Mbps时，步长为100Mbps。
-   带宽峰值为2000 - 10000Mbps时，步长为500Mbps。

|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=ModifyCenBandwidthPackageSpec
&CenBandwidthPackageId=cenbwp-oq2ehpxq4zhwp790l7
&Bandwidth=10
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ModifyCenBandwidthPackageSpecResponse>
         <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </ModifyCenBandwidthPackageSpecResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    }
    ```


