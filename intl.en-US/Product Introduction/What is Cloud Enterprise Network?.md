# What is Cloud Enterprise Network? {#concept_jjt_3lz_sdb .concept}

Cloud Enterprise Network \(CEN\) is a service that allows you to create a global network for rapidly building a distributed business system with a hybrid cloud computing solution. CEN enables you to build a secure, private, and enterprise-class interconnected network between VPCs in different regions and your local data centers. CEN provides enterprise-class scalability that automatically responds to your dynamic computing requirements.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3038/1548052700856_en-US.png)

## Components {#section_vyj_tlz_sdb .section}

CEN consists of the following components:

-   CEN instances

    A CEN instance is basic resource of creating and managing your network.

    To connect your network worldwide, you must first create a CEN instance, attach networks to it, and then purchase a bandwidth package and configure a bandwidth for cross-region communication.

-   Networks

    The networks attached to CEN are all connected. Networks include Virtual Private Cloud \(VPC\), Virtual Border Router \(VBR\) and Cloud Connect Network \(CCN\).

-   Bandwidth packages

    A bandwidth package is required only for cross-region communications. When purchasing a bandwidth package, you must specify the interconnection areas for the network resources to communicate. An area is a collection of Alibaba Cloud regions. Please refer to the console for the intercommunication area.

    **Note:** No bandwidth package is required for the intercommunication in the same region. No need to purchase bandwidth packages if you want to connect networks in the same region; However, a bandwidth package is required if you want to connect networks in different regions. \(By default, 1 Kbps bandwidth is provided for connectivity test. To run normal business, you must buy a bandwidth package and set a proper interconnection bandwidth\).

    The relationship between areas and regions are shown in the following table:

    |Area|Included regions|
    |:---|:---------------|
    |Mainland China|China \(Qingdao\), China \(Beijing\), China \(Zhangjiakou\), China \(Shenzhen\), China \(Hangzhou\), China \(Shanghai\), China \(Hohhot\)|
    |North America|US \(Silicon Valley\), US \(Virginia\)|
    |Asia Pacific|Hong Kong, Singapore, Malaysia \(Kuala Lumpur\), Japan \(Tokyo\), India \(Mumbai\), Indonesia \(Jakarta\)|
    |Europe|Germany \(Frankfurt\), UK \(London\)|
    |Australia|Australia \(Sydney\)|

    For example, if you want to connect a network in China \(Beijing\) with a network in US \(Silicon Valley\), the interconnection areas are China Mainland and North America. For more information, see [Scenarios](reseller.en-US/Product Introduction/Scenarios.md#).


