# ModifyFlowLogAttribute {#doc_api_Cbn_ModifyFlowLogAttribute .reference}

Modifies the name and description of a flow log.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=ModifyFlowLogAttribute&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String |Yes|cen-7qthudw0ll6jmc\*\*\*\*|The ID of the CEN instance.

 |
|FlowLogId|String|Yes|flowlog-m5evbtbpt\*\*\*\*|The ID of the flow log.

 |
|RegionId|String|Yes|cn-hangzhou|The region ID of the flow log. To query the region ID, call [DescribeRegions](~~36063~~).

 |
|Action|String|No|ModifyFlowLogAttribute|Optional. The name of this action. Value: **ModifyFlowLogAttribute**

 |
|Description|String|No|This is my Flowlog.|Optional. The description of the flow log. The description must be 2 to 256 characters in length. It must start with a letter or a Chinese character, and cannot start with `http://` or `https://`.

 |
|FlowLogName|String|No|myFlowlog|Optional. The name of the flow log. The name must be 2 to 128 characters in length and can contain letters, numbers, periods \(.\), underscores \(\_\), and hyphens \(-\). The name must start with a letter or a Chinese character. It cannot start with `http://` or `https://`.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=ModifyFlowLogAttribute
&CenId=cen-7qthudw0ll6jmc****
&FlowLogId=flowlog-m5evbtbpt****
&RegionId=cn-hangzhou
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<ModifyFlowLogAttributeResponse>
	  <RequestId>F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1</RequestId>
</ModifyFlowLogAttributeResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"F7DDDC17-FA06-4AC2-8F35-59D2470FCFC1"
}
```

## Errors { .section}

