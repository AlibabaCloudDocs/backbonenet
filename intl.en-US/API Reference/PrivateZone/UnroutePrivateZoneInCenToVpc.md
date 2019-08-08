# UnroutePrivateZoneInCenToVpc {#doc_api_Cbn_UnroutePrivateZoneInCenToVpc .reference}

Deletes a PrivateZone entry.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=UnroutePrivateZoneInCenToVpc&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|AccessRegionId|String|Yes|cn-hangzhou| The access region.

 The access region is the region of the cloud resource that accesses the PrivateZone service through CEN.

 |
|CenId|String|Yes|cen-7qthudw0ll6jmc\*\*\*\*| The ID of the CEN instance.

 |
|Action|String|No|UnroutePrivateZoneInCenToVpc| Optional. The name of this action. Value: **UnroutePrivateZoneInCenToVpc**

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|C0245BEF-52AC-44A8-A776-EF96FD26A5CA| The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=UnroutePrivateZoneInCenToVpc
&AccessRegionId=cn-hangzhou
&CenId=cen-7qthudw0ll6jmc****
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<UnroutePrivateZoneInCenToVpcResponse>
      <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
</UnroutePrivateZoneInCenToVpcResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"C0245BEF-52AC-44A8-A776-EF96FD26A5CA"
}
```

## Errors {#section_ffm_s2y_155 .section}

