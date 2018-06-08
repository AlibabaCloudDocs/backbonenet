# DeleteCen {#reference_i4w_xmt_ndb .reference}

删除指定的云企业网实例。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DeleteCen

 |
|CenId|String|是| 云企业网实例的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DeleteCen
&CenId=cen-04sgjpvkc062ahzd26
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DeleteCenResponse>
        <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </DeleteCenResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId":"5903EE99-D542-4E14-BC65-AAC1CB2D3D03"
    }
    ```


