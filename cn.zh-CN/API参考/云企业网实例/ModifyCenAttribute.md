# ModifyCenAttribute {#reference_i4w_xmt_ndb .reference}

编辑云企业网实例的名称和描述信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyCenAttribute

 |
|CenId|String|是| 云企业网实例的ID。

 |
|Name|String|否| 云企业网实例的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 云企业网实例的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=ModifyCenAttribute
&CenId=cen-04sgjpvkc062ahzd26
&Name=cen1
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ModifyCenAttributeResponse>
         <RequestId>13526224-5780-4426-8BDF-BC8B08700F22</RequestId>
    </ModifyCenAttributeResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId":"13526224-5780-4426-8BDF-BC8B08700F22"
    }
    ```


