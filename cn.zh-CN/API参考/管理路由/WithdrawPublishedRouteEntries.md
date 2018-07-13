# WithdrawPublishedRouteEntries {#reference_ehn_cv2_h2b .reference}

解除VPC或VBR网络实例中已发布到CEN的路由。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 WithdrawPublishedRouteEntries

 |
|CenId|String|是|云企业网的ID。|
|ChildInstanceRegionId|String|是|加载的网络实例的地域ID。|
|ChildInstanceId|String|是|加载的网络实例ID（VPC或VBR ID）。|
|ChildInstanceType|String|是|网络实例类型，取值：-   VPC
-   VBR

|
|ChildInstanceRouteTableId|String|是|网络实例的路由表ID。|
|DestinationCidrBlock|String|是|要解除的已发布目标路由网段。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=WithdrawPublishedRouteEntries
&ChildInstanceRegionId=cn-hangzhou-667
&CenId=cbn-3rh17kwhs6208rej85
&DestinationCidrBlock=192.168.10.0/24
&ChildInstanceRouteTableId=vtb-il7qut3mjgtlcbpk2ie31
&ChildInstanceId=vpc-il7krrmtp6elewp6426kr
&ChildInstanceType=VPC
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <PublishRouteEntriesResponse>
        <RequestId>FBDB18D8-E91E-4978-8D6C-6E2E3EE101330</RequestId>
    </PublishRouteEntriesResponse>
    ```

-   JSON格式

    ```
    
    {
        "RequestId": "FBDB18D8-E91E-4978-8D6C-6E2E3EE10133"
    }
    
    
    ```


