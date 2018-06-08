# DisableCenVbrHealthCheck {#reference_i4w_xmt_ndb .reference}

关闭指定边界路由器（VBR）的健康检查。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DisableCenVbrHealthCheck

 |
|CenId|String|是|云企业网实例的ID。|
|VbrInstanceRegionId|String|是| VBR所在的地域。

 您可以通过调用DescribeRegions接口查询地域ID。

 |
|VbrInstanceId|String|是|VBR的ID。|
|VbrInstanceOwnerId|Long|否|VBR所属账户的UID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DisableCenVbrHealthCheck
&CenId=cen-kojok19x3j0q6kx5qf
&VbrInstanceRegionId=cn-shenzhen
&VbrInstanceId=vbr-wz95o9aylj181n5mzk8za
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DisableCenVbrHealthCheckResponse>
        <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
    </DisableCenVbrHealthCheckCheckResponse >
    ```

-   JSON格式

    ```
    {
        "RequestId":"A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A"
    }
    ```


