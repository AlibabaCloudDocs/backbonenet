# RAM authentication {#concept_hp4_vcz_sdb .concept}

Before using a RAM user to call an API, you must grant the RAM user the corresponding permission to call the API by creating an authorization policy and attaching the policy to the RAM user.

You can specify the resource that a RAM user has permission to operate in the authorization policy. In the authorization policy, an Alibaba Resource Name \(ARN\) is used to identity the resource to authorize.

|Resource type|ARN format|
|:------------|:---------|
|ceninstance|`acs:cen:*:$accountid: ceninstance /$ceninstanceidacs:cen:*:$accountid: ceninstance`|
|cenbandwidthpackage|`acs:cen:*:$accountid: cenbandwidthpackage /$ cenbandwidthpackageidacs:cen:*:$accountid: cenbandwidthpackage/*`|

|Authorization action| Authorization rule|
|:-------------------|:------------------|
|cen: CreateCen|`acs:cen:*:$accountid:ceninstance/*`|
|cen: ModifyCenAttribute|`acs:cen: *:$accountid:ceninstance/$ceninstanceid`|
|cen: DeleteCen|`acs:cen: *:$accountid:ceninstance/$ceninstanceid`|
|cen: DescribeCens|`acs:cen: *:$accountid: ceninstance/*`|
|cen: AttachCenChildInstance|`acs:cen:*:$accountid: ceninstance/$ceninstanceidVPC:acs:vpc:$regionid:$accountid:vpc/$vpcidVBR:acs:vpc:$regionid:$accountid:virtualborderrouter/$virtualborderrouterid`|
|cen: DetachCenChildInstance|`acs:cen:*:$accountid: ceninstance/$ ceninstanceidVPC:acs:vpc:$regionid:$accountid:vpc/$vpcidVBR:acs:vpc:$regionid:$accountid:virtualborderrouter/$virtualborderrouterid`|
|cen: DescribeCenAttachedChildInstances|`acs:cen:*:$accountid: ceninstance/$ceninstanceid`|
|cen: DescribeCenRegionDomainRouteEntries|`acs:cen:*:$accountid: ceninstance/$ceninstanceid`|
|cen: EnableCenVbrHealthCheck|`acs:cen:*:$accountid: ceninstance/$ceninstanceidacs:vpc:$regionid:$accountid:virtualborderrouter/$virtualborderrouterid`|
|cen: DisableCenVbrHealthCheck|`acs:cen:*:$accountid: ceninstance/$ceninstanceidacs:vpc:$regionid:$accountid:virtualborderrouter/$virtualborderrouterid`|
|cen: DescribeCenVbrHealthCheck|`acs:cen:*:$accountid: ceninstance/$ceninstanceidacs:vpc:$regionid:$accountid:virtualborderrouter/$virtualborderrouterid`|
|cen: CreateCenBandwidthPackage|`acs:cen:*:$accountid: cenbandwidthpackage/*`|
|cen: DescribeCenBandwidthPackage|`acs:cen:*:$accountid: cenbandwidthpackage/*`|
|cen: ModifyCenBandwidthPackageAttribute|`acs:cen:*:$accountid:cenbandwidthpackage/$cenbandwidthpackageid`|
|cen: ModifyCenBandwidthPackageSpec| ```
acs:cen:*:$accountid:cenbandwidthpackage/$cenbandwidthpackageid
```

 |
|cen: DeleteCenBandwidthPackage|`acs:cen:*:$accountid:bandwidthpackage/$cenbandwidthpackageid`|
|cen: AssociateCenBandwidthPackage|`acs:cen:*:$accountid: ceninstance/$ceninstanceidacs:cen:*:$accountid:bandwidthpackage/$cenbandwidthpackageid`|
|cen: UnassociateCenBandwidthPackage|`acs:cen:*:$accountid: ceninstance/$ceninstanceid acs:cen:*:$accountid:bandwidthpackage/$cenbandwidthpackageid`|
|cen: DescribeCenGeographicSpanRemainingBandwidth|`acs:cen:*:$accountid: ceninstance/$ceninstanceid`|
|cen: SetCenInterRegionBandwidthLimit|`acs:cen:*:$accountid: ceninstance/$ceninstanceid`|
|cen: DescribeCenInterRegionBandwidthLimits|`acs:cen:*:$accountid: ceninstance/$ceninstanceid`|
|cen: DescribeRouteConflict|`VPC:acs:vpc:$regionid:$accountid:vpc/$vpcid VBR:acs:vpc:$regionid:$accountid:virtualborderrouter/$virtualborderrouterid`|
|cen: DescribeGeographicRegionMembership|No authentication required.|

