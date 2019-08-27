# Configure a cross-region connection bandwidth {#task_1681085 .task}

This topic describes how to configure a cross-region connection bandwidth. To connect networks in different regions, you must configure a cross-region connection bandwidth after purchasing a bandwidth package.

The sum of all cross-region connection bandwidth values cannot exceed the bandwidth of the bandwidth package. By default, 1 Kbit/s bandwidth is provided for cross-region connections. This default bandwidth is provided for you to perform connectivity tests. To run normal services, you must buy a bandwidth package and set a proper cross-region connection bandwidth.

Assume that you have bought a bandwidth package of 20 Mbit/s for a Cloud Enterprise Network \(CEN\) instance and the connected areas are Mainland China and North America. You can set a cross-region connection bandwidth between US \(Virginia\) and China \(Hangzhou\), China \(Shanghai\), China \(Shenzhen\), or other regions. However, the total bandwidth values set for all cross-region connections cannot exceed 20 Mbit/s.

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  On the Instances page, find the target CEN instance and click **Manage** in the **Actions** column.
3.  Click the **Region Connections** tab, and click **Set Region Connection**.
4.  In the displayed Set Region Connection dialog box, configure the cross-region connection bandwidth and click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Bandwidth Package**|Select the bandwidth package attached to the CEN instance.|
    |**Connected Regions**|Select the regions to be connected.|
    |**Bandwidth**|Enter the required bandwidth value for the connected regions. The sum of all cross-region connection bandwidth values cannot exceed the bandwidth of the bandwidth package.

 Assume that you have bought a bandwidth package of 20 Mbit/s for a CEN instance and the connected areas are Mainland China and North America. You can set a cross-region connection bandwidth between US \(Virginia\) and China \(Hangzhou\), China \(Shanghai\), China \(Shenzhen\), or other regions. However, the total bandwidth values set for all the cross-region connections cannot exceed 20 Mbit/s.

 |


