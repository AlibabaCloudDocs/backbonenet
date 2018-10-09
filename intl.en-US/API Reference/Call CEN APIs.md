# Call CEN APIs {#concept_jyw_13k_qdb .concept}

## Request structure {#section_mqj_q3f_mdb .section}

CEN APIs belong to the RPC type. You can call CEN APIs by sending HTTP requests.

The request structure is as follows:

```
http://Endpoint/?Action=xx&Parameters
```

Where:

-   Endpoint is the entry of the Alibaba Cloud service to call. The endpoint of CEN is `cbn.aliyuncs.com`.
-   Action is the action to perform. For example, use the DescribeCens action to query created CEN instances.
-   Version is the version of API to call. The API version of CEN is 09/12/2017.
-   Parameters are request parameters separated by ampersands \(&\).

    Request parameters consist of common parameters and API specific parameters. Common parameters include VPI version, credentials and more.


The following is an example using the DescribeCens API to query the created CEN instances:

**Note:** To make it easy to read, the API request is displayed in the following format in the document:

```
https://cbn.aliyuncs.com/?Action=CreateCen
&Format=xml
&Version=2017-09-12
&Signature=xxxx%xxxx%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396
&SignatureVersion=1.0
&AccessKeyId=key-test
&Timestamp=2012-06-01T12:00:00Z
...
```

## API authorization {#section_mlp_qmf_mdb .section}

For the security of your account, we recommend that you use a RAM user to call APIs. Before using a RAM user to call an API, you must grant the RAM user the corresponding permission to call the API by creating an authorization policy and attaching the policy to the RAM user.

For more information, see [RAM authentication](intl.en-US/API Reference/RAM authentication.md#).

## API signature {#section_jtc_ymf_mdb .section}

CEN authenticates each API request. You must include the signature in the request no matter you submit an HTTP or HTTPs request.

CEN performs symmetric encryption by using the AccessKey ID and AccessKey Secret to verify the identities of request senders. AccessKey is an identity credential issued to Alibaba Cloud accounts and the RAM users \(similar to the login password\). The AccessKey ID is used to verify the identity of the user, and the AccessKey Secret is used to encrypt the signature string and is also the key used by the server to verify the signature string. The AccessKey Secret must be kept strictly confidential.

For an RPC API, you must add the signature to the API request in the following format:

`https://endpoint/?SignatureVersion=*1.0*&SignatureMethod=*HMAC-SHA1*&Signature=*CT9X0VtwR86fNWSnsc6v8YGOjuE%3D&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf*`

Take the DescribeCens as an example. If the AccessKey ID is `testid`, and the AccessKey Secret is `testsecret`, and the original request URL is as follows:

```
http://cbn.aliyuncs.com/?Action=DescribeCens
&Timestamp=2016-02-23T12:46:24Z
&Format=XML
&AccessKeyId=testid&Action=DescribeCens
&SignatureMethod=HMAC-SHA1
&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
&Version=2014-05-26&SignatureVersion=1.0
```

Complete these steps to calculate the signature:

1.  Use the request parameters to create a canonicalized query string to sign.

    ```
    GET&%2F&AccessKeyId%3Dtestid&Action%3DDescribeCens&Format%3DXML&SignatureMethod%3DHMAC-SHA1&SignatureNonce%3D3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf&SignatureVersion%3D1.0&TimeStamp%3D2016-02-23T12%253A46%253A24Z&Version%3D2014-05-15
    ```

    .

2.  Compute the HMAC of the string to sign.

    Append an ampersand \(&\) to the AccessKey Secret to use the new string as the key to compute the HMAC. In this example, the key is `testsecret&amp;`.

    ```
    CT9X0VtwR86fNWSnsc6v8YGOjuE=
    ```

3.  Add the signature to the request URL:

    ```
    http:/cbn.aliyuncs.com/? Action=DescribeCens
    &Timestamp=2016-02-23T12:46:24Z
    &Format=XML
    &AccessKeyId=testid
    &SignatureMethod=HMAC-SHA1
    &SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
    &Version=2014-05-26
    &SignatureVersion=1.0
    &Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D
    ```


