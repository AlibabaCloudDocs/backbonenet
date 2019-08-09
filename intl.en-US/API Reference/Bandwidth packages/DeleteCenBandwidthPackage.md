# DeleteCenBandwidthPackage {#doc_api_Cbn_DeleteCenBandwidthPackage .reference}

Deletes a bandwidth package.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=DeleteCenBandwidthPackage&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenBandwidthPackageId|String |Yes|cenbwp-4c2zaavbvh5f42\*\*\*\*|The ID of the bandwidth package to be deleted.

 |
|Action|String|No|DeleteCenBandwidthPackage|Optional. The name of this action. Value: **DeleteCenBandwidthPackage**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|C0245BEF-52AC-44A8-A776-EF96FD26A5CA|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteCenBandwidthPackage
&CenBandwidthPackageId=cenbwp-4c2zaavbvh5f42****
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteCenBandwidthPackageResponse>
       <RequestId>13526224-5780-4426-8BDF-BC8B08700F22</RequestId>
</DeleteCenBandwidthPackageResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"C0245BEF-52AC-44A8-A776-EF96FD26A5CA"
}
```

## Errors { .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden.Release|Forbidden to release a PREPAY bandwidth instance within validity period.|Deletion of Subscription bandwidth packages is not allowed.|

