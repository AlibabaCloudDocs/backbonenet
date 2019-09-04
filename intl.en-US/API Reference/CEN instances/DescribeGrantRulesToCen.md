# DescribeGrantRulesToCen {#doc_api_Cbn_DescribeGrantRulesToCen .reference}

Queries the authorization relationship between the associated networks and a CEN instance in a specified region.

**Note:** This API is a VPC API. Therefore, the endpoint of this API is `vpc.aliyuncs.com`. The API version is 2016-04-28.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeGrantRulesToCen&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-7qthudw0ll6jmxx\*\*\*\*| The ID of the CEN instance.

 |
|ProductType|String|Yes|VPC| The product type.

 |
|RegionId|String|Yes|cn-hangzou| The ID of the region to which the network belongs.

 |
|Action|String|No|DescribeGrantRulesToCen| Optional. The name of this action. Value: **DescribeGrantRulesToCen**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|GrantRules| | | The details of the authorization relationship.

 |
|CenId|String|cen-7qthudw0ll6jmccc\*\*\*\*| The ID of the CEN instance.

 |
|ChildInstanceId|String|vpc-bp18sth14qii3pnvc\*\*\*\*| The ID of the associated network \(VPC or VBR\).

 |
|ChildInstanceOwnerId|Long|1231579085529123| The ID of the account to which the network belongs.

 |
|ChildInstanceRegionId|String|cn-hangzhou| The ID of the region to which the network belongs.

 |
|ChildInstanceType|String|VPC| The type of the network. Valid values:

 -   **VPC**
-   **VBR**
-   **CCN**

 |
|RequestId|String|330714D1-F335-4CE2-9D29-F54445937387| The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeGrantRulesToCen
&CenId=cen-7qthudw0ll6jmxx****
&ProductType=VPC
&RegionId=cn-hangzou
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeGrantRulesToCenResponse>
      <TotalCount>1</TotalCount>
      <PageNumber>1</PageNumber>
      <CbnGrantRules>
            <CbnGrantRule>
                  <CbnInstanceId>cbn-6ugox0vl0zff4g****</CbnInstanceId>
                  <CbnOwnerId>101664776xxxx</CbnOwnerId>
                  <CreationTime>2018-01-18T11:49:09Z</CreationTime>
            </CbnGrantRule>
      </CbnGrantRules>
      <PageSize>10</PageSize>
      <RequestId>330714D1-F335-4CE2-9D29-F54445937387</RequestId>
</DescribeGrantRulesToCenResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"CbnGrantRules":{
		"CbnGrantRule":[
			{
				"CreationTime":"2018-01-18T11:49:09Z",
				"CbnInstanceId":"cbn-6ugox0vl0zff4g****",
				"CbnOwnerId":"101664776xxxx"
			}
		]
	},
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"330714D1-F335-4CE2-9D29-F54445937387"
}
```

## Errors {#section_67b_4zw_w7p .section}

