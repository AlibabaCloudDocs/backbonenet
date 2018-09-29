# Manage bandwidth packages {#concept_uzw_bmh_tdb .concept}

To connect networks in different regions, you must buy a bandwidth package and set cross-region bandwidths.

## What is the bandwidth package {#section_kj5_zf3_tdb .section}

The CEN bandwidth package is an abstracted object that includes an interconnection bandwidth and interconnection areas. To buy a bandwidth package, you must specify the areas to connect. An area consists of one or more Alibaba Cloud regions. The areas in CEN include Mainland China, Asia Pacific, North America, and Europe.

The relationship between a region and a region is shown in the following table:

|Area|Included regions|
|:---|:---------------|
|Mainland China|China \(Qingdao\), China \(Beijing\), China \(Zhangjiakou\), China \(Shenzhen\), China \(Hangzhou\), China \(Shanghai\), China \(Hohhot\), China \(Wuhan\)|
|North America|US \(Silicon Valley\), US \(Virginia\)|
|Asia Pacific|Hong Kong, Singapore, Malaysia \(Kuala Lumpur\), Japan \(Tokyo\), India \(Mumbai\), Indonesia \(Jakarta\)|
|Europe|Germany \(Frankfurt\), UK \(London\)|
|Australia|Australia \(Sydney\)|

## Buy a bandwidth package {#section_xlq_3w3_tdb .section}

To connect networks in different regions, you must buy a bandwidth package and set cross-region bandwidths. Connecting networks in the same region does not require a bandwidth package.

**Note:** To delete a bandwidth package, you must open a ticket.

To buy a bandwidth package, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  Click the ID of the target cloud enterprise instance.
3.  On the Bandwidth Packages page, click **Buy Bandwidth Package**, and then click **Buy Bandwidth Package \(Subscription\)**.
4.  Configure the bandwidth package according to the following information:

    |Configuration|Description|
    |:------------|:----------|
    |**Cloud Enterprise Network**|Select the CEN instance that requires a bandwidth package.|
    |**Areas**|Select the areas to connect.|
    |**Bandwidth**|Select the bandwidth of the bandwidth package.**Note:** The interconnection area cannot be modified after the bandwidth package is created.

|
    |**Bandwidth Package Name**|Enter the name of the bandwidth package.|


## Unbind bandwidth package {#section_phj_pz3_tdb .section}

You can unbind bandwidth packets from an instance of cloud enterprise network, this bandwidth package can then be bound to other cloud Enterprise Network instances.

**Note:** 

-   Before deleting a bandwidth package, delete region connections using the bandwidth package.
-   The bandwidth package is still charged even if it is unbound from a CEN instance. To avoid additional charges, open a ticket to delete the bandwidth package.

To unbind a bandwidth package, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  Click the ID of the target cloud enterprise instance.
3.  On the CEN page, click **Bandwidth Packages**.
4.  Click the **Unbind** option under the **Action** column of the target bandwidth package.
5.  In the displayed dialog, click **Confirm**.

## Bind bandwidth package {#section_btf_m1j_tdb .section}

You can bind an unbound bandwidth package to another CEN instance.

To bind a bandwidth package, complete these steps:

1.  Log on to the [CEN console](http://cen.console.aliyun.com/).
2.  Click the ID of the target cloud enterprise instance.
3.  On the CEN page, click the **Bandwidth Packages** tab.
4.  Click the **Bind** option under the **Action** column of the target bandwidth package.
5.  In the displayed dialog, click **Confirm**.

## Modify bandwidth {#section_gg4_z1j_tdb .section}

You can change the bandwidth of the bandwidth package at any time, and the change takes effect immediately.

To modify the bandwidth, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  Click the ID of the target cloud enterprise instance.
3.  On the CEN page, click the **Bandwidth Packages** tab.
4.  Click the **Downgrade** or the **Upgrade** option under the **Bandwidth** column of the target bandwidth package.
5.  Modify the bandwidth, and then complete the payment.

## Renew a bandwidth package {#section_qjq_4bj_tdb .section}

To renew a bandwidth package, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  Click the ID of the target cloud enterprise instance.
3.  On the CEN page, click the **Bandwidth Packages** tab.
4.  Click the **Renew** option under the **Action** column of the target bandwidth package.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3050/1538231964877_en-US.png)

5.  Select the renew duration and complete the payment.

