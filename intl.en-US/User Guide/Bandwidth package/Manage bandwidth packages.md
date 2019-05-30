# Manage bandwidth packages {#concept_uzw_bmh_tdb .concept}

To connect networks in different regions, you must buy a bandwidth package and set cross-region bandwidths.

## What is a bandwidth package? {#section_kj5_zf3_tdb .section}

A Cloud Enterprise Network \(CEN\) bandwidth package is an abstracted object that includes an interconnection bandwidth and interconnection areas. To buy a bandwidth package, you must specify the areas to connect. An area consists of one or more Alibaba Cloud regions. The areas in CEN include Mainland China, Asia Pacific, North America, and Europe.

The relationship between an area and a region is shown in the following table:

|Area|Included regions|
|:---|:---------------|
|Mainland China|China \(Qingdao\), China \(Beijing\), China \(Zhangjiakou\), China \(Shenzhen\), China \(Hangzhou\), China \(Shanghai\), China \(Hohhot\)|
|North America|US \(Silicon Valley\), US \(Virginia\)|
|Asia Pacific|Hong Kong, Singapore, Malaysia \(Kuala Lumpur\), Japan \(Tokyo\), India \(Mumbai\), Indonesia \(Jakarta\)|
|Europe|Germany \(Frankfurt\), UK \(London\)|
|Australia|Australia \(Sydney\)|

## Buy a bandwidth package {#section_xlq_3w3_tdb .section}

To connect networks in different regions, you must buy a bandwidth package and set cross-region bandwidths. Connecting networks in the same region does not require a bandwidth package.

**Note:** To delete a bandwidth package, you must open a ticket.

To buy a bandwidth package, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  Click the ID of the target CEN instance.
3.  On the displayed page, click the Bandwidth Packages tab and then click **Buy Bandwidth Package \(Subscription\)**.
4.  Configure the bandwidth package according to the following information:

    |Configuration|Description|
    |:------------|:----------|
    |**Cloud Enterprise Network**|Select the CEN instance that requires a bandwidth package.|
    |**Areas**|Select the areas to connect.|
    |**Bandwidth**|Select the bandwidth of the bandwidth package. **Note:** The interconnection area cannot be modified after the bandwidth package is created.

 |
    |**Bandwidth Package Name**|Enter the name of the bandwidth package.|


## Unbind a bandwidth package {#section_phj_pz3_tdb .section}

You can unbind a bandwidth package from a CEN instance. This bandwidth package can then be bound to other CEN instances.

**Note:** 

-   Before you delete a bandwidth package, delete region connections using the bandwidth package.
-   The bandwidth package is still charged even if it is unbound from a CEN instance. To avoid additional charges, open a ticket to delete the bandwidth package.

To unbind a bandwidth package, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  Click the ID of the target CEN instance.
3.  On the displayed page, click the **Bandwidth Packages** tab.
4.  Locate the target bandwidth package and click **Unbind** in the **Actions** column.
5.  In the displayed dialog box, click **OK**.

## Bind a bandwidth package {#section_btf_m1j_tdb .section}

You can bind an unbound bandwidth package to another CEN instance.

To bind a bandwidth package, complete these steps:

1.  Log on to the [CEN console](http://cen.console.aliyun.com/).
2.  Click the ID of the target CEN instance.
3.  On the displayed page, click the **Bandwidth Packages** tab.
4.  Locate the target bandwidth package and click **Bind** in the **Actions** column.
5.  In the displayed dialog box, click **OK**.

## Modify bandwidth {#section_gg4_z1j_tdb .section}

You can change the bandwidth of the bandwidth package at any time, and the change takes effect immediately.

To modify the bandwidth, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  Click the ID of the target CEN instance.
3.  On the displayed page, click the **Bandwidth Packages** tab.
4.  Locate the target bandwidth package and click **Downgrade** or **Upgrade** in the **Bandwidth** column.
5.  Modify the bandwidth, and then complete the payment.

## Renew a bandwidth package {#section_qjq_4bj_tdb .section}

To renew a bandwidth package, complete these steps:

1.  Log on to the [CEN console](https://cen.console.aliyun.com).
2.  Click the ID of the target CEN instance.
3.  On the displayed page, click the **Bandwidth Packages** tab.
4.  Locate the target bandwidth package and click **Renew** in the **Actions** column.
5.  Select the renew duration and complete the payment.

