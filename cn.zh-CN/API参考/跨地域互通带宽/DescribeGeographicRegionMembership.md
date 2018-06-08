# DescribeGeographicRegionMembership {#reference_i4w_xmt_ndb .reference}

查看指定区域内所有的地域。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeGeographicRegionMembership

 |
|GeographicRegionId|String|是| 指定区域的ID。

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
|RegionIds|List|地域的详细信息。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeGeographicRegionMembership
&GeographicRegionId=North-America
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeGeographicRegionMembershipResponse>
       <PageNumber>1</PageNumber>
       <PageSize>10</PageSize>
       <RegionIds>
          <RegionId>
                <RegionId>us-west-1</RegionId>
             </RegionId>
             <RegionId>
                <RegionId>us-east-1</RegionId>
             </RegionId>
       </RegionIds>
       <RequestId>DC9EB0C9-60AF-4A09-A36C-608F70130274</RequestId>
       <TotalCount>2</TotalCount>
       <TotalCount>6</TotalCount>
    </DescribeGeographicRegionMembershipResponse>
    ```

-   JSON格式

    ```
    {
       "RegionIds":{
          "RegionId":[
             {
                "RegionId":"us-west-1"
             },
             {
                "RegionId":"us-east-1"
             }
          ]
       },
       "PageNumber":1,
       "TotalCount":2,
       "PageSize":10,
       "RequestId":"DC9EB0C9-60AF-4A09-A36C-608F70130274"
    }
    ```


