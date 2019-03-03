# DescribePublishedRouteEntries {#reference_xrs_fx2_h2b .reference}

Query the publish status of the route entries in the attached VPC or VBR.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform.  Valid value:

 DescribePublishedRouteEntries

 |
|CenId|String|Yes|The ID of the CEN instance to query.|
|ChildInstanceRegionId|String|Yes|The ID of the region where the attached network \(VBR or VPC\) is located.|
|ChildInstanceId|String|Yes|The ID of the network \(VBR or VPC\).|
|ChildInstanceRouteTableId|String|No|The ID of the route table of the VPC or VBR.|
|DestinationCidrBlock|String|No|The destination CIDR block of the route entry to query.|
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|PublishRouteEntries|List|The detailed information of the queried route entry in the specified region.|

|Name|Type|Description|
|:---|:---|:----------|
|ChildInstanceRouteTableId|String|The ID of the route table.|
|DestinationCidrBlock|String|The destination CIDR block of the route entry.|
|NextHopType|String| Type of the next hop. Values:

-   Instance: ECS instance \(Default\)
-   HaVip: High Availability Virtual IP \(HaVip\)
-   RouterInterface: Router interface

 |
|RouteType|String| Type of the route entry. Values:

-   System: System route entry
-   Custom: High Availability Virtual IP \(HaVip\)
-   BGP:  BGP route entry

 |
|OperationalMode|Boolean| Whether to allow the route entry to be published or removed to or from CEN:

-   true: Allow the route entry to be published or removed
-   false: Do not allow

 |
|NextHopId|String|The ID of the next hop.|
|PublishStatus|String|The publish status of the route entry in CEN:-   Published: Published
-   NonPublished: Not published

|
|Conflicts|List|A list of conflicted route entries.|

|Name|Type|Description|
|:---|:---|:----------|
|DestinationCidrBlock|String|The destination CIDR block of the conflicted route entry.|
|RegionId|String|The ID of the region where the conflicted route entry is located.|
|InstanceType|String| The type of the network.

 |
|Status|String|Reasons of exceptions:-   conflict: The route entry is conflicted with others.
-   overflow: The number of the route entry in other network exceeds the default limit.
-   prohibited: The route entry is not allowed in VBR.

|

## Example {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribePublishedRouteEntries
&ChildInstanceRegionId=cn-hangzhou-667
&CenId=cbn-3rh17kwhs6208rej85
&ChildInstanceId=vpc-il7krrmtp6elewp6426kr
&ChildInstanceType=VPC
&CommonRequestParameters
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
    {
      "TotalCount": 2, 
      "PublishRouteEntries": {
        "PublishRouteEntries": [
          {
            "DestinationCidrBlock": "100.64.0.0/10", 
            "NextHopId": "", 
            "NextHopType": "service", 
            "ChildInstanceRouteTableId": "vtb-il7qut3mjgtlcbpk2ie31", 
            "PublishStatus": "NonPublished", 
            "RouteConflicts": {
              "RouteConflicts": []
            }, 
            "RouteType": "System"
          }, 
          {
            "DestinationCidrBlock": "192.168.10.0/24", 
            "NextHopId": "", 
            "NextHopType": "local", 
            "ChildInstanceRouteTableId": "vtb-il7qut3mjgtlcbpk2ie31", 
            "PublishStatus": "Published", 
            "RouteConflicts": {
              "RouteConflicts": []
            }, 
            "RouteType": "System"
          }
        ]
      }, 
      "PageNumber": 1, 
      "RequestId": "FF1A7B2A-677F-4F71-96EA-6002B329F437", 
      "PageSize": 10
    }
    ```


