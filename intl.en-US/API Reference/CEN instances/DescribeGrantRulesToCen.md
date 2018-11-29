# DescribeGrantRulesToCen {#reference_i4w_xmt_ndb .reference}

Query the networks that have been authorized to CEN.

**Note:** This API is an API of VPC. Therefore, the endpoint of the API is`vpc.aliyuncs.com` and the API  version is 2016-04-28.

## Request parameters {#section_dmr_mhp_tdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform.  Valid value:

 DescribeGrantRulesToCen

 |
|RegionId|String|Yes|The ID of the region where the network is located.|
|InstanceId|String|Yes|The ID of the network.|
|InstanceType|String|Yes|The type of the network. Valid value: VPC | VBR|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|CenGrantRules|List|A list of the authorized networks.|

|Name|Type|Description|
|:---|:---|:----------|
|CenId|String|The ID of the CEN instance.|
|CenOwnerId|String|The account ID that the network belongs to.|
|CreationTime|String|The time at which the network instance is authorized in the format of YYYY-MM-DDThh:mmZ.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeGrantRulesToCen
&InstanceId=vpc-o6wcsp5lcdf4b5kcdcytm
&RegionId=cn-hangzhou-test-306
&InstanceType=VPC
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DescribeGrantRulesToCenResponse>
        <TotalCount>1</TotalCount>
        <PageNumber>1</PageNumber>
        <CbnGrantRules>
            <CbnGrantRule>
                <CbnInstanceId>cbn-6ugox0vl0zff4gl0b8</CbnInstanceId>
                <Cbnownerid> 1016647762843556 </cbnownerid>
                <CreationTime>2018-01-18T11:49:09Z</CreationTime>
            </CbnGrantRule>
        </CbnGrantRules>
        <PageSize>10</PageSize>
        <RequestId>330714D1-F335-4CE2-9D29-F54445937387</RequestId>
    </DescribeGrantRulesToCenResponse>
    ```

-   JSON format

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


