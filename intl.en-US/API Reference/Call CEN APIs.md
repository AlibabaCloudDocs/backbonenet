# Call CEN APIs {#concept_jyw_13k_qdb .concept}

## Request syntax {#section_mqj_q3f_mdb .section}

CEN APIs use RPC style. To call CEN APIs, send HTTP GET requests.

The structure of a CEN API request is as follows:

``` {#codeblock_qbg_6sj_ojk}
http://Endpoint/?Action=xx&Parameters
```

where,

-   Endpoint: the endpoint of the cloud resource involved. The endpoint of CEN is `cbn.aliyuncs.com`.
-   Action: the name of this action. For example, if you need to query created CEN instances, the action is DescribeCens.
-   Version: the version of the API. The version of CEN APIs is 2017-09-12.
-   Parameters: the request parameters. Separate multiple parameters by using ampersands \(&\).

    Request parameters include common parameters and API-specific parameters. Common parameters include API version and identity authentication information among other parameters.


The following is an example of calling DescribeCens to query created CEN instances.

**Note:** Note that the following code has been edited to ease readability.

``` {#codeblock_3g1_l3r_ker}
https://cbn.aliyuncs.com/?Action=CreateCen
&Format=xml
&Version=2017-09-12
&Signature=xxxx%xxxx%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396
&SignatureVersion=1.0
&AccessKeyId=key-test
&Timestamp=2012-06-01T12:00:00Z
…
```

## User authentication {#section_mlp_qmf_mdb .section}

To maintain account security, we recommend that you use the Access Keys \(AKs\) of RAM users to call APIs. Before you use a RAM user to call an API, you must grant the RAM user the corresponding permission to call the API by creating an authorization policy and attaching the policy to the RAM user.

For more information about the policies related to CEN APIs, see [RAM authentication](reseller.en-US/API Reference/RAM authentication.md#).

## Request signature {#section_jtc_ymf_mdb .section}

Authentication is required by the CEN service for each API call, which is provided by the inclusion of signature information in the request.

CEN uses an AccessKeyID and AccessKeySecret pair \(that is, an AK\) and symmetric encryption to authenticate the identity of the request sender. AKs are certificates that Alibaba Cloud issues to Alibaba Cloud accounts and RAM users for authentication. It is similar to a logon password. The AccessKeyID is used to identify the visitor's identity. The AccessKeySecret is the key used to encrypt the signature string. The server uses the AccessKeySecret to decrypt the signature string. The AccessKeySecret must be kept confidential.

A request in an API call is signed in the following format:

`https://endpoint/?SignatureVersion=*1.0*&SignatureMethod=*HMAC-SHA1*&Signature=*CT9X0VtwR86fNWSnsc6v8YGOjuE%3D&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf*`

Take the API call of DescribeCens as an example. If your AccessKeyID is `testid`, and your AccessKeySecret is `testsecret`, then, the URL in the signature is as follows:

``` {#codeblock_9q9_3j4_5cu}
http://cbn.aliyuncs.com/?Action=DescribeCens
&Timestamp=2016-02-23T12:46:24Z
&Format=XML
&AccessKeyId=testid&Action=DescribeCens
&SignatureMethod=HMAC-SHA1
&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
&Version=2014-05-26&SignatureVersion=1.0
```

To generate the signature, follow these steps:

1.  Create the string to be signed by using the request parameter.

    ``` {#codeblock_62x_pw9_xlc}
    GET&%2F&AccessKeyId%3Dtestid&Action%3DDescribeCens&Format%3DXML&SignatureMethod%3DHMAC-SHA1&SignatureNonce%3D3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf&SignatureVersion%3D1.0&TimeStamp%3D2016-02-23T12%253A46%253A24Z&Version%3D2014-05-15
    ```

2.  Calculate the HMAC value of the string.

    Add an ampersand \(&\) after the AccessKeySecret to add the key of the HMAC value. In this example, the key is `testsecret&`.

    ``` {#codeblock_79d_na1_2xa}
    CT9X0VtwR86fNWSnsc6v8YGOjuE=
    ```

3.  Add the signature to the request parameter.

    ``` {#codeblock_iph_x3e_iyu}
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


