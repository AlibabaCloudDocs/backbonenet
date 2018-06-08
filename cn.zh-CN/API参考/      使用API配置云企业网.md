# 使用API配置云企业网 {#concept_yvm_ycz_sdb .concept}

您可以通过调用云企业网的API，实现不同场景下网络实例（VPC或边界路由器）之间的互连。

## 同账号同地域互连 {#section_yjs_dxz_sdb .section}

完成以下操作，连接同一个账号下同地域内的的网络实例：

1.  调用[CreateCen](cn.zh-CN/API参考/云企业网实例/CreateCen.md#)接口，创建云企业网实例。
2.  调用[AttachCenChildInstance](cn.zh-CN/API参考/云企业网实例/AttachCenChildInstance.md)接口，将需要互连的网络实例加载到云企业网实例中。

## 同账号跨地域互连 {#section_r1q_3xz_sdb .section}

完成以下操作，连接同一个账号下不同地域内的网络实例：

1.  调用[CreateCen](cn.zh-CN/API参考/云企业网实例/CreateCen.md)接口，创建云企业网实例。
2.  调用[AttachCenChildInstance](cn.zh-CN/API参考/云企业网实例/AttachCenChildInstance.md)接口，将需要互连的网络实例加载到云企业网实例中。
3.  调用[CreateCenBandwidthPackage](cn.zh-CN/API参考/带宽包/CreateCenBandwidthPackage.md)接口，根据网络实例所在的区域购买带宽包。
4.  调用[AssociateCenBandwidthPackage](cn.zh-CN/API参考/带宽包/AssociateCenBandwidthPackage.md)接口，将带宽包绑定至云企业网实例上。
5.  调用[SetCenInterRegionBandwidthLimit](cn.zh-CN/API参考/跨地域互通带宽/SetCenInterRegionBandwidthLimit.md)接口，设置各地域间的互通带宽。

## 跨账号同地域互连 {#section_yvp_dyz_sdb .section}

本文以如下场景为例介绍如何利用云企业网实现跨账号同地域互连：

-   账号A：云企业网实例和VPC 1的所有者
-   账号B：VPC 2的所有者

完成以下操作，通过云企业网连接VPC 1和VPC 2：

1.  使用账号A调用[CreateCen](cn.zh-CN/API参考/云企业网实例/CreateCen.md)接口，创建云企业网实例。
2.  使用账号A调用[AttachCenChildInstance](cn.zh-CN/API参考/云企业网实例/AttachCenChildInstance.md)接口，将VPC 1加载到云企业网实例中。
3.  使用账号B调用[GrantInstanceToCen](cn.zh-CN/API参考/云企业网实例/GrantInstanceToCen.md)接口，授权账号A加载VPC 2。
4.  使用账号A调用[AttachCenChildInstance](cn.zh-CN/API参考/云企业网实例/AttachCenChildInstance.md)接口，将VPC 2加载到云企业网实例中。
5.  使用账号A调用[CreateCenBandwidthPackage](cn.zh-CN/API参考/带宽包/CreateCenBandwidthPackage.md)接口，根据VPC 1和VPC 2所在的区域购买带宽包。
6.  使用账号A调用[AssociateCenBandwidthPackage](cn.zh-CN/API参考/带宽包/AssociateCenBandwidthPackage.md)接口，将带宽包绑定至云企业网实例上。
7.  使用账号A调用[SetCenInterRegionBandwidthLimit](cn.zh-CN/API参考/跨地域互通带宽/SetCenInterRegionBandwidthLimit.md)接口，设置各地域间的互通带宽。

