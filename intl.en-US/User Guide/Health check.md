# Health check {#concept_wzs_gmh_tdb .concept}

CEN provides the health check function so that you can monitor the network conditions of local data centers connected to the attached VBRs.

## Configure health check {#section_hv3_qzn_tdb .section}

To configure the health check, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  In the left-side navigation pane, click **Health Check**.
3.  Select the region of the CEN instance and click **Add Health Check**.
4.  On the displayed page, configure the following:

    |Configuration|Description|
    |:------------|:----------|
    |**Instances**|Select the CEN instance associated with the VBR.|
    |**Virtual Border Router \(VBR\)**|Select the VBR to monitor.|
    |**Source IP**|Any unused IP address in the VPC attached to the CEN instance.|
    |**Target IP**|The IP address of the customer premises equipment connected to the VBR.|


## View monitoring data {#section_w1z_h14_tdb .section}

To view the monitoring data after configuring the health check, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  In the left-side navigation pane, click **Health Check**.
3.  Click the monitoring icon to view the monitoring data.
    -   **Outbound bandwidth**: The bandwidth of data transmission from Alibaba Cloud to the local data center.
    -   **Inbound bandwidth**: The bandwidth of data transmission from the local data center to the Alibaba Cloud.
    -   **Packet loss**: The loss rate of data transmitted between the Alibaba Cloud and the local data center.

