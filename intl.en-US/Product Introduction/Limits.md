# Limits {#concept_rzs_nc1_tdb .concept}

The following table describes the limits of different items in Cloud Enterprise Network \(CEN\) and whether a ticket can be opened to adjust the limit.

|Item|Limit|Can I open a ticket?|
|:---|:----|:-------------------|
|The number of CEN instances per account|5|Yes|
|The number of attached networks per region|10|Yes. You can apply for up to 15 networks.|
|The number of bandwidth packages in the same connected areas per account in a CEN instance|1|No|
|The number of associated regions per CEN instance|5|Yes|
|Limits on VPCs with ClassicLink enabled|The VPC cannot use the IP address range 10.0.0.0/8.|No|
|Networks|You cannot attach VPCs or VBRs that are using Express Connect to a CEN instance.|No|
|The number of route entries per CEN instance|100|Yes|
|Can I share NAT Gateway through CEN?|No|No|
|Is cross-region access to cloud resources supported?|No|No|
|Can cloud resources access networks attached to CEN?|No|No|
|Subnet routing|If a VPC has more than one route table, CEN only learns route entries of the primary route table and does not learn route entries from the customized route tables. Similarly, the route entries that a VPC learned from CEN are added to the primary route table only.|No|
|Is Ant Financial Cloud supported?|No|No|

