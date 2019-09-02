# Set a cross-region connection bandwidth {#task_1563616 .task}

This topic describes how to set a cross-region connection bandwidth. By setting a cross-region connection bandwidth, you can connect network instances across different regions through the intranet.

[Attach networks](reseller.en-US/Quick Start/Attach networks.md#)

You do not need to configure a bandwidth package or pay for network instance connections in the same region. Additionally, you must purchase a bandwidth package if you want to connect network instances across different regions. When you purchase a bandwidth package, you need to specify the areas then set the bandwidth for the regions that you want to interconnect through the intranet.

## Purchase a bandwidth package {#section_79f_pkk_acu .section}

To purchase a bandwidth package, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  On the Instances page, find the target CEN instance and click the instance ID.
3.  On the CEN page, click **Bandwidth Packages**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1240718/156740389854489_en-US.png)

4.  Click **Buy Bandwidth Package \(Subscription\)**.
5.  **CEN ID**: Select the CEN instance for which you want to purchase a bandwidth packet.
6.  Select the areas to be interconnected. An area consists of one or more Alibaba Cloud regions. After you purchase a bandwidth package and set a cross-region interconnection bandwidth for two areas, network instances in the regions of these two areas can communicate with each other.

    **Note:** After you purchase the bandwidth package, the interconnection areas cannot be modified.

    |Area|Included regions|
    |:---|:---------------|
    |Mainland China|China \(Qingdao\), China \(Beijing\), China \(Zhangjiakou\), China \(Shenzhen\), China \(Hangzhou\), China \(Shanghai\), China \(Hohhot\)|
    |North America|US \(Silicon Valley\), US \(Virginia\)|
    |Asia Pacific|China \(Hong Kong\), Singapore, Malaysia \(Kuala Lumpur\), Japan \(Tokyo\), India \(Mumbai\), Indonesia \(Jakarta\)|
    |Europe|Germany \(Frankfurt\), UK \(London\)|
    |Australia|Australia \(Sydney\)|

7.  Set the bandwidth of the bandwidth package.
8.  Enter a name for the bandwidth package.
9.   Select a duration, and then select Auto Renew or not.
10. Click **Buy Now** and complete the payment.

## Set a cross-region connection bandwidth {#section_1mq_qrm_wdt .section}

To set a cross-region connection bandwidth, complete these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  On the Instances page, find the target CEN instance and click the instance ID.
3.  On the CEN page, click **Region Connections**, and then click **Set Region Connection**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1240718/156740389954523_en-US.png)

4.  **Bandwidth Packages**: Select the bandwidth package that you purchased.
5.  **Connected Regions**: select two regions to be interconnected.
6.  **Bandwidth**: Set a bandwidth for the selected regions. 

    **Note:** The default bandwidth is 1 Kbit/s, which is only used to test the connectivity between the selected regions. We recommend that you set the bandwidth according to your specific needs. The sum of all the connection bandwidth values cannot exceed the bandwidth value of the bandwidth package.

7.  Click **OK**.

