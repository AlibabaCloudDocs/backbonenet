# DescribeRouteConflict {#reference_i4w_xmt_ndb .reference}

查看指定路由器（VRouter或VBR）中存在冲突的路由条目。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeRouteConflict

 |
|ChildInstanceRegionId|String|是|指定地域的ID。|
|ChildInstanceType|String|是|指定路由器类型，包括VRouter和VBR。|
|ChildInstanceRouteTableId|String|是|路由表的ID。|
|DestinationCidrBlock|String|否|目标网段的CIDR地址块。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|Integer|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|Integer|每页包含多少条目。|
|RouteConflicts|List|冲突路由条目的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|DestinationCidrBlock|String|路由条目的目标网段。|
|RegionId|String|地域的ID。|
|InstanceId|String|路由器的ID。|
|InstanceType|String|路由器的类型，VRouter或VBR。|
|Status|String|产生路由异常的原因：-   conflict：路由冲突。
-   overflow：其他网络实例路由表路由数量超出限制。
-   prohibited：VBR策略不允许的默认路由。

|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeRouteConflict
&ChildInstanceId=vpc-wz9fldmuq4v3g8gyp1qqy
&ChildInstanceType=VPC
&ChildInstanceRegionId=cn-shenzhen
&ChildInstanceRouteTableId=vrt-wz93gtdvt87w7cpff071n
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
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

-   JSON格式

    ```
    {
      "PageNumber": 1,
      "TotalCount": 0,
      "PageSize": 10,
      "RequestId": "B6C11547-2D56-4EEC-A8D5-FDC5A53E53D0",
      "RouteConflicts": {
        "RouteConflict": []
      }
    }
    ```


