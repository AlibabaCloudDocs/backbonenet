# PublishRouteEntries {#reference_ehn_cv2_h2b .reference}

Publish the route entries in the attached VPC and VBR to CEN.

## Router entry list {#section_mmj_5cl_l2b .section}

The following table lists the route entries that can be published to CEN:

|Route entry|Network the route entry belongs to|Published to CEN by default?|
|:----------|:---------------------------------|:---------------------------|
|The route entry pointing to an ECS instance|VPC|No|
|The route entry pointing to a VPN Gateway|VPC|No|
|The route entry pointing to a HaVip|VPC|No|
|VPC system route entries|VPC|Yes|
|The route entry pointing to a local IDC|VBR|Yes|
|BGP route entries|VBR|Yes|

## Request parameters: {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description |
|:---|:---|:-------|:-----------|
|Action|String |Yes | The action to perform. Valid value:

 PublishRouteEntries

 |
|CenId|String |Yes |The ID of the CEN instance where the route entry is published.|
|ChildInstanceRegionId|String |Yes |The ID of the region where the attached VBR or VPC is located.|
|ChildInstanceId|String |Yes |The ID of the attached network \(VPC or VBR\).|
|ChildInstanceType|String |Yes |The type of the network.|
|ChildInstanceRouteTableId|String |Yes |The route table of the attached VBR or VPC.|
|DestinationCidrBlock|String |Yes |The destination CIDR block of the route entry to publish.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://cbn.aliyuncs.com/?Action=PublishRouteEntries
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


