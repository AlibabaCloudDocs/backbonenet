# API overview {#doc_3055 .concept}

This topic lists available APIs for Cloud Enterprise Network \(CEN\).

## CEN instance APIs {#section_2sh_ep7_lep .section}

|API|Description|
|---|-----------|
|[CreateCen](reseller.en-US/API Reference/CEN instances/CreateCen.md)|Creates a CEN instance.|
|[ModifyCenAttribute](reseller.en-US/API Reference/CEN instances/ModifyCenAttribute.md)|Modifies the name and description of a CEN instance.|
|[DescribeCens](reseller.en-US/API Reference/CEN instances/DescribeCens.md)|Views the details of all CEN instances under your account.|
|[DeleteCen](reseller.en-US/API Reference/CEN instances/DeleteCen.md)|Deletes a CEN instance.|
|[AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md)|Attaches a network instance to a CEN instance.|
|[DescribeCenAttachedChildInstanceAttribute](reseller.en-US/API Reference/CEN instances/DescribeCenAttachedChildInstanceAttribute.md)|Views the details of network instances \(such as VPC, VBR, and CCN\) attached to the CEN instance.|
|[DescribeCenAttachedChildInstances](reseller.en-US/API Reference/CEN instances/DescribeCenAttachedChildInstances.md)|Views the network instances attached to the CEN instance.|
|[DetachCenChildInstance](reseller.en-US/API Reference/CEN instances/DetachCenChildInstance.md)|Detaches a network instance from a CEN instance.|
|[DescribeGrantRulesToCen](reseller.en-US/API Reference/CEN instances/DescribeGrantRulesToCen.md)|Views the permissions that a network instance grants to a CEN instance.|
|[GrantInstanceToCen](reseller.en-US/API Reference/CEN instances/GrantInstanceToCen.md)|Grants permissions to a CEN instance before attaching any network instance that belongs to another account to the CEN instance.|
|[RevokeInstanceFromCen](reseller.en-US/API Reference/CEN instances/RevokeInstanceFromCen.md)|Revokes the permissions granted to a CEN instance by a network instance.|
|[DescribeChildInstanceRegions](reseller.en-US/API Reference/CEN instances/DescribeChildInstanceRegions.md)|Queries the regions of the network instances of the same network type.|

## Bandwidth package APIs {#section_a1x_pjm_hly .section}

|API|Description|
|---|-----------|
|[CreateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/CreateCenBandwidthPackage.md)|Creates a bandwidth package.|
|[AssociateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/AssociateCenBandwidthPackage.md)|Associates a bandwidth package with a CEN instance.|
|[UnassociateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/UnassociateCenBandwidthPackage.md)|Disassociates a bandwidth package from a CEN instance. After you disassociate a bandwidth package from a CEN instance, you can associate the bandwidth package to another CEN instance.|
|[DescribeCenBandwidthPackages](reseller.en-US/API Reference/Bandwidth packages/DescribeCenBandwidthPackages.md)|Views all bandwidth packages under an account.|
|[ModifyCenBandwidthPackageAttribute](reseller.en-US/API Reference/Bandwidth packages/ModifyCenBandwidthPackageAttribute.md)|Modifies the name and description of a bandwidth package.|
|[ModifyCenBandwidthPackageSpec](reseller.en-US/API Reference/Bandwidth packages/ModifyCenBandwidthPackageSpec.md)|Modifies the bandwidth value of a bandwidth package.|
|[DescribeCenGeographicSpanRemainingBandwidth](reseller.en-US/API Reference/Bandwidth packages/DescribeCenGeographicSpanRemainingBandwidth.md)|Queries the remaining available bandwidth of a bandwidth package.|
|[DeleteCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/DeleteCenBandwidthPackage.md)|Deletes a bandwidth package.|
|[DescribeCenGeographicSpans](reseller.en-US/API Reference/Bandwidth packages/DescribeCenGeographicSpans.md)|Queries the connected areas.|

## Cross-region connection bandwidth APIs {#section_jpg_mjb_wvq .section}

|API|Description|
|---|-----------|
|[SetCenInterRegionBandwidthLimit](reseller.en-US/API Reference/Cross-region connection bandwidth/SetCenInterRegionBandwidthLimit.md)|Sets the connection bandwidth across two regions in a bandwidth package.|
|[DescribeCenInterRegionBandwidthLimits](reseller.en-US/API Reference/Cross-region connection bandwidth/DescribeCenInterRegionBandwidthLimits.md)|Queries the cross-region connection bandwidth among different regions.|
|[DescribeGeographicRegionMembership](reseller.en-US/API Reference/Cross-region connection bandwidth/DescribeGeographicRegionMembership.md)|Views all regions in an area.|

## Route management APIs {#section_ytc_big_psw .section}

