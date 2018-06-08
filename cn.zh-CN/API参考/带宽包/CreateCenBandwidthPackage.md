# CreateCenBandwidthPackage {#reference_i4w_xmt_ndb .reference}

在使用云企业网连接不同地域的网络实例前，您需要根据网络实例所属的区域购买带宽包。

区域是阿里云地域的集合，云企业网的区域包括中国大陆、亚太、北美、欧洲。区域与地域的对应关系如下表所示：

|区域|包含的地域|
|:-|:----|
|中国大陆|华北1（青岛）、华北2（北京）、华北3（张家口）、华南1（深圳）、华东1（杭州）、华东2（上海）、华北5（呼和浩特）|
|北美|美国（硅谷）、美国（弗吉尼亚）|
|亚太|香港、新加坡、马来西亚（吉隆坡）、日本（东京）、印度（孟买）、印度尼西亚（雅加达）|
|欧洲|德国（法兰克福）|

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateCenBandwidthPackage

 |
|BandwidthPackageChargeType|String|否|带宽包的付费类型，取值：PrePaid|
|Bandwidth|String|是|带宽包的带宽峰值，单位为Mbps，最小值为1。|
|GeographicRegionAId|String|是| 网络实例所属的区域。

 取值：China | North-America | Asia-Pacific | Europe | Middle-East

 |
|GeographicRegionBId|String|是| 网络实例所属的区域。

 取值：China | North-America | Asia-Pacific | Europe | Middle-East

 |
|PricingCycle|String|是| 带宽包的计费周期。

 取值：Month | Year，默认值为Month。

 |
|Period|String|是|带宽包的购买时长，默认值为1。|
|AutoPay|String|否| 指定是否开启自动续费。

 取值：true | false，默认值为false。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|Name|String|否| 带宽包的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|CenId|String|否|指定与带宽包绑定的云企业网实例。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|CenBandwidthPackageId|String|新建带宽包的ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=CreateCenBandwidthPackage
&Bandwidth=2
&GeographicRegionAId=China
&GeographicRegionBId=China
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <CreateCenBandwidthPackageResponse>
        <RequestId>E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B</RequestId>
        <CenBandwidthPackageId> Cenbwp-stb2axpqzzko2jagd7</CenBandwidthPackageId>
    </CreateCenBandwidthPackageResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId":"E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B",
        "CenBandwidthPackageId":"Cenbwp-stb2axpqzzko2jagd7"
    }
    ```


