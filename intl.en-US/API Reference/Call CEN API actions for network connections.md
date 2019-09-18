# Call CEN API actions for network connections {#task_1512598 .task}

This topic describes how to connect network instances by calling CEN API actions.

## Connect network instances in the same region under the same account {#section_d3z_578_876 .section}

To connect network instances in the same region under the same account, follow these steps:

1.  Call [CreateCen](reseller.en-US/API Reference/CEN instances/CreateCen.md) to create a CEN instance.
2.  Call [AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md) to attach the target network instances to the CEN instance.

## Connect network instances among different regions under the same account {#section_3h6_lua_jg9 .section}

To connect network instances among different regions under the same account, follow these steps:

1.  Call [CreateCen](reseller.en-US/API Reference/CEN instances/CreateCen.md) to create a CEN instance.
2.  Call [AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md) to attach the target network instances to the CEN instance.
3.  Call [CreateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/CreateCenBandwidthPackage.md) to purchase a bandwidth package in the area to which the network instances belong.
4.  Call [AssociateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/AssociateCenBandwidthPackage.md) to associate the bandwidth package with the CEN instance.
5.  Call [SetCenInterRegionBandwidthLimit](reseller.en-US/API Reference/Cross-region connection bandwidth/SetCenInterRegionBandwidthLimit.md) to set cross-region connection bandwidth.

## Connect network instances in the same region under different accounts {#section_w4p_jzf_7bb .section}

In this example, the following accounts are used:

-   Account A: the owner of a CEN instance and VPC1.
-   Account B: the owner of VPC2.

To connect VPC1 and VPC2, follow these steps:

1.  Use account A to call [CreateCen](reseller.en-US/API Reference/CEN instances/CreateCen.md) to create a CEN instance.
2.  Use account A to call [AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md) to attach VPC 1 to the CEN instance.
3.  Use account B to call [GrantInstanceToCen](../../../../reseller.en-US/API reference/Virtual Private Cloud (VPC)/GrantInstanceToCen.md#) to authorize account A to attach VPC2.
4.  Use account A to call [AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md) to attach VPC2 to the CEN instance.

## Connect network instances among different regions under different accounts {#section_u22_6dw_uvl .section}

In this example, the following accounts are used:

-   Account A: the owner of a CEN instance and VPC1.
-   Account B: the owner of VPC 2.

To connect VPC1 and VPC2, follow these steps:

1.  Use account A to call [CreateCen](reseller.en-US/API Reference/CEN instances/CreateCen.md) to create a CEN instance.
2.  Use account A to call [AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md) to attach VPC1 to the CEN instance.
3.  Use account B to call [GrantInstanceToCen](../../../../reseller.en-US/API reference/Virtual Private Cloud (VPC)/GrantInstanceToCen.md#) to authorize account A to attach VPC2.
4.  Use account A to call [AttachCenChildInstance](reseller.en-US/API Reference/CEN instances/AttachCenChildInstance.md) to attach VPC2 to the CEN instance.
5.  Use account A to call [CreateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/CreateCenBandwidthPackage.md) to purchase a bandwidth package in the area to which VPC1 and VPC2 belong.
6.  Use account A to call [AssociateCenBandwidthPackage](reseller.en-US/API Reference/Bandwidth packages/AssociateCenBandwidthPackage.md) to associate the bandwidth package with the CEN instance.
7.  Use account A to call [SetCenInterRegionBandwidthLimit](reseller.en-US/API Reference/Cross-region connection bandwidth/SetCenInterRegionBandwidthLimit.md) to set connection bandwidth between the two regions.

