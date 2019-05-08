# RAM鉴权 {#concept_hp4_vcz_sdb .concept}

为了确保账号的安全，建议您使用子账号（RAM user）调用API。用子账号调用API时，您需要先创建一个授权策略，然后将这个授权策略关联给对应的子账号完成资源授权。

在创建授权策略时，您可以通过ARN\(Aliyun Resource Name\) 指定要授权的资源。ARN是阿里云为每个资源定义的一个全局的阿里云资源名称。

|资源类型|授权策略中的资源描述方式（ARN格式）|
|:---|:------------------|
|ceninstance|`acs:cen:*:$accountid: ceninstance /$ceninstanceidacs:cen:*:$accountid: ceninstance /*`|
|cenbandwidthpackage|`acs:cen:*:$accountid: cenbandwidthpackage /$ cenbandwidthpackageidacs:cen:*:$accountid: cenbandwidthpackage/*`|

|鉴权Action|鉴权规则|
|:-------|:---|
|cen: CreateCen|`acs:cen:*:$accountid:ceninstance/*`|
|cen: ModifyCenAttribute|`acs:cen: *:$accountid:ceninstance/$ceninstanceid`|
|cen: DeleteCen|`acs:cen: *:$accountid:ceninstance/$ceninstanceid`|
|cen: DescribeCens|`acs:cen: *:$accountid: ceninstance/*`|
|cen: AttachCenChildInstance| -   `acs:cen:*:$accountid: ceninstance/$ceninstanceid`
-   VPC网络实例规则：

`acs:vpc:$regionid:$accountid:vpc/$vpcid`

-   VBR网络实例规则：

`acs:vpc:$regionid:$accountid:virtualborderrouter/$virtualborderrouterid`


 |
|cen: DetachCenChildInstance| -   `acs:cen:*:$accountid: ceninstance/$ ceninstanceid`
-   VPC网络实例规则：

`acs:vpc:$regionid:$accountid:vpc/$vpcid`

-   VBR网络实例规则：

`acs:vpc:$regionid:$accountid:virtualborderrouter/$virtualborderrouterid`


 |
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
|cen: DescribeRouteConflict| -   VPC网络实例规则：

`acs:vpc:$regionid:$accountid:vpc/$vpcid`

-   VBR网络实例规则：

`acs:vpc:$regionid:$accountid:virtualborderrouter/$virtualborderrouterid`


 |
|cen: DescribeGeographicRegionMembership|无需授权|

