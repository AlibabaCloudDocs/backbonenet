# Manage bandwidth packages {#concept_uzw_bmh_tdb .concept}

To connect networks in different regions, you must buy a bandwidth package and set a cross-region bandwidth value.

## What is a bandwidth package? {#section_kj5_zf3_tdb .section}

A Cloud Enterprise Network \(CEN\) bandwidth package is an abstracted object that includes an interconnection bandwidth and interconnection areas. To buy a bandwidth package, you must specify the areas to connect. An area consists of one or more Alibaba Cloud regions.

The relationship between an area and a region is shown in the following table:

|Area|Included regions|
|:---|:---------------|
|Mainland China|China \(Qingdao\), China \(Beijing\), China \(Zhangjiakou\), China \(Shenzhen\), China \(Hangzhou\), China \(Shanghai\), China \(Hohhot\)|
|North America|US \(Silicon Valley\), US \(Virginia\)|
|Asia Pacific|China \(Hong Kong\), Singapore, Malaysia \(Kuala Lumpur\), Japan \(Tokyo\), India \(Mumbai\), Indonesia \(Jakarta\)|
|Europe|Germany \(Frankfurt\), UK \(London\)|
|Australia|Australia \(Sydney\)|

## Buy a bandwidth package {#section_xlq_3w3_tdb .section}

To connect networks in different regions, you must buy a bandwidth package and set a cross-region bandwidth value. Connecting networks in the same region does not require a bandwidth package.

**Note:** To delete a bandwidth package, you must open a ticket.

To buy a bandwidth package, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  Click the ID of the target CEN instance.
3.  On the CEN page, click the **Bandwidth Packages** tab and then click **Buy Bandwidth Package \(Subscription\)**.
4.  Configure the bandwidth package according to the following information:

    |Configuration|Description|
    |:------------|:----------|
    |**Cloud Enterprise Network**|Select the CEN instance that requires a bandwidth package.|
    |**Area**|Select the area to connect.|
    |**Area**|Select the area to connect.|
    |**Bandwidth**|Set a bandwidth value for the bandwidth package. **Note:** You cannot modify the interconnected areas after the bandwidth package is purchased.

 |
    |**Name**|Enter a name for the bandwidth package.|
    |**Duration**|Select a validity period for your Subscription.|


## Disassociate a bandwidth package {#section_phj_pz3_tdb .section}

You can disassociate a bandwidth package from a CEN instance and associate this bandwidth package with other CEN instances.

**Note:** 

-   Before you disassociate a bandwidth package, delete region connections using the bandwidth package.
-   The bandwidth package is still charged after it is disassociated from a CEN instance. To delete a bandwidth package, open a ticket.

To disassociate a bandwidth package, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  Click the ID of the target CEN instance.
3.  On the CEN page, click the **Bandwidth Packages** tab.
4.  Find the target bandwidth package and click **Unbind** in the **Actions** column.
5.  In the displayed dialog box, click **OK**.

## Associate a bandwidth package {#section_btf_m1j_tdb .section}

You can associate a disassociated bandwidth package to another CEN instance.

To associate a bandwidth package, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  Click the ID of the target CEN instance.
3.  On the CEN page, click the **Bandwidth Packages** tab.
4.  Find the target bandwidth package and click **Bind** in the **Actions** column.
5.  In the displayed dialog box, click **OK**.

## Modify the bandwidth {#section_gg4_z1j_tdb .section}

You can change the bandwidth value of a bandwidth package at any time, and the change takes effect immediately.

To modify the bandwidth, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  Click the ID of the target CEN instance.
3.  On the CEN page, click the **Bandwidth Packages** tab.
4.  Find the target bandwidth package and click **Downgrade** or **Upgrade** in the **Bandwidth** column.

    **Note:** 

    -   Cross-border bandwidth packages \(from Mainland China to areas outside Mainland China\) do not support bandwidth downgrades.
5.  In the Configuration Upgrade section, modify the bandwidth, click **Pay**, and complete the payment.

## Renew a bandwidth package {#section_qjq_4bj_tdb .section}

To renew a bandwidth package, follow these steps:

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  Click the ID of the target CEN instance.
3.  On the CEN page, click the **Bandwidth Packages** tab.
4.  Find the target bandwidth package and click **Renew** in the **Actions** column.
5.  Select the renewal duration and complete the payment.

## References {#section_l1z_ear_pak .section}

[What is Cloud Enterprise Network?](../reseller.en-US/Product Introduction/What is Cloud Enterprise Network?.md#)

