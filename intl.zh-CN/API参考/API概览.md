# API概览 {#doc_3055 .concept}

云企业网提供以下相关API接口。

## 云企业网实例 {#section_2sh_ep7_lep .section}

|API|描述|
|---|--|
|[CreateCen](intl.zh-CN/API参考/云企业网实例/CreateCen.md)|调用CreateCen接口创建云企业网实例。|
|[ModifyCenAttribute](intl.zh-CN/API参考/云企业网实例/ModifyCenAttribute.md)|调用ModifyCenAttribute编辑云企业网实例的名称和描述信息。|
|[DescribeCens](intl.zh-CN/API参考/云企业网实例/DescribeCens.md)|调用DescribeCens查看账户下所有云企业网实例的详细信息。|
|[DeleteCen](intl.zh-CN/API参考/云企业网实例/DeleteCen.md)|调用DeleteCen删除指定的云企业网实例。|
|[AttachCenChildInstance](intl.zh-CN/API参考/云企业网实例/AttachCenChildInstance.md)|调用AttachCenChildInstance将网络实例加载到云企业网实例中。|
|[DescribeCenAttachedChildInstanceAttribute](intl.zh-CN/API参考/云企业网实例/DescribeCenAttachedChildInstanceAttribute.md)|调用DescribeCenAttachedChildInstanceAttribute查看加载到CEN中的网络实例（VPC，VBR，CCN）的详细信息。|
|[DescribeCenAttachedChildInstances](intl.zh-CN/API参考/云企业网实例/DescribeCenAttachedChildInstances.md)|调用DescribeCenAttachedChildInstances查看云企业网实例下已加载的网络实例。|
|[DetachCenChildInstance](intl.zh-CN/API参考/云企业网实例/DetachCenChildInstance.md)|调用DetachCenChildInstance从云企业网实例中解绑指定的网络实例。|
|[DescribeGrantRulesToCen](intl.zh-CN/API参考/云企业网实例/DescribeGrantRulesToCen.md)|调用DescribeGrantRulesToCen查看网络实例对云企业网实例的授权关系。|
|[GrantInstanceToCen](intl.zh-CN/API参考/云企业网实例/GrantInstanceToCen.md)|在加载其他账号的网络实例前，需要在网络实例所在的账号下为云企业网实例授权。|
|[RevokeInstanceFromCen](intl.zh-CN/API参考/云企业网实例/RevokeInstanceFromCen.md)|撤销网络实例对指定云企业网实例的授权。|
|[DescribeChildInstanceRegions](intl.zh-CN/API参考/云企业网实例/DescribeChildInstanceRegions.md)|调用DescribeChildInstanceRegions查询支持加载到云企业网中的网络实例的地域。|

## 带宽包 {#section_a1x_pjm_hly .section}

|API|描述|
|---|--|
|[CreateCenBandwidthPackage](intl.zh-CN/API参考/带宽包/CreateCenBandwidthPackage.md)|调用CreateCenBandwidthPackage创建带宽包。|
|[AssociateCenBandwidthPackage](intl.zh-CN/API参考/带宽包/AssociateCenBandwidthPackage.md)|调用AssociateCenBandwidthPackage将带宽包绑定到指定的云企业网实例。|
|[UnassociateCenBandwidthPackage](intl.zh-CN/API参考/带宽包/UnassociateCenBandwidthPackage.md)|调用UnassociateCenBandwidthPackage将带宽包与云企业网实例之间的绑定取消。取消绑定后，该带宽包可以绑定至其他云企业网实例。|
|[DescribeCenBandwidthPackages](intl.zh-CN/API参考/带宽包/DescribeCenBandwidthPackages.md)|查看账户下所有带宽包的详细信息。|
|[ModifyCenBandwidthPackageAttribute](intl.zh-CN/API参考/带宽包/ModifyCenBandwidthPackageAttribute.md)|调用ModifyCenBandwidthPackageAttribute编辑带宽包的名称和描述信息。|
|[ModifyCenBandwidthPackageSpec](intl.zh-CN/API参考/带宽包/ModifyCenBandwidthPackageSpec.md)|调用ModifyCenBandwidthPackageSpec更改带宽包的带宽值。|
|[DescribeCenGeographicSpanRemainingBandwidth](intl.zh-CN/API参考/带宽包/DescribeCenGeographicSpanRemainingBandwidth.md)|调用DescribeCenGeographicSpanRemainingBandwidth查询指定带宽包的剩余可用带宽值。|
|[DeleteCenBandwidthPackage](intl.zh-CN/API参考/带宽包/DeleteCenBandwidthPackage.md)|调用DeleteCenBandwidthPackage删除带宽包。|
|[DescribeCenGeographicSpans](intl.zh-CN/API参考/带宽包/DescribeCenGeographicSpans.md)|调用DescribeCenGeographicSpans查询互通区域信息。|

## 跨地域互通带宽 {#section_jpg_mjb_wvq .section}

|API|描述|
|---|--|
|[SetCenInterRegionBandwidthLimit](intl.zh-CN/API参考/跨地域互通带宽/SetCenInterRegionBandwidthLimit.md)|调用SetCenInterRegionBandwidthLimit设置带宽包中两个地域间的跨地域互通带宽。|
|[DescribeCenInterRegionBandwidthLimits](intl.zh-CN/API参考/跨地域互通带宽/DescribeCenInterRegionBandwidthLimits.md)|调用DescribeCenInterRegionBandwidthLimits查询各个地域之间的跨地域互通带宽。|
|[DescribeGeographicRegionMembership](intl.zh-CN/API参考/跨地域互通带宽/DescribeGeographicRegionMembership.md)|调用DescribeGeographicRegionMembership查看指定区域内所有的地域。|

## 管理路由 {#section_ytc_big_psw .section}

