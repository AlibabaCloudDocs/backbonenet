# Migrate VPCs and VBRs to CEN {#concept_778470 .concept}

You can migrate the VPCs and Virtual Border Routers \(VBRs\) that are using existing Express Connect peering connections to Cloud Enterprise Network \(CEN\). By using CEN, you can build private network communication channels between VPCs or between VPCs and on-premises data centers. CEN uses automatic route distribution and learning, which can improve the network convergence and the quality and security of cross-network communication, and achieve the interconnection of all your network resources.

## Migration procedure {#section_6yx_bw0_njk .section}

After you complete necessary preparations, add the VPCs and VBRs that use peering connections to a CEN instance, and then manage routes.

CEN automatically learns and distributes routes of the added networks. After a VPC or VBR in a peering connection is added to a CEN instance, the static route configured for the peering connection takes precedence over the dynamic route of the CEN instance. Specifically, if a static route is configured for the peering connection, no route that is more detailed than or the same as the static route is allowed to be learnt by the CEN instance. In this case, we recommend that you divide a large route segment into smaller route segments and delete these routes after CEN learns the routes to ensure smooth migration. For more information about the migration procedure, see [Migrate a VPC in a peering connection to a CEN instance](intl.en-US/Best Practices/Migrate Express Connect peering connections to CEN/Migrate a VPC in a peering connection to a CEN instance.md#) and [Migrate a VBR in a peering connection to a CEN instance](intl.en-US/Best Practices/Migrate Express Connect peering connections to CEN/Migrate a VBR in a peering connection to a CEN instance.md#).

## Differences between CEN and Express Connect peering connections {#section_1gn_wik_ift .section}

The following table compares the basic functions of CEN and Express Connect peering connections.

|Item|CEN|Express Connect|
|:---|:--|:--------------|
|Network connection| Network-wide interconnection

 All networks \(VPCs and Virtual Border Routers\) associated with a CEN instance are interconnected with each other. A secure, reliable, and high-speed intranet communication channel can be established between any two networks.

 | Single point interconnection

 Express Connect connections cannot be extended. Specifically, the VPCs or on-premises data centers that are connected through Express Connect can only communicate with the peer VPCs.

 |
|Route management| Dynamic learning

 Based on the Fullmesh link, CEN dynamically learns and distributes routes, which improves the convergence of routes, and the quality and security of network communication.

 | Manual configuration

 Express Connect requires end-to-end manual route configuration.

 |
|Bandwidth management| Cross-region shared bandwidth package

 CEN provides bandwidth packages which are sold by region to facilitate cross-region bandwidth adjustments. Bandwidth packages also help optimize resource allocation and save costs.

 | Point-to-point purchase

 The bandwidth of an Express Connect connection must be specified when you create the connection. You can adjust the bandwidth value after you create an Express Connect connection, but you cannot change the connected regions.

 |

