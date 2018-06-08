# DescribeCenInterRegionBandwidthLimits {#reference_i4w_xmt_ndb .reference}

查询各个地域之间的跨地域互通带宽。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeCenInterRegionBandwidthLimits

 |
|CenId|String|否| 指定查询该云企业网实例内的跨地域互通带宽。

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
|CenInterRegionBandwidthLimits|List|跨地域互连的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|CenId|String|云企业网实例的ID。|
|LocalRegionId|String|本端地域的ID。|
|OppositeRegionId|String|对端地域的ID。|
|Status|String|跨地域互通带宽的状态，包括Active和Modifying。|
|BandwidthLimit|Long|两个地域之间的跨地域互通带宽。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenInterRegionBandwidthLimits
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeCenInterRegionBandwidthLimitsResponse>
            <CenInterRegionBandwidthLimits>
                <CenInterRegionBandwidthLimit>
                <Status> Active </Status>
                    <LocalRegionId>cn-hangzhou-667</LocalRegionId>
                        <CenId>Cen-to55jjgdqd4pfvby3d</CenId>
                        <OppositeRegionId>cn-hangzhou-668</OppositeRegionId>
                        <BandwidthLimit>1000</BandwidthLimit>
                    </CenInterRegionBandwidthLimit>
                </CenInterRegionBandwidthLimits>
            <PageNumber>1</PageNumber>
            <TotalCount>1</TotalCount>
            <PageSize>10</PageSize>
        <RequestId>C4CF2E97-5C04-4A9E-B908-BE95FF68C7B2</RequestId>
    </DescribeCenInterRegionBandwidthLimitsResponse>
    ```

-   JSON格式

    ```
    {
        "CenInterRegionBandwidthLimits":{
            "CenInterRegionBandwidthLimit":[
                {"
                    Status":" Active ",
                    "LocalRegionId":"cn-hangzhou-667",
                    "CenId":"Cen-to55jjgdqd4pfvby3d",
                    "OppositeRegionId":"cn-hangzhou-668",
                    "BandwidthLimit":1000
                }
             ]
        },
        "PageNumber":1,
        "TotalCount":1,
        "PageSize":10,
        "RequestId":"187507F9-D955-41A5-98EB-7E4471F9D8E7"
    }
    ```


