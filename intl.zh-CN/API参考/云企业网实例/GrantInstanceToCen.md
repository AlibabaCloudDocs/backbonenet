# GrantInstanceToCen {#reference_i4w_xmt_ndb .reference}

在加载其他账号的网络实例前，需要在网络实例所在的账号下为云企业网实例授权。

**说明：** 该接口使用专有网络VPC的endpoint \(vpc.aliyuncs.com\)，VPC API的版本为2016-04-28。

## 请求参数 {#section_av2_ghp_tdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
| Action|String|是| 要执行的操作。 取值：

  GrantInstanceToCen 

 |
| RegionId|String|是|网络实例所在的地域。|
| InstanceId|String|是|网络实例的ID。|
| InstanceType|String|是|网络实例的类型，包括VPC和VBR。|
| CenId|String|是|指定要授权的云企业网实例的ID。|
| CenOwnerId|String|是|云企业网实例所属账号的UID。|
| ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
| RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

 **请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=GrantInstanceToCen
&CenId=cen-wvzsvi8ujffj95h1i4
&CenOwnerId=108649638129****
&InstanceId=vpc-t4nsmy2lskkven1nf****
&RegionId=ap-southeast-1
&InstanceType=VPC
&公共请求参数
```

 **返回示例** 

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <GrantInstanceToCenResponse>
        <RequestId>0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50</RequestId>
    </GrantInstanceToCenResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    }
    ```


