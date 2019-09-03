# Alibaba Cloud CEN tutorials {#concept_ppf_c3b_tdb .concept}

This topic provides an overview of Cloud Enterprise Network \(CEN\) tutorials. When you use a CEN, you can build a global network that consists of interconnected hybrid clouds and distributed service systems. You can attach network instances to a CEN instance so that the network instances can communicate with each other.

![CEN](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3043/156747247254379_en-US.png)

Typically, the configurations shown in the following figure are required when a CEN is used for network interconnection. However, these configurations may vary depending on the region and account to which network instances belong. Such network instances include VPCs, VBRs associated with on-premises data centers, CCNs associated with local branches or headquarters. Therefore, we recommend that you use these configurations selectively according to your specific business needs and network resources.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3043/156747247254404_en-US.png)

This tutorial uses the following two ECS instances deployed in different zones under different accounts as an example to describe how to establish intranet communication through a CEN.

|Configuration|ECS1|ECS2|
|-------------|----|----|
|Private IP address|192.168.1.41|192.168.136.60|
|Region|China \(Shanghai\)|China \(Hangzhou\)|
|Account|123157908xxxx123|1954105xxxx83124|
|VPC|vpc-uf6w8bk8dxxxxfj0b7k94|vpc-bp1dylcs2xxxxnkckxxxx|

