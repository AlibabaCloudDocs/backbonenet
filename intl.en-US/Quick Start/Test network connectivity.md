# Test network connectivity {#task_1563808 .task}

This topic describes how to test the network connectivity between two network instances attached to a CEN instance.

A cross-region connection bandwidth is configured for the network instances if the two network instances belong to different regions. For more information, see [Set a cross-region connection bandwidth](reseller.en-US/Quick Start/Set a cross-region connection bandwidth.md#).

The following table describes two ECS instances \(ECS 1 and ECS 2\) that are used as examples in this procedure.

|Configuration|ECS 1|ECS 2|
|-------------|-----|-----|
|Private IP address|192.168.1.41|192.168.136.60|
|Region|China \(Shanghai\)|China \(Hangzhou\)|

1.  Log on to ECS 2.
2.  Ping the private IP address of ECS 1 to check whether the connection between ECS 1 and ECS 2 is successful. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1240739/156740394954541_en-US.png)


