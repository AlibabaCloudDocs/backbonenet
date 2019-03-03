# CreateCen {#reference_i4w_xmt_ndb .reference}

在使用云企业网前，需要创建云企业网实例。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateCen

 |
|Name|String|否| 云企业网实例的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 云企业网实例的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|CenId|String|新建的云企业网实例的ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=CreateCen
&RegionId=cn-hangzhou
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateCenResponse>
         <CenId> Cen-dc4vwznpwbobrlcm6w </CenId>
         <RequestId>0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50</RequestId>
    </CreateCenResponse>
    ```

-   JSON格式

    ```
    {
           "CenId":"Cen-dc4vwznpwbobrlcm6w",
           "RequestId":"0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    }
    ```


