# CreateFlowlog {#doc_api_Cbn_CreateFlowlog .reference}

Creates a flow log.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=CreateFlowlog&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String |Yes|cen-7qthudw0ll6jmc\*\*\*\*|The ID of the CEN instance.

 |
|LogStoreName|String |Yes|FlowLogStore|The LogStore that stores the captured traffic information.

 |
|ProjectName|String|Yes|FlowLogProject|The Project that stores the captured traffic information.

 |
|RegionId|String |Yes|cn-hangzhou|The region ID of the flow log. To query the region ID, call [DescribeRegions](~~36063~~).

 |
|Action|String|No|CreateFlowlog|Optional. The name of this action. Value: **CreateFlowLog**

 |
|Description|String|No|This is my Flowlog.|Optional. The description of the flow log. The description must be 2 to 256 characters in length. It must start with a letter or a Chinese character, and cannot start with `http://` or `https://`.

 |
|FlowLogName|String|No|myFlowlog|Optional. The name of the flow log. The name must be 2 to 128 characters in length and can contain letters, numbers, periods \(.\), underscores \(\_\), and hyphens \(-\). The name must start with a letter or a Chinese character. It cannot start with `http://` or `https://`.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|FlowLogId|String|flowlog-m5evbtbpt\*\*\*\*|The ID of the flow log.

 |
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B457|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateFlowlog
&CenId=cen-7qthudw0ll6jmc****
&LogStoreName=FlowLogStore
&ProjectName=FlowLogProject
&RegionId=cn-hangzhou
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<CreateFlowlogResponse>
      <RequestId>54B48E3D-DF70-471B-AA93-08E683A1B457</RequestId>
      <FlowLogId>flowlog-m5evbtbptxffgs****</FlowLogId>
</CreateFlowlogResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"54B48E3D-DF70-471B-AA93-08E683A1B457",
	"FlowLogId":"flowlog-m5evbtbpt****"
}
```

## Errors { .section}

