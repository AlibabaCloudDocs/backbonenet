# DescribeGeographicRegionMembership {#reference_i4w_xmt_ndb .reference}

Query regions in a specified area.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action |String| Yes| The action to perform. Valid value: 

 DescribeGeographicRegionMembership

 |
|GeographicRegionId|String| Yes| The ID of the specified area. Valid value:

-   china
-   asia-pacific
-   europe
-   australia
-   north-america

 |

|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name |Type|Description|
|:----|:---|:----------|
|RequestId|String |The ID of the request.|
|Totalcount|String |The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String |The number of entries on the current page.|
|RegionIds|List|A list of regions in the specified area.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeGeographicRegionMembership
&GeographicRegionId=north-america
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
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

-   JSON format

    ```
    {
       "RegionIds":{
          "Regionid ":[
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


