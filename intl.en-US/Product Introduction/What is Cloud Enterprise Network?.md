# What is Cloud Enterprise Network? {#concept_jjt_3lz_sdb .concept}

By using Cloud Enterprise Network \(CEN\), you can build private network communication channels between VPCs or between VPCs and on-premises data centers. CEN uses automatic route distribution and learning, which can improve the network convergence and the quality and security of cross-network communication, and achieve the interconnection of all network resources.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3038/1565800892856_en-US.png)

## Components {#section_vyj_tlz_sdb .section}

CEN consists of the following components:

-   CEN instances

    A CEN instance is the basis of creating and managing your networks.

    To connect your networks worldwide, you must first create a CEN instance, attach networks to it, and then purchase a bandwidth package and configure a bandwidth for cross-region communication.

-   Networks

    The networks attached to CEN are all connected. Networks include Virtual Private Clouds \(VPCs\), Virtual Border Routers \(VBRs\), and Cloud Connect Networks \(CCNs\).

-   Bandwidth packages

    A bandwidth package is required only for cross-region communication. When purchasing a bandwidth package, you must specify the interconnection areas for the network resources to communicate. An area is a collection of Alibaba Cloud regions. You can see the areas that can be connected in the console.

    **Note:** No bandwidth package is required if you want to connect networks in the same region. However, if you want to connect networks in different regions, you must purchase a bandwidth package. By default, 1 Kbit/s bandwidth is provided for connected networks so that you can perform connectivity tests. To run normal services, you must buy a bandwidth package and set a proper connection bandwidth.

    The relationship between areas and regions are shown in the following table.

    |Area|Included regions|
    |:---|:---------------|
    |Mainland China|China \(Qingdao\), China \(Beijing\), China \(Zhangjiakou\), China \(Shenzhen\), China \(Hangzhou\), China \(Shanghai\), China \(Hohhot\)|
    |North America|US \(Silicon Valley\), US \(Virginia\)|
    |Asia Pacific|Hong Kong, Singapore, Malaysia \(Kuala Lumpur\), Japan \(Tokyo\), India \(Mumbai\), Indonesia \(Jakarta\)|
    |Europe|Germany \(Frankfurt\), UK \(London\)|
    |Australia|Australia \(Sydney\)|

    For example, if you want to connect a network in China \(Beijing\) with a network in US \(Silicon Valley\), the areas to be connected are China Mainland and North America. For more information, see [Scenarios](reseller.en-US/Product Introduction/Scenarios.md#).


