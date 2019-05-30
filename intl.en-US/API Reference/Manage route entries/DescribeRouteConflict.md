# DescribeRouteConflict {#reference_i4w_xmt_ndb .reference}

Query the conflicted route entries in the specified VRouter or VBR.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeRouteConflict

 |
|ChildInstanceRegionId|String|Yes|Specify the ID of the region where the network \(VPC or VBR\) is located.|
|ChildInstanceType|String|Yes|Specify the instance type. Valid value: VPC | VBR.|
|ChildInstanceId|String|Yes|The instance ID of the attached network.|
|ChildInstanceRouteTableId|String|Yes|The ID of the router table.|
|DestinationCidrBlock|String|No|The destination CIDR block.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|RouteConflicts|List|The detailed information of conflicted route entries.|

|Name|Type|Description|
|:---|:---|:----------|
|DestinationCidrBlock|String|The destination CIDR block of the route entry.|
|Regionid|String|The ID of the region.|
|InstanceId|String|The ID of the VRouter or the VBR.|
|InstanceType|String|The instance type, VPC or VBR.|
|Status|String|The status of the route entry: -   conflict: The route entry is in conflict.
-   overflow: The number of router entries in other network instances exceeds the limit.
-   prohibited: The route entry is not allowed by VBR.

 |

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeRouteConflict
&ChildInstanceId=vpc-wz9fldmuq4v3g8gyp1qqy
&ChildInstanceType=VPC
&ChildInstanceRegionId=cn-shenzhen
&ChildInstanceRouteTableId=vrt-wz93gtdvt87w7cpff071n
& Common parameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DescribeRouteConflictResponse>
        <PageNumber>1</PageNumber>
        <PageSize>10</PageSize>
        <RequestId>B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0</RequestId>
        <RouteConflicts>
            <RouteConflict/>
        </RouteConflicts>
        <TotalCount>0</TotalCount>
    </DescribeRouteConflictResponse>
    ```

-   JSON format

    ```
    
    
      "PageNumber": 1,
      "TotalCount": 0,
      "PageSize": 10,
      "RequestId": "B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0",
      "RouteConflicts": {
        "RouteConflict": []
      }
    					
    ```


