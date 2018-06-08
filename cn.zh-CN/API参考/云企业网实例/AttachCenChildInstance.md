# AttachCenChildInstance {#reference_i4w_xmt_ndb .reference}

将网络实例加载到云企业网实例中，网络实例包括VPC和边界路由器（VBR）。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 AttachCenChildInstance

 |
|CenId|String|是|云企业网实例的ID。|
|ChildInstanceId|String|是|指定待加载的网络实例的ID。|
|ChildInstanceType|String|是|网络实例的类型。|
|ChildInstanceRegionId|String|是|网络实例所在的地域。|
|ChildInstanceOwnerId|LONG|否|跨账号加载场景下，网络实例所属账号的UID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=AttachCenChildInstance
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
    <AttachCenChildInstanceResponse>
        <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
    </AttachCenChildInstanceResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId":"A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A"
    }
    ```


