# Differences between CEN and Express Connect {#concept_uqw_km4_tdb .concept}

Both Cloud Enterprise Network \(CEN\) and Express Connect can be used to connect an on-premises data center with a VPC to allow access to cloud resources and to build a hybrid cloud.

The following table shows the differences between CEN and Express Connect.

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

