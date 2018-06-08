# ModifyCenBandwidthPackageAttribute {#reference_i4w_xmt_ndb .reference}

编辑带宽包的名称和描述信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyCenBandwidthPackageAttribute

 |
|CenBandwidthPackageId|String|是| 带宽包的ID。

 |
|Name|String|否| 带宽包的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 带宽包的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=ModifyCenBandwidthPackageAttribute
&CenBandwidthPackageId=cenbwp-oq2ehpxq4zhwp790l7
&Name=china
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifyCenBandwidthPackageAttributeResponse>
         <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </ModifyCenBandwidthPackageAttributeResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId":"13526224-5780-4426-8ADF-BC8B08700F23"
    }
    ```


