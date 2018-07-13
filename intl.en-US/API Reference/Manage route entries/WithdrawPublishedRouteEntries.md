# WithdrawPublishedRouteEntries {#reference_ehn_cv2_h2b .reference}

Remove the route entries that have been advertised to CEN from the route table of the attached VPC or VBR.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform.  Valid value:

 WithdrawPublishedRouteEntries

 |
|CenId|String|Yes|The ID of the CEN instance from which the route entries are removed.|
|ChildInstanceRegionId|String|Yes|The ID of the region where the attached VBR or VPC is located.|
|ChildInstanceId|String|Yes|The ID of the attached network \(VPC or VBR\).|
|ChildInstanceType|String|Yes|The type of the network, value:-   VPC
-   VBR

|
|ChildInstanceRouteTableId|String|Yes|The route table of the attached VBR or VPC.|
|DestinationCidrBlock|String|Yes|The destination CIDR block of the route entry to be removed.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Example {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=WithdrawPublishedRouteEntries
&ChildInstanceRegionId=cn-hangzhou-667
&CenId=cbn-3rh17kwhs6208rej85
&DestinationCidrBlock=192.168.10.0/24
&ChildInstanceRouteTableId=vtb-il7qut3mjgtlcbpk2ie31
&ChildInstanceId=vpc-il7krrmtp6elewp6426kr
&ChildInstanceType=VPC
&CommonRequestParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <PublishRouteEntriesResponse>
        <RequestId>FBDB18D8-E91E-4978-8D6C-6E2E3EE101330</RequestId>
    </PublishRouteEntriesResponse>
    ```

-   JSON format

    ```
    
    {
        "RequestId": "FBDB18D8-E91E-4978-8D6C-6E2E3EE10133"
    }
    
    
    ```


