# RevokeInstanceFromCen {#reference_i4w_xmt_ndb .reference}

撤销网络实例对指定云企业网实例的授权。

**说明：** 该接口是VPC的API，所以调用该接口必须使用`vpc.aliyuncs.com`域名。API version为2016-04-28。

## 请求参数 {#section_yn4_rhp_tdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 RevokeInstanceFromCen

 |
|RegionId|String|是|网络实例所在的地域。|
|InstanceId|String|是|网络实例的ID。|
|InstanceType|String|是|网络实例的类型，包括VPC和VBR。|
|CenId|String|是|指定要授权的云企业网实例的ID。|
|CenOwnerId|String|是|云企业网实例所属账号的UID。|
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=RevokeInstanceFromCen
&CenId=cbn-6ugox0vl0zff4gl0b8
&CenOwnerId=1016647762843556
&InstanceId=vpc-o6wcsp5lcdf4b5kcdcytm
&RegionId=cn-hangzhou-test-306
&InstanceType=VPC
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <RevokeInstanceFromCenResponse>
        <RequestId>0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50</RequestId>
    </RevokeInstanceFromCenResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId":"0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    }
    ```


