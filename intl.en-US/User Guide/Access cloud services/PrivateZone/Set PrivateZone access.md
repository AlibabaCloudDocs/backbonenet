# Set PrivateZone access {#task_zp5_nwy_pgb .task}

PrivateZone is a VPC-based resolution and management service for private domain names. Networks in a Cloud Enterprise Network \(CEN\) instance can access the PrivateZone service through CEN.

Make sure that the host region and access region have networks \(VPC,VBR, and CCN\) attached to the CEN instance.

1.  Log on to the [CEN console](https://cen.console.aliyun.com/). 
2.  Click the target CEN instance ID. 
3.  Click the PrivateZone tab and then click **Authorization**. 

    **Note:** You need to grant permissions to Smart Access Gateway only for the first time you configure PrivateZone access.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122838/156413470038425_en-US.png)

4.  In the Cloud Resource Authorization dialog box, click **Confirm Authorization Policy** to allow local branches associated with a CCN \(a component of smart access gateway\) in the CEN instance to access PrivateZone. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122838/156413470138860_en-US.png)

5.  Click **SetPrivateZone** and then in the SetPrivateZone dialog box, set the following parameters: 
    1.  **Host Region**: Select the region to which the VPC configured with PrivateZone belongs. 
    2.  **Host VPC**: Select the VPC that is configured with PrivateZone. 

        The PrivateZone service can be selected only by selecting the VPC in the host region.

    3.  **Access Region**: Select the region where the access is initiated. 

        **Note:** 

        -   The access region can be CCN, or the same region as the host region. Make sure that the network in the selected access region has been attached to the CEN instance.
        -   If you select CCN, and the account of CCN is different from that of VPC or CEN, you need to grant permissions to CCN. For more information, see [Grant permissions to CCN](reseller.en-US/User Guide/Access cloud services/PrivateZone/Grant permissions to CCN.md#)。
6.  Click **OK**. 

