# Use APIs to establish connections {#concept_yvm_ycz_sdb .concept}

You can call CEN APIs to connect networks \(VPCs or VBRs\) in different scenarios.

## Interconnection in the same region using the same account {#section_yjs_dxz_sdb .section}

To connect networks in the same region using the same account, complete the following steps:

1.  Create a CEN instance using the [CreateCen](intl.en-US/API Reference/CEN instances/CreateCen.md#) API.
2.  Attach a network instance to CEN using the [AttachCenChildInstance](intl.en-US/API Reference/CEN instances/AttachCenChildInstance.md) API.

## Cross-regional interconnection using the same account {#section_r1q_3xz_sdb .section}

To connect networks in different regions using the same account, complete the following steps:

1.  Create a CEN instance using the [CreateCen](intl.en-US/API Reference/CEN instances/CreateCen.md) API.
2.  Attach a network to CEN using the [AttachCenChildInstance](intl.en-US/API Reference/CEN instances/AttachCenChildInstance.md) API.
3.  Purchase a bandwidth package using the [CreateCenBandwidthPackage](intl.en-US/API Reference/Cross-region intercommunication bandwidth/CreateCenBandwidthPackage.md) API.
4.  Bind the bandwidth package to CEN using the [AssociateCenBandwidthPackage](intl.en-US/API Reference/Cross-region intercommunication bandwidth/AssociateCenBandwidthPackage.md) API.
5.  Allocate a cross-regional interconnection bandwidth using the [SetCenInterRegionBandwidthLimit](intl.en-US/API Reference/Cross-region interconnection bandwidth/SetCenInterRegionBandwidthLimit.md) API.

## Cross-account interconnection in the same region {#section_yvp_dyz_sdb .section}

The following example shows you how to connect networks in the same region using different accounts:

-   Account A: the owner of CEN and network VPC1.
-   Account B: the owner of network VPC2.

To connect VPC1 and VPC2, complete the following steps:

1.  Account A creates a CEN instance using the [CreateCen](intl.en-US/API Reference/CEN instances/CreateCen.md) API.
2.  Account A attaches VPC1 to CEN using the [AttachCenChildInstance](intl.en-US/API Reference/CEN instances/AttachCenChildInstance.md) API.
3.  Account B authorizes Account A to attach VPC2 using the [GrantInstanceToCen](intl.en-US/API Reference/CEN instances/GrantInstanceToCen.md) API .
4.  Account A attaches VPC2 to CEN using the [AttachCenChildInstance](intl.en-US/API Reference/CEN instances/AttachCenChildInstance.md) API .
5.  Account A purchases a bandwidth package according to the regions of VPC 1 and VPC 2 using the [CreateCenBandwidthPackage](intl.en-US/API Reference/Cross-region intercommunication bandwidth/CreateCenBandwidthPackage.md) API.
6.  Account A binds the bandwidth package to CEN using the [AssociateCenBandwidthPackage](intl.en-US/API Reference/Cross-region intercommunication bandwidth/AssociateCenBandwidthPackage.md) API.
7.  Account A allocates a cross-regional interconnection bandwidth using the [SetCenInterRegionBandwidthLimit](intl.en-US/API Reference/Cross-region interconnection bandwidth/SetCenInterRegionBandwidthLimit.md) API.

