# DescribeCenBandwidthPackages {#reference_i4w_xmt_ndb .reference}

查看账户下所有带宽包的详细信息。

## 请求参数 {#section_rny_k3p_tdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeCenBandwidthPackages

 |
|Filter.n.Key|String|否| 过滤条件，最多可提供5个过滤条件。n的取值范围为\[1,5\]。

 每个过滤条件（filter key）可以提供多个值，多个值之间是“or”关系，即只要与其中一个值符合则视为符合参数的过滤条件。

 各个过滤条件（filter key）之间为“and”逻辑关系，即符合所有参数的过滤条件，才会被查询出来。

 支持的过滤条件如下：CenId（云企业网实例的ID），Status （带宽包被使用的状态Idle/ InUse）， CenBandwidthPackageId（带宽包的ID），Name （带宽包的名称）

-   CenId：云企业网实例的ID。

-   Status：带宽包被使用的状态（Idle/ InUse）。

-   CenBandwidthPackageId：带宽包的ID。

-   Name：带宽包的名称。


 |
|Filter.n.Value.m|String|否| 指定的过滤条件对应的值。m的取值范围为\[1，5\]。

 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|CenBandwidthPackages|List|带宽包的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|CenBandwidthPackageId|String|带宽包的ID。|
|CenIds|List|带宽包对应的云企业网实例的列表。|
|Name|String|带宽包的名称。|
|Description|String|带宽包的描述信息。|
|BusinessStatus|String|带宽包的状态，包括Normal、FinancialLocked和SecurityLocked。|
|Status|String|带宽包在云企业网中的状态。包括Idle和InUse。|
|Bandwidth|Integer|带宽包的峰值带宽。|
|CreationTime|String|带宽包的创建时间，采用ISO8601格式表示，格式为：YYYY-MM-DDThh:mmZ。|
|BandwidthPackageChargeType|String|带宽包的付费类型，包括POSTPAY和PREPAY。|
|GeographicRegionAId|String|参与互连的区域。|
|GeographicRegionBId|String|参与互连的区域。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenBandwidthPackage
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeCenBandwidthPackageResponse>
        <PageNumber>1</PageNumber>
        <TotalCount>5</TotalCount>
        <PageSize>10</PageSize>
        <RequestId>9D7E2400-2755-4AF5-9B73-12565E4F73A0</RequestId>
        <CenBandwidthPackages>
            <CenBandwidthPackage>
                <CreationTime>2018-02-07T02:19Z</CreationTime>
                <Status>InUse</Status>
                <GeographicRegionBId>china</GeographicRegionBId>
                <BusinessStatus>Normal</BusinessStatus>
                <BandwidthPackageChargeType>PREPAY</BandwidthPackageChargeType>
                <GeographicRegionAId>china</GeographicRegionAId>
                <CenBandwidthPackageId>cenbwp-oq2ehpxq4zhwp790l7</CenBandwidthPackageId>
                <CenIds>
                    <CenId>cen-kojok19x3j0q6kx5qf</CenId>
                </CenIds>
                <ExpiredTime>2018-03-07T16:00Z</ExpiredTime>
                <Bandwidth>1</Bandwidth>
            </CnBandwidthPackage>
        </DescribeCenBandwidthPackageResponse>
    ```

-   JSON格式

    ```
    {
       "PageNumber":1,
       "TotalCount":5,
       "PageSize":10,
       "RequestId":"9D7E2400-2755-4AF5-9B73-12565E4F73A0",
       "CenBandwidthPackages":{
          "CenBandwidthPackage":[
             {
                "CreationTime":"2018-02-07T02:19Z",
                "Status":"InUse",
                "GeographicRegionBId":"china",
                "BusinessStatus":"Normal",
                "BandwidthPackageChargeType":"PREPAY",
                "GeographicRegionAId":"china",
                "CenBandwidthPackageId":"cenbwp-oq2ehpxq4zhwp790l7",
                "CenIds":{
                   "CenId":[
                      "cen-kojok19x3j0q6kx5qf"
                   ]
                },
                "ExpiredTime":"2018-03-07T16:00Z",
                "Bandwidth":1
             }
          ]
       }
    }
    ```


