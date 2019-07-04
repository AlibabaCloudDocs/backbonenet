# API概览 {#doc_3055 .concept}

本文档汇总了云企业网的API，具体接口信息请参阅相关文档。

## 云企业网实例 {#section_gqm_wc7_isa .section}

|接口|说明|
|:-|:-|
|[CreateCen](cn.zh-CN/API参考/云企业网实例/CreateCen.md#)|创建云企业网实例。|
|[ModifyCenAttribute](cn.zh-CN/API参考/云企业网实例/ModifyCenAttribute.md#)|修改云企业网实例。|
|[DescribeCens](cn.zh-CN/API参考/云企业网实例/DescribeCens.md#)|查询云企业网实例。|
|[DeleteCen](cn.zh-CN/API参考/云企业网实例/DeleteCen.md#)|删除云企业网实例。|
|[AttachCenChildInstance](cn.zh-CN/API参考/云企业网实例/AttachCenChildInstance.md#)|加载网络实例到云企业网中。|
|[DescribeCenAttachedChildInstances](cn.zh-CN/API参考/云企业网实例/DescribeCenAttachedChildInstances.md#)|查询已加载到云企业网中的网络实例。|
|[DescribeCenAttachedChildInstanceAttribute](cn.zh-CN/API参考/云企业网实例/DescribeCenAttachedChildInstanceAttribute.md#)|查询已加载到云企业网的网络实例的详细信息。|
|[DetachCenChildInstance](cn.zh-CN/API参考/云企业网实例/DetachCenChildInstance.md#)|卸载已加载到云企业网中的网络实例。|
|[GrantInstanceToCen](cn.zh-CN/API参考/云企业网实例/GrantInstanceToCen.md#)|跨账号网络实例授权。|
|[DescribeGrantRulesToCen](cn.zh-CN/API参考/云企业网实例/DescribeGrantRulesToCen.md#)|查询跨账号网络实例授权。|
|[RevokeInstanceFromCen](cn.zh-CN/API参考/云企业网实例/RevokeInstanceFromCen.md#)|撤销跨账号网络实例授权。|

## 带宽包 {#section_p2r_gap_boe .section}

|接口|说明|
|:-|:-|
|[CreateCenBandwidthPackage](cn.zh-CN/API参考/带宽包/CreateCenBandwidthPackage.md#)|购买带宽包。|
|[AssociateCenBandwidthPackage](cn.zh-CN/API参考/带宽包/AssociateCenBandwidthPackage.md#)|将带宽包绑定到指定的云企业网实例。|
|[UnassociateCenBandwidthPackage](cn.zh-CN/API参考/带宽包/UnassociateCenBandwidthPackage.md#)|取消带宽包与云企业网实例之间的绑定。|
|[DescribeCenBandwidthPackages](cn.zh-CN/API参考/带宽包/DescribeCenBandwidthPackages.md#)|查看账户下所有带宽包的详细信息。|
|[ModifyCenBandwidthPackageAttribute](cn.zh-CN/API参考/带宽包/ModifyCenBandwidthPackageAttribute.md#)|修改带宽包的名称和描述信息。|
|[ModifyCenBandwidthPackageSpec](cn.zh-CN/API参考/带宽包/ModifyCenBandwidthPackageSpec.md#)|修改带宽包的带宽值。|

## 跨地域互通带宽 {#section_vem_851_ynw .section}

|接口|说明|
|:-|:-|
|[SetCenInterRegionBandwidthLimit](cn.zh-CN/API参考/跨地域互通带宽/SetCenInterRegionBandwidthLimit.md#)|设置跨地域互通带宽。|
|[DescribeCenInterRegionBandwidthLimits](cn.zh-CN/API参考/跨地域互通带宽/DescribeCenInterRegionBandwidthLimits.md#)|查询各个地域之间的跨地域互通带宽。|
|[DescribeGeographicRegionMembership](cn.zh-CN/API参考/跨地域互通带宽/DescribeGeographicRegionMembership.md#)|查询指定区域内所有的地域。|

## 管理路由 {#section_krh_j74_wwq .section}

|接口|API|
|--|---|
|[DescribeCenRegionDomainRouteEntries](cn.zh-CN/API参考/管理路由/DescribeCenRegionDomainRouteEntries.md#)|查询云企业网实例中某个地域内路由条目的详细信息。|
|[DescribeRouteConflict](cn.zh-CN/API参考/管理路由/DescribeRouteConflict.md#)|查询指定路由器中存在冲突的路由条目。|
|[PublishRouteEntries](cn.zh-CN/API参考/管理路由/PublishRouteEntries.md#)|将加载到云企业网中的VPC或VBR的路由条目发布到云企业网中。|
|[DescribePublishedRouteEntries](cn.zh-CN/API参考/管理路由/DescribePublishedRouteEntries.md#)|查询发布到云企业网中路由条目。|
|[WithdrawPublishedRouteEntries](cn.zh-CN/API参考/管理路由/WithdrawPublishedRouteEntries.md#)|解除VPC或VBR网络实例中已发布到云企业网的路由。|

## 健康检查 {#section_089_r8z_zi0 .section}

|接口|说明|
|--|--|
|[EnableCenVbrHealthCheck](cn.zh-CN/API参考/健康检查/EnableCenVbrHealthCheck.md#)|开启边界路由器（VBR）的健康检查。|
|[DescribeCenVbrHealthCheckRequest](cn.zh-CN/API参考/健康检查/DescribeCenVbrHealthCheckRequest.md#)|查询指定地域内物理专线健康检查的状态。|
|[DisableCenVbrHealthCheck](cn.zh-CN/API参考/健康检查/DisableCenVbrHealthCheck.md#)|关闭指定边界路由器（VBR）的健康检查。|

## 流日志 {#section_s3l_rt9_txj .section}

|接口|说明|
|--|--|
|[CreateFlowlog](cn.zh-CN/API参考/流日志/CreateFlowlog.md#)|创建流日志。|
|[ModifyFlowLogAttribute](cn.zh-CN/API参考/流日志/ModifyFlowLogAttribute.md#)|修改流日志的名称和描述。|
|[DescribeFlowlogs](cn.zh-CN/API参考/流日志/DescribeFlowlogs.md#)|查询流日志。|
|[ActiveFlowLog](cn.zh-CN/API参考/流日志/ActiveFlowLog.md#)|启动流日志。|
|[DeactiveFlowLog](cn.zh-CN/API参考/流日志/DeactiveFlowLog.md#)|停止流日志。|
|[DeleteFlowlog](cn.zh-CN/API参考/流日志/DeleteFlowlog.md#)|删除流日志。|

