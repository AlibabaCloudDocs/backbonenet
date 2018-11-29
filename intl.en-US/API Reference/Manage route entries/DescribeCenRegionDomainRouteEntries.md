# DescribeCenRegionDomainRouteEntries {#reference_i4w_xmt_ndb .reference}

Query the detailed information of CEN routes, including from which region and which network instance this route is learned.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform.  Valid value:

 DescribeCenRegionDomainRouteEntries

 |
|CenId|String|Yes| The ID of the CEN instance to query.|
|CenRegionId|String|Yes|The ID of the region to query.|
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
|CenRouteEntries|List|The detailed information of CEN route entries.|

|Name|Type|Description|
|:---|:---|:----------|
|DestinationCidrBlock|String|The destination CIDR block of the route entry.|
|Type|String|The type of the route entry. The default value is CEN.|
|NextHopInstanceId|String|The ID of the next hop.|
|NextHopType|String|The type of the next hop, VPC or VBR.|
|NextHopRegionId|String|The ID of the region where the next hop is located.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenRegionDomainRouteEntries
&CenId=cen-04sgjpvkc062ahzd26
&CenRegionId=cn-hangzhou
&Common parameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    < DescribeCenRegionDomainRouteEntriesResponse>
        < Routes>
            < Route>
                <Source>
                    <Routetype> System </routetype>
                    <RouterType>VRouter</RouterType>
                    <Dstcidrblock> 10.10.100.0/24 </dstcidrblock>
                    <Aliyunidkp> 1617256082593208 </aliyunidkp>
                    <RouterId>vpc-qn1eves08n7sk62vsj3ka</RouterId>
                    <RegionId>cn-hangzhou-668</RegionId>
                    <Nexthop></Nexthop>
                    <RouteTableId>vtb-qn1bindq4q7m30obbcyj0</RouteTableId>
                    <PropagationScope>CEN</PropagationScope>
                    <NexthopType>local</NexthopType>
                </Source>
            <Routetype> CEN </routetype>
            <Dstcidrblock> 10.10.100.0/24 </dstcidrblock>
            <Nexthop></Nexthop>
            <Conflicts /> 
            </ Route>
        </ Routes>
    <PageNumber>1</PageNumber>
    <TotalCount>1</TotalCount>
    <PageSize>10</PageSize>
    <RequestId>C4CF2E97-5C04-4A9E-B908-BE95FF68C7B2</RequestId>
    </ DescribeCenRegionDomainRouteEntriesResponse>
    ```

-   JSON format

    ```
    {
        "Routes":{
            "Route":[
                {\"
                    "conflicts":[],
                    "Maid": "maid/24 ",
                    "nexthop":"",
                    "Routetype": "CEN ",
                    "source":{
                        "aliyunIdkp":"1617256082593208",
                        "dstCidrBlock":"10.10.100.0/24",
                        "nexthop":"",
                        "nexthopType":"local",
                        "Propagation scope": "CEN ",
                        "regionId":"cn-hangzhou-668",
                        "routeTableId":"vtb-qn1bindq4q7m30obbcyj0",
                        "Routetype": "system ",
                        "routerId":"vpc-qn1eves08n7sk62vsj3ka",
                        "routerType":"VRouter"
                    }
                }
             ]
        },
        "PageNumber":1,
        "TotalCount":1,
        "PageSize":10,
        "RequestId":"187507F9-D955-41A5-98EB-7E4471F9D8E7"
    }
    ```


