# Configure the health check function {#task_1681270 .task}

This topic describes how to configure the health check function of a Cloud Enterprise Network \(CEN\) instance. After you configure the health check function of a CEN instance, you can monitor the network conditions of on-premises data centers connected to the CEN.

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  In the left-side navigation pane, click **Health Check**.
3.  On the CEN page, select the region to which the target CEN instance belongs, and then click **Set Health Check**.
4.  On the Set Health Check page, set the parameters as needed, and then click **OK**. The following table describes the parameters. 

    |Configuration|Description|
    |:------------|:----------|
    |**Instances**|Select the CEN instance to which the VBR is attached.|
    |**Virtual Border Router \(VBR\)**|Select the VBR that you want to monitor.|
    |**Source IP**|The source IP address can be any available IP address in the 10.0.0.0/8, 192.168.0.0/16, or 172.16.0.0/12 CIDR block. However, the source IP address cannot conflict with the IP address that it will communicate with in the CEN, or the IP address of the VBR at the Alibaba Cloud side or customer side.|
    |**Target IP**|The Interface IP address of the customer premises equipment connected to the VBR.|


