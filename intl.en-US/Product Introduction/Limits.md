# Limits {#concept_rzs_nc1_tdb .concept}

Before using CEN, read the limits first.

|Resource|Default limit|Exception|
|:-------|:------------|:--------|
|The number of CEN instances per account|5|Open a ticket|
|The number of attached networks per region|10|Open a ticket|
|The number of bandwidth packages in the same connected areas per account in a CEN instance|1|No exception|
|The number of associated regions per CEN instance|5|Open a ticket|
|Limits on VPC with ClassicLink enabled|The VPC cannot use the IP address range 10.0.0.0/8.|No exception|
|Networks|You cannot attach VPCs or VBRs that are using Express Connect to a CEN instance.|No exception|
|The number of route entries per CEN instance|100|Open a ticket|
|Share NAT Gateway through CEN|No|No exception|
|Cross-region access to cloud resources|No|No exception|
|Cloud resources access networks attached to CEN|No|No exception|
|Subnet routing|If a VPC has more than one route table, CEN only learns route entries of the primary route table and does not learn route entries from the customized route tables. Similarly, the route entries that a VPC learned from CEN are added to the primary route table only.|No exception|
|Ant Financial Cloud|No|No exception|

