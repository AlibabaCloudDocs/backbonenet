# Limits {#concept_rzs_nc1_tdb .concept}

The following table describes the limits that apply to Cloud Enterprise Networks \(CENs\) and whether you can open a ticket to change these limits.

|Item|Limit|Changes allowed?|
|:---|:----|:---------------|
|The number of CEN instances that can be created for each account|5|Yes. Open a ticket.|
|The number of CEN instances that can be added to each region|10|Yes. Open a ticket to apply for a quota of up to 15 CEN instances.|
|The number of bandwidth packages that you can purchase in either of the interconnected regions in each CEN|1|No.|
|The number of regions in each CEN instance|5|Yes. Open a ticket.|
|Limits on VPCs whose ClassicLink feature is enabled|VPCs cannot use the 10.0.0.0/8 CIDR block.|No.|
|Network instance|No Express Connect can be created for network instances that are added to the CEN.|No.|
|The number of route entries that can be created in each CEN|100|Yes. Open a ticket.|
|Sharing of NAT Gateways through CEN|No|No.|
|Support for cross-region access to cloud services|No|No.|
|Support for cloud services to access network instances in CEN|No|No.|
|Subnet routing|If a VPC has multiple route tables, CEN learns route entries of the primary route table rather than those of the secondary route table. Similarly, the route entries that a VPC learns from CEN can only be added to the primary route table of the VPC.|No.|

