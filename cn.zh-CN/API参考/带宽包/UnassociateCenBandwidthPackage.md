# UnassociateCenBandwidthPackage {#reference_i4w_xmt_ndb .reference}

将带宽包与云企业网实例之间的绑定取消。取消绑定后，该带宽包可以绑定至其他云企业网实例。

## 请求参数 {#section_cch_pjg_mdb .section}

|删除

名称|类型|是否必须|描述|
|:-----|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 UnassociateCenBandwidthPackage

 |
|CenId|String|是|云企业网实例的ID。|
|CenBandwidthPackageId|String|是|带宽包的ID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=UnassociateCenBandwidthPackage
&CenId=cen-04sgjpvkc062ahzd26
&CenBandwidthPackageId=Cenbwp-stb2axpqzzko2ja
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <UnassociateCenBandwidthPackageResponse>
        <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </UnassociateCenBandwidthPackageResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    }
    ```


