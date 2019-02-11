# DescribePublishedRouteEntries {#reference_xrs_fx2_h2b .reference}

查询加载到CEN中的网络实例\(VPC和VBR\)各条路由明细在CEN中的发布情况

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribePublishedRouteEntries

 |
|CenId|String|是|需要查询的云企业网ID。|
|ChildInstanceRegionId|String|是|需要查询的地域ID。|
|ChildInstanceId|String|是|网络实例ID。|
|ChildInstanceType|String|是|网络实例类型，取值：-   VPC：专有网络
-   VBR：边界路由器接口

|
|ChildInstanceRouteTableId|String|否|网络实例的路由表ID。|
|DestinationCidrBlock|String|否|要查询的网段。|
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
|PublishRouteEntries|List|返回指定的云企业网的指定的region的路由信息。|

|名称|类型|描述|
|:-|:-|:-|
|ChildInstanceRouteTableId|String|路由表ID。|
|DestinationCidrBlock|String|目标网段。|
|NextHopType|String| 下一跳的类型等，取值：

-   Instance：ECS实例（默认值）
-   HaVip：高可用虚拟IP
-   RouterInterface：路由器接口

 |
|RouteType|String| 路由条目的类型，取值：

-   System：系统路由
-   Custom：高可用虚拟IP
-   BGP：BGP路由

 |
|OperationalMode|Boolean| 是否允许发布或撤销该路由到CEN：

-   true：允许发布或撤销
-   false：不允许

 |
|NextHopId|String|下一跳实例的ID。|
|PublishStatus|String|在CEN中的发布状态：-   Published：已发布
-   Non-Published：未发布

|
|RouteConflicts|String \(JSON Array\)|冲突路由列表。|

|名称|类型|描述|
|:-|:-|:-|
|DestinationCidrBlock|String|冲突目标网段地址。|
|RegionId|String|冲突实例所在的地域ID。|
|InstanceId|String|冲突实例ID。|
|InstanceType|String| 网络实例类型。

 |
|Status|String|异常原因：-   conflict：路由发生冲突
-   overflow：其他网络实例路由表路由数量超出限制
-   prohibited：VBR策略不允许的默认路由

|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}

http://cbn.aliyuncs.com?Action=DescribePublishedRouteEntries
&ChildInstanceRegionId=cn-hangzhou-667
&CenId=cbn-3rh17kwhs6208rej85
&ChildInstanceId=vpc-il7krrmtp6elewp6426kr
&ChildInstanceType=VPC
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


