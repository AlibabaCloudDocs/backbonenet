# ModifyCenAttribute {#doc_api_Cbn_ModifyCenAttribute .reference}

Modifies the name and description of a CEN instance.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Cbn&api=ModifyCenAttribute&type=RPC&version=2017-09-12)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|CenId|String|Yes|cen-7qthudw0ll6jmc\*\*\*\*| The ID of the CEN instance.

 |
|Action|String|No|ModifyCenAttribute| Optional. The name of this action. Value: **ModifyCenAttribute**.

 |
|Description|String|No|cen| Optional. The description of the CEN instance. The description must be 2 to 256 characters in length. It must start with a letter or a Chinese character, and cannot start with `http://` or `https://`.

 |
|Name|String|No|test| Optional. The name of the CEN instance. The name must be 2 to 128 characters in length and can contain letters, numbers, periods \(.\), underscores \(\_\), and hyphens \(-\). The name must start with a letter or a Chinese character. It cannot start with `http://` or `https://`.

 |
|ProtectionLevel|String|No|FULL| Optional. The level of the routing overlapping function. Valid values:

 -   **FULL**: No overlapped routes are allowed.
-   **REDUCE**: Overlapped routes are allowed. However, the overlapped routes cannot be the same.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|455AC20C-7061-446A-BDBD-B3BEE0856304| The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=ModifyCenAttribute
&CenId=cen-7qthudw0ll6jmc****
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<ModifyCenAttributeResponse>
       <RequestId>13526224-5780-4426-8BDF-BC8B08700F22</RequestId>
</ModifyCenAttributeResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"13526224-5780-4426-8BDF-BC8B08700F22"
}
```

## Errors {#section_1r6_6nd_w9o .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|InvalidOperation.EnhanceProtectionLevel|Your request to enhance CBN protection level cannot be processed. Please contact customer support to continue this operation.|The request to increase the CBN level cannot be processed. If you must perform this operation, contact the customer service.|

