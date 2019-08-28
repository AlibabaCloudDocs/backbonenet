# Create a flow log {#task_895232 .task}

This topic describes how to create a flow log. The flow log function in Cloud Enterprise Network \(CEN\) is used to record the cross-region traffic data of the networks associated with a CEN instance. To record traffic data, you must create a flow log.

Before you create a flow log, make sure that the following conditions are met:

-   Log Service is activated.
-   A Project and a Logstore are created to store the traffic data. For more information, see [Create a project](../../../../reseller.en-US/Preparation/Manage projects.md#section_ahq_ggx_ndb) and [Create a Logstore](../../../../reseller.en-US/Preparation/Manage a Logstore.md#section_v52_2jx_ndb).

After a flow log is created, the flow log enters the **Enabled** state, indicating that traffic data is recording.

You can view and analyze the traffic data in Log Service.

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  In the left-side navigation pane, click **Flow Logs**.
3.  Select the region of the flow log to be created. 

    **Note:** 

    -   The region of the flow log must be the same as that of the Project.
    -   Currently, the flow log function is supported only in the following regions: China \(Hangzhou\), China \(Shanghai\), China \(Shenzhen\), China \(Beijing\), China \(Hohhot\), Hong Kong, UK \(London\), US \(Silicon Valley\), and US \(Virginia\).
4.  On the CEN page, click **Create Flow Log**.
5.  On the Create Flow Log page, configure the flow log according to the following information, and then click **OK**. 

    |Configuration|Description|
    |-------------|-----------|
    |**Name**|Enter a name for the flow log to be created.|
    |**CEN**|Select the CEN instance of which you want to record the traffic data.|
    |**Project**|Select the Project where the recorded traffic data is stored.|
    |**LogStoreName**|Select the Logstore where the recorded traffic data is stored.|
    |**Description**|Enter a description for the flow log.|


