# DetachCenChildInstance {#reference_i4w_xmt_ndb .reference}

从云企业网实例中解绑指定的网络实例。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DetachCenChildInstance

 |
|CenId|String|是|云企业网实例的ID。|
|ChildInstanceId|String|是|指定待解绑的网络实例ID。|
|ChildInstanceType|String|是|网络实例的类型。|
|ChildInstanceRegionId|String|是|网络实例所在的地域。|
|ChildInstanceOwnerId|LONG|否|网络实例所属账号的UID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DetachCenChildInstance
&CenId=vpc-hp3kz27b1uv9hsmm9vqiv
&ChildInstanceId=vpc-2zeki1et77fssihllb9s7
&ChildInstanceRegionId=cn-beijing
&ChildInstanceType=vpc
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DetachCenChildInstanceResponse>
         <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
    </DetachCenChildInstanceResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "0C2EE7A8-74D4-4081-8236-CEBDE3BBCF50"
    }
    ```


