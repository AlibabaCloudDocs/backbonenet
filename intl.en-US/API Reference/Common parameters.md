# Common parameters {#reference_xry_cjk_qdb .reference}

The following common request parameters must be added each time calling an API, and a request ID will be returned no matter the request is successful or not.

## Common request parameters {#section_zm5_rgf_cz .section}

Public request parameters are request parameter that each interface uses.

|Name|Type|Required|Description|
|----|----|--------|-----------|
|Format|String|No|The format of the response. Valid values:JSON\(default value\) | XML 

|
|Version|String|是|The version of the API in the format of `YYYY-MM-DD`. Valid value:2017-09-12

|
|AccessKeyId|String|Yes|The AccessKey ID of the user who calls the API.|
|Signature|String|Yes|The request signature.|
|SignatureMethod|String|Yes|The algorithm used to create the request signature. Valid value:HMAC-SHA1

|
|Timestamp|String|Yes|Request timestamp. The date format follows the ISO8601 standard and uses UTC time. The format is `YYYY-MM-DDThh:mm:ssZ`.Example: 2014-11-11T12:00:00Z \(November 11, 2014 at 20:00:00, Beijing time\)

|
|SignatureVersion|String|Yes|The signature version to use. Valid value:1.0

|
|SignatureNonce|String|Yes|A random number for the signature to prevent from network attacks.Different random numbers must be used for different requests.

|

**Example**

```
https://cbn.aliyuncs.com/?Action=DescribeCens
&TimeStamp=2014-05-19T10%3A33%3A56Z
&Format=xml
&AccessKeyId=testid
&Action=DescribeCens
&SignatureMethod=Hmac-SHA1
&CenId=*CenID*
&SignatureNonce=NwDAxvLU6tFE0DVb
&Version=2016-04-28
&SignatureVersion=1.0
&Signature=*Signature*
```

## Common response parameters {#section_rjn_1hf_cz .section}

After the API service is called, the returned data adopts a uniform format. A returned HTTP status code of 2xx indicates that the call was successful. A returned HTTP status code of 4xx or 5xx indicates that the call fails. For a successful call, the primary formats of returned data are XML and JSON. When a request is sent, an external system can input parameters to specify the format of returned data. The default format is JSON.

Each time you send a request to call an interface, the system returns a unique identification code \(RequestId\), whether the request is successful.

