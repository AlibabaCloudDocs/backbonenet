# DescribeGrantRulesToCen {#reference_i4w_xmt_ndb .reference}

查看网络实例对云企业网实例的授权关系。

**说明：** 该接口是VPC的API，所以调用该接口必须使用`vpc.aliyuncs.com`域名。API version为2016-04-28。

## 请求参数 {#section_dmr_mhp_tdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeGrantRulesToCen

 |
|RegionId|String|是|网络实例所在的地域。|
|InstanceId|String|是|网络实例的ID。|
|InstanceType|String|是|网络实例的类型，包括VPC和VBR。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|CenGrantRules|List|授权规则的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|CenId|String|云企业网实例的ID。|
|CenOwnerId|String|云企业网实例所属账户的UID。|
|CreationTime|String|授权规则的创建时间，采用ISO8601标准表示，格式为：YYYY-MM-DDThh:mmZ。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeGrantRulesToCen
&InstanceId=vpc-o6wcsp5lcdf4b5kcdcytm
&RegionId=cn-hangzhou-test-306
&InstanceType=VPC
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeGrantRulesToCenResponse>
        <TotalCount>1</TotalCount>
        <PageNumber>1</PageNumber>
        <CbnGrantRules>
            <CbnGrantRule>
                <CbnInstanceId>cbn-6ugox0vl0zff4gl0b8</CbnInstanceId>
                <CbnOwnerId>1016647762843556</CbnOwnerId>
                <CreationTime>2018-01-18T11:49:09Z</CreationTime>
            </CbnGrantRule>
        </CbnGrantRules>
        <PageSize>10</PageSize>
        <RequestId>330714D1-F335-4CE2-9D29-F54445937387</RequestId>
    </DescribeGrantRulesToCenResponse>
    ```

-   JSON格式

    ```
    {
      "TotalCount": 1,
      "PageNumber": 1,
      "CbnGrantRules": {
        "CbnGrantRule": [
          {
            "CbnInstanceId": "cbn-6ugox0vl0zff4gl0b8",
            "CbnOwnerId": 1016647762843556,
            "CreationTime": "2018-01-18T11:49:09Z"
          }
        ]
      },
      "PageSize": 10,
      "RequestId": "330714D1-F335-4CE2-9D29-F54445937387"
    }
    ```