|API|Description|
|---|-----------|
|[DescribeCenRegionDomainRouteEntries](reseller.en-US/API Reference/Manage routes/DescribeCenRegionDomainRouteEntries.md)|Queries the route entries of a CEN instance in a region.|
|[DescribeRouteConflict](reseller.en-US/API Reference/Manage routes/DescribeRouteConflict.md)|Views conflicting route entries in a VRouter or VBR.|
|[PublishRouteEntries](reseller.en-US/API Reference/Manage routes/PublishRouteEntries.md)|Publishes the route entries of a VPC or VBR to the attached CEN instance.|
|[DescribePublishedRouteEntries](reseller.en-US/API Reference/Manage routes/DescribePublishedRouteEntries.md)|Queries the published routes of a VPC or VBR attached to a CEN instance.|
|[WithdrawPublishedRouteEntries](reseller.en-US/API Reference/Manage routes/WithdrawPublishedRouteEntries.md)|Withdraws the routes that have been published to CEN in a VPC or VBR network instance.|
|[DescribeCenChildInstanceRouteEntries](reseller.en-US/API Reference/Manage routes/DescribeCenChildInstanceRouteEntries.md)|Queries the routes of a network instance.|

## Health check APIs {#section_vne_f5l_po7 .section}

|API|Description|
|---|-----------|
|[EnableCenVbrHealthCheck](reseller.en-US/API Reference/Health checks/EnableCenVbrHealthCheck.md)|Enables the health check function of a VBR to ensure timely detection of faulty physical connections.|
|[DescribeCenVbrHealthCheck](reseller.en-US/API Reference/Health checks/DescribeCenVbrHealthCheck.md)|Queries the health check status of the physical connections in a region.|
|[DisableCenVbrHealthCheck](reseller.en-US/API Reference/Health checks/DisableCenVbrHealthCheck.md)|Disables the health check function of a VBR.|

## Flow log APIs {#section_8sy_idh_kny .section}

|API|Description|
|---|-----------|
|[CreateFlowlog](reseller.en-US/API Reference/Flow logs/CreateFlowlog.md)|Creates a flow log.|
|[ModifyFlowLogAttribute](reseller.en-US/API Reference/Flow logs/ModifyFlowLogAttribute.md)|Modifies the name and description of a flow log.|
|[DescribeFlowlogs](reseller.en-US/API Reference/Flow logs/DescribeFlowlogs.md)|Queries one or more flow logs.|
|[ActiveFlowLog](reseller.en-US/API Reference/Flow logs/ActiveFlowLog.md)|Starts a flow log. After a flow log is started, the traffic information of the specified cloud resource starts to be collected.|
|[DeactiveFlowLog](reseller.en-US/API Reference/Flow logs/DeactiveFlowLog.md)|Stops a flow log. After a flow log is stopped, the traffic information of the specified cloud resource is no longer collected.|
|[DeleteFlowlog](reseller.en-US/API Reference/Flow logs/DeleteFlowlog.md)|Deletes a flow log.|

## Route map APIs {#section_z2l_oce_udc .section}

|API|Description|
|---|-----------|
|[CreateCenRouteMap](reseller.en-US/API Reference/Routing policies/CreateCenRouteMap.md)|Creates a route map.|
|[DescribeCenRouteMaps](reseller.en-US/API Reference/Routing policies/DescribeCenRouteMaps.md)|Queries the route maps of a CEN instance.|
|[ModifyCenRouteMap](reseller.en-US/API Reference/Routing policies/ModifyCenRouteMap.md)|Modifies a route map.|
|[DeleteCenRouteMap](reseller.en-US/API Reference/Routing policies/DeleteCenRouteMap.md)|Deletes a route map.|

## Cloud service APIs {#section_1ms_s3e_zad .section}

|API|Description|
|---|-----------|
|[DeleteRouteServiceInCen](reseller.en-US/API Reference/Cloud services/DeleteRouteServiceInCen.md)|Deletes the access settings of a cloud service.|
|[DescribeRouteServicesInCen](reseller.en-US/API Reference/Cloud services/DescribeRouteServicesInCen.md)|Queries the access settings of cloud services.|
|[ResolveAndRouteServiceInCen](reseller.en-US/API Reference/Cloud services/ResolveAndRouteServiceInCen.md)|Adds cloud service access settings.|

## PrivateZone APIs {#section_1zs_6db_fmb .section}

|API|Description|
|---|-----------|
|[RoutePrivateZoneInCenToVpc](reseller.en-US/API Reference/PrivateZone/RoutePrivateZoneInCenToVpc.md)|Sets PrivateZone.|
|[DescribeCenPrivateZoneRoutes](reseller.en-US/API Reference/PrivateZone/DescribeCenPrivateZoneRoutes.md)|Queries PrivateZone.|
|[UnroutePrivateZoneInCenToVpc](reseller.en-US/API Reference/PrivateZone/UnroutePrivateZoneInCenToVpc.md)|Deletes PrivateZone.|

