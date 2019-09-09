# Call CEN API actions to establish connections {#concept_yvm_ycz_sdb .concept}

This topic describes how to call CEN API actions to establish connections among network instances \(VPCs or VBRs\) in different scenarios.

## Connections in the same region under the same account {#section_yjs_dxz_sdb .section}

To connect network instances in the same region under the same account, follow these steps:

1.  Call [EN-US\_TP\_3062.md\#](reseller.en-US/API Reference/CEN instances/CreateCen.md#) to create a CEN instance.
2.  Call [AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md) to attach the target network instances to the CEN instance.

## Connections among different regions under the same account {#section_r1q_3xz_sdb .section}

To connect network instances among different regions under the same account, follow these steps:

1.  Call [CreateCen](reseller.en-US/API Reference/CEN instances/CreateCen.md) to create a CEN instance.
2.  Call [AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md) to attach the target network instances to the CEN instance.
3.  Call [CreateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/CreateCenBandwidthPackage.md) to purchase a bandwidth package.
4.  Call [AssociateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/AssociateCenBandwidthPackage.md) to associate the bandwidth package with the CEN instance.
5.  Call [SetCenInterRegionBandwidthLimit](reseller.en-US/API Reference/Cross-region connection bandwidth/SetCenInterRegionBandwidthLimit.md) to set cross-regional connection bandwidth.

## Connections in the same region under different accounts {#section_yvp_dyz_sdb .section}

In this example, the following accounts are used:

-   Account A: the owner of a CEN instance and VPC1.
-   Account B: the owner of VPC2.

To connect VPC1 and VPC2, complete the following steps:

1.  Use account A to call [CreateCen](reseller.en-US/API Reference/CEN instances/CreateCen.md) to create a CEN instance.
2.  Use account A to call [AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md) to attach VPC1 to the CEN instance.
3.  Use account B to call [GrantInstanceToCen](../../../../reseller.en-US/API reference/Virtual Private Cloud (VPC)/GrantInstanceToCen.md#) to authorize account A to attach VPC2.
4.  Use account A to call [AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md) to attach VPC2 to the CEN instance.
5.  Use account A to call [CreateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/CreateCenBandwidthPackage.md) to purchase a bandwidth package in the region to which VPC1 and VPC2 belong.
6.  Use account A to call [AssociateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/AssociateCenBandwidthPackage.md) to associate the bandwidth package with the CEN instance.
7.  Use account A to call [SetCenInterRegionBandwidthLimit](reseller.en-US/API Reference/Cross-region connection bandwidth/SetCenInterRegionBandwidthLimit.md) to set cross-regional connection bandwidth.

