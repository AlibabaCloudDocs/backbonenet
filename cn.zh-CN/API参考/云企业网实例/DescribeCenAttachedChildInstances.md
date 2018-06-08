# DescribeCenAttachedChildInstances {#reference_i4w_xmt_ndb .reference}

查看云企业网实例下已加载的网络实例。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeCenAttachedChildInstances

 |
|CenId|String|是| 指定云企业网实例的ID。

 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|Cens|List|云企业网实例的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|CenId|String|云企业网实例的ID。|
|ChildInstanceId|String|网络实例的ID。|
|ChildInstanceType|String|网络实例的类型，包括VPC和VBR。|
|ChildInstanceRegionId|String|网络实例所在的地域。|
|Status|Status|网络实例的状态，包括attaching、attached和detaching。|
|ChildInstanceOwnerId|Long|网络实例所属账号的UID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=DescribeCenAttachedChildInstances
&CenId=cen-kojok19x3j0q6kx
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeCenAttachedChildInstancesResponse>
       <ChildInstances        <ChildInstance>
                <CenId>cen-kojok19x3j0q6kx5qf</CenId>
                <ChildInstanceId>vpc-hp3kz27b1uv9hsmm9vqiv</ChildInstanceId>
                <ChildInstanceOwnerId>1894573272823690</ChildInstanceOwnerId>
                <ChildInstanceRegionId>cn-huhehaote</ChildInstanceRegionId>
                <ChildInstanceType>VPC</ChildInstanceType>
                <Status>Attached</Satus>
            </ChildIntance>
            <ChildInstance>
                <CenId>cen-kojok19x3j0q6kx5qf</CenId>
                <ChildInstanceId>vpc-gw85r5kr8urw957szm455</ChildInstanceId>
                <ChildInstanceOwnerId>1894573272823690</ChildInstanceOwnerId>
                <ChildInstanceRegionId>eu-central-1</ChildInstanceRegionId>
                <ChildInstanceType>VPC</ChildInstanceType>
                <Status>Attched</Status>
        e>
          </ChildInstance>
       </ChildInstances>
       <PageNumber>1</PageNumber>
       <PageSize>10</PageSize>
       <RequestId>50F8E0AB-A225-41C0-AC88-FFB51A4F5C72</RequestId>
       <TotalCount>3</TotalCount>
    </DescribeCenAttachedChildInstancesResponse>
    ```

-   JSON格式

    ```
    {
       "PageNumber":1,
       "ChildInstances":{
          "ChildInstance":[
             {
                "Status":"Attached",
                "ChildInstanceOwnerId":"1894573272823690",
                "ChildInstanceId":"vpc-hp3kz27b1uv9hsmm9vqiv",
                "ChildInstanceRegionId":"cn-huhehaote",
                "CenId":"cen-kojok19x3j0q6kx5qf",
                "ChildInstanceType":"VPC"
             },
             {
                "Status":"Attached",
                "ChildInstanceOwnerId":"1894573272823690",
                "ChildInstanceId":"vpc-gw85r5kr8urw957szm455",
                "ChildInstanceRegionId":"eu-central-1",
                "CenId":"cen-kojok19x3j0q6kx5qf",
                "ChildInstanceType":"VPC"
             }
          ]
       },
       "TotalCount":3,
       "PageSize":10,
       "RequestId":"50F8E0AB-A225-41C0-AC88-FFB51A4F5C72"
    }
    ```