|API|描述|
|---|--|
|[DescribeCenRegionDomainRouteEntries](intl.zh-CN/API参考/管理路由/DescribeCenRegionDomainRouteEntries.md)|调用DescribeCenRegionDomainRouteEntries查询云企业网实例中某个地域内路由条目的详细信息。|
|[DescribeRouteConflict](intl.zh-CN/API参考/管理路由/DescribeRouteConflict.md)|调用DescribeRouteConflict查看指定路由器（VRouter或VBR）中存在冲突的路由条目。|
|[PublishRouteEntries](intl.zh-CN/API参考/管理路由/PublishRouteEntries.md)|调用PublishRouteEntries将加载到CEN中的VPC或VBR的路由条目发布到CEN中。|
|[DescribePublishedRouteEntries](intl.zh-CN/API参考/管理路由/DescribePublishedRouteEntries.md)|调用DescribePublishedRouteEntries查询已加载到CEN网络实例（VPC和VBR）的各条路由在CEN中的发布情况。|
|[WithdrawPublishedRouteEntries](intl.zh-CN/API参考/管理路由/WithdrawPublishedRouteEntries.md)|调用WithdrawPublishedRouteEntries解除VPC或VBR网络实例中已发布到CEN的路由。|
|[DescribeCenChildInstanceRouteEntries](intl.zh-CN/API参考/管理路由/DescribeCenChildInstanceRouteEntries.md)|调用DescribeCenChildInstanceRouteEntries查询云企业网的网络实例路由条目。|

## 健康检查 {#section_vne_f5l_po7 .section}

|API|描述|
|---|--|
|[EnableCenVbrHealthCheck](intl.zh-CN/API参考/健康检查/EnableCenVbrHealthCheck.md)|调用EnableCenVbrHealthCheck开启边界路由器（VBR）的健康检查，确保及时发现出现故障的物理专线。|
|[DescribeCenVbrHealthCheck](intl.zh-CN/API参考/健康检查/DescribeCenVbrHealthCheck.md)|调用DescribeCenVbrHealthCheck查询指定地域内物理专线健康检查的状态。|
|[DisableCenVbrHealthCheck](intl.zh-CN/API参考/健康检查/DisableCenVbrHealthCheck.md)|调用DisableCenVbrHealthCheck关闭指定边界路由器（VBR）的健康检查。|

## 流日志 {#section_8sy_idh_kny .section}

|API|描述|
|---|--|
|[CreateFlowlog](intl.zh-CN/API参考/流日志/CreateFlowlog.md)|调用CreateFlowlog接口创建流日志。|
|[ModifyFlowLogAttribute](intl.zh-CN/API参考/流日志/ModifyFlowLogAttribute.md)|调用ModifyFlowLogAttribute接口编辑流日志的名称和描述。|
|[DescribeFlowlogs](intl.zh-CN/API参考/流日志/DescribeFlowlogs.md)|调用DescribeFlowlogs接口查询流日志。|
|[ActiveFlowLog](intl.zh-CN/API参考/流日志/ActiveFlowLog.md)|调用ActiveFlowLog接口启动流日志，启动后开始捕获指定资源的流量。|
|[DeactiveFlowLog](intl.zh-CN/API参考/流日志/DeactiveFlowLog.md)|调用DeactiveFlowLog接口停止流日志，停止后不再捕获指定资源的流量。|
|[DeleteFlowlog](intl.zh-CN/API参考/流日志/DeleteFlowlog.md)|调用DeleteFlowlog接口删除流日志。|

## 路由策略 {#section_z2l_oce_udc .section}

|API|描述|
|---|--|
|[CreateCenRouteMap](intl.zh-CN/API参考/路由策略/CreateCenRouteMap.md)|调用CreateCenRouteMap接口创建路由策略。|
|[DescribeCenRouteMaps](intl.zh-CN/API参考/路由策略/DescribeCenRouteMaps.md)|调用DescribeCenRouteMaps接口查询路由策略。|
|[ModifyCenRouteMap](intl.zh-CN/API参考/路由策略/ModifyCenRouteMap.md)|调用ModifyCenRouteMap接口修改路由策略。|
|[DeleteCenRouteMap](intl.zh-CN/API参考/路由策略/DeleteCenRouteMap.md)|调用DeleteCenRouteMap接口删除路由策略。|

## 云服务 {#section_1ms_s3e_zad .section}

|API|描述|
|---|--|
|[DeleteRouteServiceInCen](intl.zh-CN/API参考/云服务/DeleteRouteServiceInCen.md)|调用DeleteRouteServiceInCen删除云服务。|
|[DescribeRouteServicesInCen](intl.zh-CN/API参考/云服务/DescribeRouteServicesInCen.md)|调用DescribeRouteServicesInCen查询云服务。|
|[ResolveAndRouteServiceInCen](intl.zh-CN/API参考/云服务/ResolveAndRouteServiceInCen.md)|调用ResolveAndRouteServiceInCen设置云服务。|

## PrivateZone {#section_1zs_6db_fmb .section}

|API|描述|
|---|--|
|[RoutePrivateZoneInCenToVpc](intl.zh-CN/API参考/PrivateZone/RoutePrivateZoneInCenToVpc.md)|调用RoutePrivateZoneInCenToVpc设置PrivateZone。|
|[DescribeCenPrivateZoneRoutes](intl.zh-CN/API参考/PrivateZone/DescribeCenPrivateZoneRoutes.md)|调用DescribeCenPrivateZoneRoutes查询PrivateZone。|
|[UnroutePrivateZoneInCenToVpc](intl.zh-CN/API参考/PrivateZone/UnroutePrivateZoneInCenToVpc.md)|调用UnroutePrivateZoneInCenToVpc删除PrivateZone。|

