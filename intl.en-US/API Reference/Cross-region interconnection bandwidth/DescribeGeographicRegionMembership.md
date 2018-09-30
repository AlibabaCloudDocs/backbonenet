# DescribeGeographicRegionMembership {#reference_i4w_xmt_ndb .reference}

Query the regions in a specified area.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Require|Description|
|:---|:---|:------|:----------|
|Action|String|是| The action to perform. Valid value:

 DescribeGeographicRegionMembership

 |
|GeographicRegionId|String|Yes| The ID of the area to query.

 |
|PageNumber|Integer|No| The number of pages to return. Default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|Request ID.|
|Totalcount|String|The number of list entries.|
|Pagenumber|Integer|The current page number.|
|Pagesize|String|The number of entries contained in the current page.|
|Regionids|List|A list of regions included in the specified area.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeGeographicRegionMembership
&GeographicRegionId=North-America
&Common parameters
```

**Return example**

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
       </Regionids>
       <RequestId>DC9EB0C9-60AF-4A09-A36C-608F70130274</RequestId>
       <TotalCount>2</TotalCount>
       <TotalCount>6</TotalCount>
    </FIG>
    ```

-   JSON format

    ```
    
       "RegionIds":{
          "Regionid ":[
             
                "RegionId":"us-west-1"
             
             
                "RegionId":"us-east-1"
             
          
       
       "PageNumber":1,
       "TotalCount":2,
       "PageSize":10,
       "RequestId":"DC9EB0C9-60AF-4A09-A36C-608F70130274"
    
    ```


