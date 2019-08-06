# Set AnyTunnel services {#task_gsf_wly_pgb .task}

If you need to access the cloud services deployed in a VPC through a network in Cloud Enterprise Network \(CEN\), you need to set domain names for the services, the regions of the services, and the access region. Cloud services are the Alibaba Cloud products that are deployed in VPCs and use AnyTunnel addresses \(100.64.0.0/10\) to provide services, such as OSS, log service, and DNS.

Make sure that the host region and the access region have networks \(VPC/VBR/CCN\) attached to CEN.

1.  Log on to the [CEN console](https://cen.console.aliyun.com/). 
2.  Click the target CEN instance ID. 
3.  Click the AnyTunnel tab, and then click **SetAnyTunnelService**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/122767/156508740938943_en-US.png)

4.  In the SetAnyTunnelService dialog box, set the following parameters: 
    1.  **Domain Name or IP**: Enter the intranet domain name or IP address of the cloud service to be accessed. For example, if you want to access the OSS sevice deployed in Hangzhou, enter `oss-cn-hangzhou-internal.aliyuncs.com`, the IP address, or CIDR block of the OSS service, for example, 100.64.0.1 or 100.64.1.0/24.
    2.  **Host Region**: Select the region to which the cloud service to be accessed belongs. 

        **Note:** Make sure that the host region is the same as the region specified for the intranet domain name.

    3.  **Access Region**: Select the region where the access is initiated. 

        **Note:** Make sure that the network in the access region has been attached to the CEN instance.

5.  Click **OK**. 

