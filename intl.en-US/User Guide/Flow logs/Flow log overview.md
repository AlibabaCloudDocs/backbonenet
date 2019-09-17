# Flow log overview {#concept_778527 .concept}

This topic describes the flow log function of Cloud Enterprise Networks \(CENs\). By using the flow log function, you can capture the traffic data of the network instances in different regions of a CEN. You can also use the data aggregated in flow logs to analyze cross-region traffic flows, minimize traffic costs, and troubleshoot network faults.

**Note:** 

-   To add your account to the whitelist for the flow log function, open a ticket.
-   Flow logs only capture cross-region traffic data of mutual access. Traffic between two VPCs in a region, or traffic among VPCs, VBRs, and on-premises data centers in a region, are not captured.
-   The flow log function is supported in China \(Hangzhou\), China \(Shanghai\), China \(Zhangjiakou\), China \(Shenzhen\), China \(Beijing\), China \(Hohhot\), China \(Hong Kong\), UK \(London\), US \(Silicon Valley\), US \(Virginia\), Germany \(Frankfurt\), India \(Mumbai\), Singapore, Indonesia \(Jakarta\), Australia \(Sydney\), and Malaysia \(Kuala Lumpur\).

## Background information {#section_fum_lzt_xlp .section}

Flow logs can be defined as aggregated traffic data that is captured in a capture window of 10 minutes. Each flow log consists of the following traffic data: a source IP address and source port, a destination IP address and destination port, and the protocol that is used.

The captured traffic data is stored in Alibaba Cloud Log Service, where you can view and analyze the traffic data. The flow log function is currently in the beta testing phase. During this phase, you are only charged for the storage and retrieval of traffic data in Log Service.

The traffic data captured by the flow log function is written to Log Service as flow log records. Each flow log record captures specified traffic data in a specified capture window, which is about 10 minutes. During this period, data is aggregated and then released to the flow log record.

The following table describes the fields of a flow log record.

|Field|Description|
|-----|-----------|
|account-id|Account ID|
|cen-id|The ID of the CEN instance.|
|srcaddr|The source IP address.|
|srcport|The source port.|
|dstaddr|The destination IP address.|
|dstport|The destination port.|
|protocol|The protocol type.|
|direction|The direction of the traffic. Valid values: -   in: indicates inbound traffic.
-   out: indicates outbound traffic.

 |
|packets|The number of data packets.|
|bytes|The number of data packets.|
|rtt|The latency.|
|start|The start time of the capture window.|
|end|The end time of the capture window.|
|log-status|The status of the flow log record. Valid values: -   OK: indicates that traffic data was successfullly recorded.
-   NODATA: indicates that no traffic data was detected during the capture window.
-   SKIPDATA: indicates that some flow log records were skipped during the capture window.

 |

## Procedure {#section_e65_aa0_cod .section}

The following figure shows the procedure for configuring the flow log function.

![Procedure](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630431/156871087650102_en-US.png)

1.  Activate Log Service.

    The traffic data captured by the flow log function is stored in Alibaba Cloud Log Service. Therefore, you need to activate Log Service before you create a flow log.

2.  Optional. Create an AccessKey.

    f you want to write data to Log Service through APIs or SDKs, you must first create an AccessKey \(AK\). However, if you want to collect logs by using Logtail, you do not need to create an AK.

3.  Create a Project.

    You must create a Project in Log Service. For more information, see [Create a project](../../../../reseller.en-US/Preparation/Manage projects.md#section_ahq_ggx_ndb).

4.  Create a Logstore.

    A Logstore is a collection of resources created in a Project. All data in a Logstore is from the same data source. After creating a Project, you must create a Logstore. For more information, see [Create a Logstore.](../../../../reseller.en-US/Preparation/Manage a Logstore.md#section_v52_2jx_ndb).

5.  Creates a flow log.

    You call create a flow log through the CEN console. For more information, see [Create a flow log](reseller.en-US/User Guide/Flow logs/Create a flow log.md#).

6.  View the flow log.

    You can view the captured traffic data in the flow log. You can use the captured traffic data to analyze cross-region traffic flows, minimize traffic costs, and troubleshoot network faults. For more information, see [View flow logs](reseller.en-US/User Guide/Flow logs/View flow logs.md#).


## Limit {#section_pt4_mcz_lxq .section}

Each CEN instance supports only one flow log.

## Related documentation {#section_u4p_zxo_9um .section}

-   [Start a flow log](reseller.en-US/User Guide/Flow logs/Start a flow log.md#)
-   [Stop a flow log](reseller.en-US/User Guide/Flow logs/Stop a flow log.md#)
-   [Modify a flow log](reseller.en-US/User Guide/Flow logs/Modify a flow log.md#)
-   [Delete a flow log](reseller.en-US/User Guide/Flow logs/Delete a flow log.md#)
-   [Flow log API overview](../../../../reseller.en-US/API Reference/API overview.md#section_s3l_rt9_txj)

