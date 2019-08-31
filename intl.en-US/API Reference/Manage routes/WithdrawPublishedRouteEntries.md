# WithdrawPublishedRouteEntries {#doc_api_Cbn_WithdrawPublishedRouteEntries .reference}

Withdraws a route of a VPC or Virtual Border Router \(VBR\) from the attached Cloud Enterprise Network \(CEN\) instance.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=WithdrawPublishedRouteEntries&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-sxjfjkjfkjfiein\*\*\*\*|The ID of the CEN instance.

 |
|ChildInstanceId|String|Yes|vpc-rj9gt5nll27onu7\*\*\*\*|The ID of the attached network \(VPC or VBR\).

 |
|ChildInstanceRegionId|String|Yes|cn-hangzhou|The ID of the region to which the attached network belongs.

 |
|ChildInstanceRouteTableId|String|Yes|vtb-bp174d1gje79u1g4t\*\*\*\*|The ID of the route table of the attached network.

 |
|ChildInstanceType|String|Yes|VPC|The type of the network. Valid values:

 -   **VPC**: Virtual Private Cloud
-   **VBR**: Virtual Border Router

 |
|DestinationCidrBlock|String|Yes|172.16.xx.xx/24|The destination CIDR block of the route to be withdrawn.

 |
|Action|String|No|WithdrawPublishedRouteEntries|Optional. The name of this action. Value: **WithdrawPublishedRouteEntries**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|FBDB18D8-E91E-4978-8D6C-6E2E3EE10133|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=WithdrawPublishedRouteEntries
&CenId=cen-sxjfjkjfkjfiein****
&ChildInstanceId=vpc-rj9gt5nll27onu7****
&ChildInstanceRegionId=cn-hangzhou
&ChildInstanceRouteTableId=vtb-bp174d1gje79u1g4t****
&ChildInstanceType=VPC
&DestinationCidrBlock=172.16.xx.xx/24
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<PublishRouteEntriesResponse>
      <RequestId>FBDB18D8-E91E-4978-8D6C-6E2E3EE101330</RequestId>
</PublishRouteEntriesResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"FBDB18D8-E91E-4978-8D6C-6E2E3EE10133"
}
```

## Errors { .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|InvalidOperation.UnsupportnexthopType|The specified next hop type is not supported by this operation.|The specified next hop type is not supported.|
|400|ParameterIllegal.CenInstanceId|The parameter of CEN instance id is illegal.|The ID of the CEN instance is incorrect.|
|400|ParameterIllegal.ChildInstanceRegionId|The parameter of child instance region id is illegal.|The region to which the network belongs is incorrect.|
|409|InvalidOperation.ChildInstanceStatus|The child-instance is not in a valid state for the operation.|The network is being processed. Please try later.|
|409|InvalidOperation.CenInstanceStatus|The CEN instance is not in a valid state for the operation.|The CEN instance is being processed. Please try later.|
|400|ParameterIllegal.ChildInstanceType|The parameter of child instance type is illegal.|The network type is incorrect.|

