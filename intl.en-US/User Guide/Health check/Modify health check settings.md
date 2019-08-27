# Modify health check settings {#task_1797369 .task}

This topic describes how to modify the source IP address and target IP address of the health check function.

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  In the left-side navigation pane, click **Health Check**.
3.  On the CEN page, select the region to which the target CEN instance belongs.
4.  Find the target CEN instance, and then click **Edit** in **Actions** column.
5.  On the Set Health Check page, modify the source IP address and target IP address, and then click **OK**. 
    -   **Source IP**: The source IP address can be any available IP address in the 10.0.0.0/8, 192.168.0.0/16, or 172.16.0.0/12 CIDR block. However, the source IP address cannot conflict with the IP address that it will communicate with in the CEN, or the IP address of the VBR at the Alibaba Cloud side or customer side.
    -   **Target IP**: The interface IP address of the customer premises equipment connected to the VBR.

