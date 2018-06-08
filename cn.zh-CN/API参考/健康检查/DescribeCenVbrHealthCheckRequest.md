# DescribeCenVbrHealthCheckRequest {#reference_i4w_xmt_ndb .reference}

查询指定地域内物理专线健康检查的状态。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeCenVbrHealthCheckRequest

 |
|VbrInstanceRegionId|String|是| VBR所在的地域。

 您可以通过调用DescribeRegions接口查询地域ID。

 |
|CenId|String|否|云企业网实例的ID。|
|VbrInstanceId|String|否|VBR的ID。|
|VbrInstanceOwnerId|Long|否|VBR所属账户的UID。|
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
|HealthChecks|List|健康检查的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|CenId|String|云企业网实例的ID。|
|VbrInstanceId|String|VBR的ID。|
|HealthCheckSourceIp|String|健康检查的源IP地址。|
|HealthCheckTargetIp|String|健康检查的目的IP地址。|
|Delay|Camel|时延。|
|Packetloss|Camel|丢包率。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenVbrHealthCheck
&CenId=cen-kojok19x3j0q6kx5qf
&VbrInstanceRegionId=cn-shenzhen
&VbrInstanceId=vbr-wz95o9aylj181n5mzk8za
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeCenVbrHealthCheckResponse>
        <HealthChecks>
            <HealthCheck>
                <CenId>Cen-atlpf6evc5kqchpma5</CenId>
                <VbrInstanceId>vbr-il7ldy0ux6rb15lc2snrw </VbrInstanceId >
                <HealthCheckSourceIp>10.10.10.10</HealthCheckSourceIp>
                <HealthCheckTargetIp>10.10.10.11</HealthCheckTargetIp>
                <Delay>3ms</Delay>
                <Packetloss>5%</Packetloss>
            </HealthCheck>
        </HealthChecks>
        <PageNumber>1</PageNumber>
        <TotalCount>1</TotalCount>
        <PageSize>10</PageSize>
        <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
    </DescribeCenVbrHealthCheckCheckResponse >
    ```

-   JSON格式

    ```
    {
       "PageNumber":1,
       "TotalCount":1,
       "PageSize":10,
       "RequestId":"4D5E0433-363C-40DB-9A85-CF051ED1EB0F",
       "VbrHealthChecks":{
          "VbrHealthCheck":[
             {
                "VbrInstanceId":"vbr-wz95o9aylj181n5mzk8za",
                "CenId":"cen-kojok19x3j0q6kx5qf",
                "HealthCheckSourceIp":"192.168.1.2",
                "HealthCheckTargetIp":"10.0.0.2"
             }
          ]
       }
    }
    ```


