# DeactiveFlowLog {#doc_api_Cbn_DeactiveFlowLog .reference}

Stops a flow log. After a flow log is stopped, the traffic information of the specified cloud resource is no longer collected.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DeactiveFlowLog&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String |Yes|cen-7qthudw0ll6jmc\*\*\*\*|The ID of the CEN instance.

 |
|FlowLogId|String |Yes|flowlog-m5evbtbpt\*\*\*\*|The ID of the flow log.

 |
|RegionId|String|Yes|cn-hangzhou|The region ID of the flow log. To query the region ID, call [DescribeRegions](~~36063~~).

 |
|Action|String|No|DeactiveFlowLog|Optional. The name of this action. Value: **DeactiveFlowLog**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeactiveFlowLog
&CenId=cen-7qthudw0ll6jmc****
&FlowLogId=flowlog-m5evbtbpt****
&RegionId=cn-hangzhou
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DeactiveFlowLogResponse>
       <RequestId>F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1</RequestId>
</DeactiveFlowLogResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1"
}
```

## Errors { .section}

