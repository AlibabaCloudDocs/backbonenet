# DescribeCenRegionDomainRouteEntries {#reference_i4w_xmt_ndb .reference}

查询云企业网实例中某个地域内路由条目的详细信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeCenRegionDomainRouteEntries

 |
|CenId|String|是|指定待查询的云企业网实例的ID。|
|CenRegionId|String|是|指定待查询的地域的ID。|
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
|CenRouteEntries|List|路由条目的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|DestinationCidrBlock|String|路由条目的目标网段。|
|Type|String|路由条目的类型。|
|NextHopInstanceId|String|下一跳的网络实例（VPC或VBR）的ID。|
|NextHopType|String|下一跳的网络实例的类型，VBR或VPC。|
|NextHopRegionId|String|下一跳的网络实例所属地域的ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenRegionDomainRouteEntries
&CenId=cen-04sgjpvkc062ahzd26
&CenRegionId=cn-hangzhou
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    < DescribeCenRegionDomainRouteEntriesResponse>
        < Routes>
            < Route>
                <Source>
                    <RouteType>System</RouteType>
                    <RouterType>VRouter</RouterType>
                    <DstCidrBlock>10.10.100.0/24</DstCidrBlock>
                    <AliyunIdkp>1617256082593208</AliyunIdkp>
                    <RouterId>vpc-qn1eves08n7sk62vsj3ka</RouterId>
                    <RegionId>cn-hangzhou-668</RegionId>
                    <Nexthop></Nexthop>
                    <RouteTableId>vtb-qn1bindq4q7m30obbcyj0</RouteTableId>
                    <PropagationScope>CEN</PropagationScope>
                    <NexthopType>local</NexthopType>
                </Source>
            <RouteType>CEN</RouteType>
            <DstCidrBlock>10.10.100.0/24</DstCidrBlock>
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

-   JSON格式

    ```
    {
        "Routes":{
            "Route":[
                {"
                    "conflicts":[],
                    "dstCidrBlock":"10.10.100.0/24",
                    "nexthop":"",
                    "routeType":"CEN",
                    "source":{
                        "aliyunIdkp":"1617256082593208",
                        "dstCidrBlock":"10.10.100.0/24",
                        "nexthop":"",
                        "nexthopType":"local",
                        "propagationScope":"CEN",
                        "regionId":"cn-hangzhou-668",
                        "routeTableId":"vtb-qn1bindq4q7m30obbcyj0",
                        "routeType":"System",
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


