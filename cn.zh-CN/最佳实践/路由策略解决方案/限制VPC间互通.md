# 限制VPC间互通 {#task_1529130 .task}

本文为您介绍如何通过路由策略功能限制加入到云企业网中的VPC间的互通关系。

您已经创建了云企业网实例，并将需要互通的VPC加载到云企业网实例中。详细信息，请参见[创建云企业网实例](../../../../cn.zh-CN/用户指南/管理云企业网实例/创建云企业网实例.md#)和[加载网络实例](../../../../cn.zh-CN/用户指南/管理网络实例/加载网络实例.md#)。

默认情况下，云企业网采取VPC与VPC/VBR/CCN间互通的策略，但在特定场景下，您可能需要限制VPC与VPC/VBR/CCN间的互通关系。

![控制部分VPC间互通](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490554271_zh-CN.png)

如上图，VPC1、VPC2和VPC3均加入到云企业网中。默认情况下，VPC1、VPC2和VPC3全互通，如果您不希望VPC1与VPC2间互通，您可以通过路由策略限制VPC1与VPC2之间的互通关系，VPC1与VPC3、VPC2与VPC3之间依然可以互通。

## 步骤1 设置拒绝VPC1访问VPC2的路由策略 {#section_kys_s9k_8gl .section}

完成以下操作，设置拒绝VPC1访问VPC2的路由策略。

1.  登录[云企业网管理控制台](https://cen.console.aliyun.com/)。
2.  在左侧导航栏，单击**云企业网实例**。
3.  在云企业网实例页面，找到目标云企业网实例，单击**操作**列下的**管理**。
4.  在云企业网页面，单击**路由策略**页签，然后单击**添加路由策略**。
5.  在添加路由策略页面，根据以下信息配置路由策略，然后单击**确定**。 

    -   **策略优先级**：路由策略的优先级。优先级数字越小，优先级越高。 本示例输入**20**。
    -   **地域**：选择路由策略应用的地域。本示例输入**华东1（杭州）**。
    -   **应用方向**：选择路由策略应用的方向。 本示例选择**出地域网关**。
    -   **匹配条件**：路由策略的匹配条件。本示例输入源实例ID列表为VPC2实例ID，目的实例ID列表为VPC1实例ID。
    -   **策略行为**：选择策略行为。本示例选择**拒绝**。
    ![设置拒绝VPC1访问VPC2的路由策略](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490655409_zh-CN.png)

    添加路由策略后，您可以在**路由信息**页签下查看拒绝VPC1访问VPC2的路由。

    ![查看路由信息](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490655414_zh-CN.png)


## 步骤2 设置拒绝VPC2访问VPC1的路由策略 {#section_mwh_cke_twx .section}

完成以下操作，设置拒绝VPC2访问VPC1的路由策略。

1.  在左侧导航栏，单击**云企业网实例**。
2.  在云企业网实例页面，找到目标云企业网实例，单击**操作**列下的**管理**。
3.  在云企业网页面，单击**路由策略**页签，然后单击**添加路由策略**。
4.  在添加路由策略页面，根据以下信息配置路由策略，然后单击**确定**。 

    -   **策略优先级**：路由策略的优先级。优先级数字越小，优先级越高。 本示例输入**50**。
    -   **地域**：选择路由策略应用的地域。本示例输入**华东1（杭州）**。
    -   **应用方向**：选择路由策略应用的方向。 本示例选择**出地域网关**。
    -   **匹配条件**：路由策略的匹配条件。本示例输入源实例ID列表为VPC1实例ID，目的实例ID列表为VPC2实例ID。
    -   **策略行为**：选择策略行为。本示例选择**拒绝**。
    ![设置拒绝VPC2访问VPC1的路由策略](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490655415_zh-CN.png)

    添加路由策略后，您可以在**路由信息**页签下查看拒绝VPC2访问VPC1的路由。

    ![查看路由信息](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490655416_zh-CN.png)


## 步骤3 测试网络连通性 {#section_c10_p33_2k8 .section}

完成以下操作，测试VPC1与VPC2的网络连通性。

1.  登录VPC1下的ECS1实例。
2.  通过ping命令pingVPC2下的ECS2实例的IP地址，验证通信是否正常。 经验证，ECS1实例不能访问ECS2实例。

    ![ECS1 to ECS2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490654751_zh-CN.png)

3.  登录VPC2下的ECS2实例。
4.  通过ping命令pingVPC1下的ECS1实例的IP地址，验证通信是否正常。 经验证，ECS2实例不能访问ECS1实例。

    ![ECS2 to ECS1](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490754752_zh-CN.png)


完成以下操作，测试VPC1与VPC3的网络连通性。

1.  登录VPC1下的ECS1实例。
2.  通过ping命令pingVPC3下的ECS3实例的IP地址，验证通信是否正常。 经验证，ECS1实例可以正常访问ECS3实例。

    ![ECS2 to ECS3](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490754778_zh-CN.png)

3.  登录VPC3下的ECS3实例。
4.  通过ping命令pingVPC1下的ECS1实例的IP地址，验证通信是否正常。 经验证，ECS3实例可以正常访问ECS1实例。

    ![ECS3实例可以正常访问ECS1实例](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490754781_zh-CN.png)


完成以下操作，测试VPC2与VPC3的网络连通性。

1.  登录VPC2下的ECS2实例。
2.  通过ping命令pingVPC3下的ECS3实例的IP地址，验证通信是否正常。 经验证，ECS2实例可以正常访问ECS3实例。

    ![ECS2 to ECS3](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490754778_zh-CN.png)

3.  登录VPC3下的ECS3实例。
4.  通过ping命令pingVPC2下的ECS2实例的IP地址，验证通信是否正常。 经验证，ECS3实例可以正常访问ECS2实例。

    ![ECS3实例可以正常访问ECS2实例](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/1214245/156645490754768_zh-CN.png)


