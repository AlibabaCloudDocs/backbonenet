# DescribeCens {#reference_i4w_xmt_ndb .reference}

查看账户下所有云企业网实例的详细信息。

## 请求参数 {#section_erd_vfp_tdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeCens

 |
|Filter.n.Key|String|否| 过滤条件，最多可提供5个过滤条件。n的取值范围为\[1,5\]。

 每个过滤条件（filter key）可以提供多个值，多个值之间是“or”关系，即只要与其中一个值符合则视为符合参数的过滤条件。

 各个过滤条件（filter key）之间为“and”逻辑关系，即符合所有参数的过滤条件，才会被查询出来。

 支持的过滤条件如下：

-   CenId：云企业网实例的ID。

-   Name：云企业网实例的名称。

-   CenBandwidthPackageId：带宽包的ID。


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
|Cens|List|云企业网实例的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|CenId|String|云企业网实例的ID。|
|Name|String|云企业网实例的名称|
|Status|String|云企业网实例的状态，包括Creating、Active和Deleting。|
|CenBandwidthPackageIds|List|已绑定的带宽包的列表。|
|Description|String|云企业网实例的描述信息。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCens
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeCensResponse>
    <Cens>
          <Cen>
                <CenBandwidthPackageIds>
                   <CenBandwidthPackageId>
                      <CenBandwidthPackageId>cenbwp-oq2ehpxq4zhwp790l7</CenBandwidthPackageId>
                      <CenBandwidthPackageId>cenbwp-18qmj0bahl3yskktho</CenBandwidthPackageId>
                   </CenBandwidthPackageId>
                </CenBandwidthPackageIds>
                <CenId>cen-kojok19x3j0q6kx5qf</CenId>
                <Description>jzwne 0207</Description>
                <Name>jzwen_0207_01</Name>
                <Status>Active</Status>
             </Cen>
             <Cen>
                <CenBandwidthPackageIds>
                   <CenBandwidthPackageId>
                      <CenBandwidthPackageId>cenbwp-3o2zy4s6jig88pn325</CenBandwidthPackageId>
                      <CenBandwidthPackageId>cenbwp-hq2ad760htrr7r5vlp</CenBandwidthPackageId>
                   </CenBandwidthPackageId>
                </CenBandwidthPackageIds>
                <CenId>cen-mkljagz6auhbzo7ayx</CenId>
                <Name>jzwen_crossaccount_01</Name>
                <Status>Active</Status>
             </Cen>
    </Cens>
    <PageNumber>1</PageNumber>
    <PageSize>10</PageSize>
    <RequestId>145F96AB-3EE9-4DCA-991C-726F96CC5703</RequestId>
    <TotalCount>4</TotalCount>
    </DescribeCensResponse>
    ```

-   JSON格式

    ```
    {
      "PageNumber": 1,
      "Cens": {
        "Cen": [
          {
            "Name": "jzwen_0207_01",
            "Status": "Active",
            "Description": "jzwne 0207",
            "CenBandwidthPackageIds": {
              "CenBandwidthPackageId": [
                "cenbwp-oq2ehpxq4zhwp790l7",
                "cenbwp-18qmj0bahl3yskktho"
              ]
            },
            "CenId": "cen-kojok19x3j0q6kx5qf"
          },
          {
            "Name": "jzwen_crossaccount_01",
            "Status": "Active",
            "CenBandwidthPackageIds": {
              "CenBandwidthPackageId": [
                "cenbwp-3o2zy4s6jig88pn325",
                "cenbwp-hq2ad760htrr7r5vlp"
              ]
            },
            "CenId": "cen-mkljagz6auhbzo7ayx"
          }
        ]
      },
      "TotalCount": 4,
      "PageSize": 10,
      "RequestId": "145F96AB-3EE9-4DCA-991C-726F96CC5703"
    }
    ```


