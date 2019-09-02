# DeleteRouteServiceInCen {#doc_api_Cbn_DeleteRouteServiceInCen .reference}

Deletes the Cloud Enterprise Network \(CEN\) settings of accessing a cloud service.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DeleteRouteServiceInCen&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|AccessRegionId|String|Yes|cn-hangzhou|The region of the network instances that access the cloud service.

 |
|CenId|String|Yes|cen-7qthudw0ll6jmc\*\*\*\*|The ID of the CEN instance.

 |
|Host|String|Yes|100.64.0.0/8|The IP address or domain name of the cloud service.

 |
|HostRegionId|String|Yes|cn-shanghai|The region of the cloud service.

 |
|Action|String|No|DeleteRouteServiceInCen|Optional. The name of this action. Value: **DeleteRouteServiceInCen**

 |
|HostVpcId|String|No|vpc-bp1t36rn9l53iwbsf\*\*\*\*|Optional. The VPC associated with the cloud service.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|2315DEB7-5E92-423A-91F7-4C1EC9AD97C3|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteRouteServiceInCen
&AccessRegionId=cn-hangzhou
&CenId=cen-7qthudw0ll6jmc****
&Host=100.64.0.0/8
&HostRegionId=cn-shanghai
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DeleteRouteServiceInCenResponse>
    <RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
</DeleteRouteServiceInCenResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
}
```

## Errors { .section}

