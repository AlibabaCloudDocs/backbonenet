# CreateCenBandwidthPackage {#doc_api_Cbn_CreateCenBandwidthPackage .reference}

调用CreateCenBandwidthPackage创建带宽包。

## API描述 {#description .section}

在使用云企业网连接不同地域的网络实例前，您需要根据网络实例所属的区域创建带宽包。

区域是阿里云地域的集合，云企业网的区域包括中国大陆、亚太、北美、欧洲、澳洲。区域与地域的对应关系如下表所示：

|区域

|包含的地域

|
|----|-------|
|中国大陆

|华北1（青岛）、华北2（北京）、华北3（张家口）、华南1（深圳）、华东1（杭州）、华东2（上海）、华北5（呼和浩特）

|
|北美

|美国（硅谷）、美国（弗吉尼亚）

|
|亚太

|中国（香港）、新加坡、马来西亚（吉隆坡）、日本（东京）、印度尼西亚（雅加达）、印度（孟买）

|
|欧洲

|德国（法兰克福）、英国（伦敦）

|
|澳洲

|澳大利亚（悉尼）

|

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=CreateCenBandwidthPackage&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Bandwidth|Integer|是|2|带宽包的带宽峰值，单位为Mbps，最小值为**2**。

 |
|GeographicRegionAId|String|是|China|网络实例所属的区域，取值：

 **China | North-America | Asia-Pacific | Europe | Australia**。

 |
|GeographicRegionBId|String|是|China|网络实例所属的区域，取值：

 **China | North-America | Asia-Pacific | Europe | Australia**。

 |
|Action|String|否|CreateCenBandwidthPackage|要执行的操作，取值：**CreateCenBandwidthPackage**。

 |
|ClientToken|String|否|SSJFLAFHHFHFF-SJSJJFBWHHE-SHHFJJDBD|客户端token，用于保证请求的幂等性。由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII字符。

 |
|Name|String|否|cen|带宽包的名称。长度为2~128个字符，必须以字母或中文开头，可包含数字、点号（.）、下划线（\_）和短横线（-），但不能以`http://`或`https://`开头。

 |
|Description|String|否|带宽包|带宽包描述。

 |
|BandwidthPackageChargeType|String|否|PREPAY|带宽包的付费类型，取值：

 -   **POSTPAY**：后付费。
-   **PREPAY**：预付费。

 **说明：** 国际站仅支持预付费。

 |
|Period|Integer|否|1|带宽包的购买时长，默认值为**1**。

 |
|PricingCycle|String|否|Month|带宽包的计费周期，取值：

 -   **Month**（默认值）：按月计费。
-   **Year**：按年计费。

 |
|AutoPay|Boolean|否|true|是否自动支付账单，取值：

 -   **true**：自动支付。
-   **false**（默认值）：不自动支付。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CenBandwidthPackageId|String|cenbwp-4c2zaavbvh5fx\*\*\*\*|新建带宽包的ID。

 |
|CenBandwidthPackageOrderId|String|201564200040390|带宽包的订单ID。

 |
|RequestId|String|6547D2DA-4383-46A0-9E39-BA324492AD9F|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateCenBandwidthPackage
&Bandwidth=2
&GeographicRegionAId=China 
&GeographicRegionBId=China 
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateCenBandwidthPackageResponse>
      <RequestId>E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B</RequestId>
      <CenBandwidthPackageOrderId>201564200040390</CenBandwidthPackageOrderId>
      <CenBandwidthPackageId> Cenbwp-stb2axpqzzko2j****</CenBandwidthPackageId>
</CreateCenBandwidthPackageResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"CenBandwidthPackageOrderId":"201564200040390",
	"RequestId":"E4B345CD-2CBA-4881-AF6D-E5D9BAE1CA7B",
	"CenBandwidthPackageId":"Cenbwp-stb2axpqzzko2j****"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|UnSupported.ChargeType|The charge type is not supported.|不支持该付费类型|

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

