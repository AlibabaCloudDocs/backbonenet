# Announcements {#concept_qkg_cnv_m2b .concept}

Cloud Enterprise Network \(CEN\) cannot carry the original AS-PATH when sending BGP route to a leased line \(IDC\), this may cause routing loops in some complex network topology scenarios. Therefore, the following limitations have been added to Cloud Enterprise Network \(CEN\), and will take effect from August 1, 2018:

-   ​All VBRs that are newly attached into CEN are not allowed to learn routing entries from each other or communicate with each other by default. For example, VPC1, VPC2, VBR1 and VBR2 are attached into CEN. Before this change, VPC1/VPC2/VBR1/VBR2 can communicate with each other; while after the change, VBR1/VBR2 and VPC1/VPC2 can be interconnected, but there is no communication between VBR1 and VBR2. If you have intercommunication requirements between VBR, please [submit a ticket](https://workorder.console.aliyun.com/console.htm#/ticket/add?productCode=cbn&commonQuestionId=1448&isSmart=true). Alibaba Cloud technicians will work with you to evaluate the network topology, and follow up the process.
-   By default, a certain model VBR cannot be attached into CEN. If you encounter an error when attaching a VBR into CEN, please [submit a ticket](https://workorder.console.aliyun.com/console.htm#/ticket/add?productCode=cbn&commonQuestionId=1448&isSmart=true). Alibaba Cloud technicians will work with you and follow up the process.​​

These changes only affect the newly attached VBR in CEN. If the VBR already attached into CEN before August 1, 2018, there is no influence.

