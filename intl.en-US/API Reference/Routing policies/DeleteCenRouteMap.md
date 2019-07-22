# DeleteCenRouteMap {#doc_api_Cbn_DeleteCenRouteMap .reference}

Deletes a routing policy.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Cbn&api=DeleteCenRouteMap) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-7qthudw0ll6jm\*\*\*\*|The ID of the CEN instance for which the routing policy is created.

 |
|CenRegionId|String|Yes|cn-hangzhou|The region of the CEN instance. To query the region ID, call [DescribeRegions](~~36063~~).

 |
|RouteMapId|String|Yes|cenrmap-abcdedfghij\*\*\*\*|The ID of the routing policy.

 |
|Action|String|No|DeleteCenRouteMap|Optional. The name of this action. Value: **DeleteCenRouteMap**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|5903EE99-D542-4E14-BC65-AAC1CB2D3D03|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

https://cbn.aliyuncs.com/?Action=DeleteCenRouteMap
&CenId=cen-7qthudw0ll6jm****
&CenRegionId=cn-hangzhou
&RouteMapId=cenrmap-abcdedfghij****
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteCenRouteMapResponse>
  <RequestId>5903EE99-D542-4E14-BC65-AAC1CB2D3D03</RequestId>
</DeleteCenRouteMapResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"5903EE99-D542-4E14-BC65-AAC1CB2D3D03"
}
```

## Error codes { .section}

