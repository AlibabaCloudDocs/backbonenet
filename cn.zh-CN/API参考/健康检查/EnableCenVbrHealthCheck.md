# EnableCenVbrHealthCheck {#reference_i4w_xmt_ndb .reference}

开启边界路由器（VBR）的健康检查，确保及时发现出现故障的物理专线。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 EnableCenVbrHealthCheck

 |
|CenId|String|是|云企业网实例的ID。|
|VbrInstanceRegionId|String|是| VBR所在的地域。

 您可以通过调用DescribeRegions接口查询地域ID。

 |
|VbrInstanceId|String|是|VBR的ID。|
|HealthCheckSourceIp|String|是|健康检查的源IP地址。|
|HealthCheckTargetIp|String|是|健康检查的目的IP地址。|
|VbrInstanceOwnerId|Long|否|VBR所属账户的UID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=EnableCenVbrHealthCheck
&CenId=cen-kojok19x3j0q6kx5qf
&VbrInstanceRegionId=cn-shenzhen
&VbrInstanceId=vbr-wz95o9aylj181n5mzk8za
&HealthCheckSourceIp=192.168.1.2
&HealthCheckTargetIp=10.0.0.2
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <EnableCenVbrHealthCheckResponse>
        <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
        <CenId>Cen-atlpf6evc5kqchpma5</CenId>
        <VbrId>vbr-il7ldy0ux6rb15lc2snrw </VbrId>
        <RegionId>cn-hangzhou</RegionId>
        <SourceIp>10.10.10.10</SourceIp>
        <TargetIp>10.10.10.11</TargetIp>
        <PacketNum>3</PacketNum>
        <Status>Enable </Status>
    </EnableCenVbrHealthCheckResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A",
      "CenId": "Cen-atlpf6evc5kqchpma5",
      "VbrId": "vbr-il7ldy0ux6rb15lc2snrw",
      "RegionId": "cn-hangzhou",
      "SourceIp": "10.10.10.10",
      "TargetIp": "10.10.10.11",
      "PacketNum": "3",
      "Status": "Enable"
    }
    ```


