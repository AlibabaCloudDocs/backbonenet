# DescribeFlowlogs {#doc_api_Cbn_DescribeFlowlogs .reference}

Queries one or more flow logs.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DescribeFlowlogs&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|No|DescribeFlowlogs| Optional. The name of this action. Value: **DescribeFlowlogs**

 |
|CenId|String|No|cen-7qthudw0ll6jmc\*\*\*\*| Optional. The ID of the CEN instance.

 |
|Description|String|No|This is my Flowlog.| Optional. The description of the flow log. The description must be 2 to 256 characters in length. It must start with a letter or a Chinese character, and cannot start with `http://` or `https://`.

 |
|FlowLogId|String|No|flowlog-m5evbtbpt\*\*\*\*| Optional. The ID of the flow log.

 |
|FlowLogName|String|No|myFlowlog| Optional. The name of the flow log.

 |
|PageNumber|Integer|No|1| Optional. The current page number.

 |
|PageSize|Integer|No|10| Optional. The number of entries per page.

 |
|RegionId|String|No|cn-hangzhou| Optional. The region ID of the flow log. To query the region ID, call [DescribeRegions](~~36063~~).

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|FlowLogs| | | The details of the flow log.

 |
|CenId|String|cen-7qthudw0ll6jmc\*\*\*\*| The ID of the CEN instance.

 |
|CreationTime|String|2018-07-24T13:00:52Z| The time when the flow log is created.

 |
|Description|String|abc| The description of the flow log.

 |
|FlowLogId|String|flowlog-m5evbtbpt\*\*\*\*| The ID of the flow log.

 |
|FlowLogName|String|myFlowlog| The name of the flow log.

 |
|LogStoreName|String|FlowLogStore| The LogStore that stores the captured traffic information.

 |
|ProjectName|String|FlowLogProject| The Project that stores the captured traffic information.

 |
|PageNumber|String|1| The current page number.

 |
|PageSize|String|10| The number of entries per page.

 |
|RequestId|String|F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1| The ID of the request.

 |
|TotalCount|String|3| The total number of queried flow logs.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeFlowlogs
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeFlowlogsResponse>
      <RequestId>04F0F334-1335-436C-A1D7-6C044FExxxxx</RequestId>
</DescribeFlowlogsResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FExxxxx"
}
```

## Errors {#section_l8l_pzj_740 .section}

