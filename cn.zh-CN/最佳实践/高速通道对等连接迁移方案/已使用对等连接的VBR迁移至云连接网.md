# 已使用对等连接的VBR迁移至云连接网 {#concept_778480 .concept}

您可以将已使用高速通道对等连接的边界路由器（VBR）平滑迁移至云企业网。云企业网（Cloud Enterprise Network, CEN）可以在不同专有网络之间，专有网络与本地数据中心间搭建私网通信通道。通过自动路由分发及学习，CEN可以提高网络的快速收敛和跨网络通信的质量和安全性，实现全网资源的互通。

## 准备工作 {#section_eqb_6jw_1q8 .section}

如果您要使用已有的CEN实例，确保网络重叠功能已开启。

**说明：** 如果存在未开启网络重叠功能的老实例，请开启网络重叠功能。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630333/156145090749935_zh-CN.png)

## 迁移操作 {#section_jva_nyi_5pq .section}

参考以下步骤，将已使用对等连接的VBR迁移至云企业网：

**说明：** 在迁移前，确保您已经完成所需的准备工作。

1.  如果VBR配置了健康检查，建议您先在高速通道控制台删除健康检查配置。
2.  登录[云企业网控制台](https://cen.console.aliyun.com)。
3.  在云企业网实例页面，单击CEN实例ID链接。
4.  在网络实例管理页面，单击**加载网络实例**加载要迁移的VBR和VPC实例。详细说明，请参见[网络实例](../cn.zh-CN/用户指南/网络实例.md#)。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630370/156145090749948_zh-CN.png)

5.  如果需要跨地域互通，请在CEN实例中购买带宽包并配置私网互通带宽。

    详细说明，请参见[设置跨地域互通带宽](../cn.zh-CN/用户指南/跨地域互通带宽.md#section_gtq_n5n_tdb)。

6.  如果VPC中存在指向ECS实例、VPN网关、HAVIP等路由条目，请根据连通性需求，在VPC控制台将这些路由发布到CEN中。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630439/156145090749940_zh-CN.png)

7.  如果本地IDC需要访问云服务例如OSS和PrivateZone等，请在云企业网控制台进行配置。

    配置说明，请参见[设置云服务访问](../cn.zh-CN/用户指南/访问云服务/设置云服务访问.md#)和[设置PrivateZone访问](../cn.zh-CN/用户指南/访问云服务/PrivateZone/设置PrivateZone访问.md#)。

8.  登录[CEN控制台](https://cen.console.aliyun.com/cen/detail/cen-0e7i2gmdfs6ymbxgay/route)，在**路由信息**页面查看路由配置。确保加载VBR和VPC后，不存在冲突路由。

    高速通道对等连接配置的静态路由优先于CEN的动态路由。即如果存在高速通道静态路由，不允许任何比该静态路由更明细或与该静态路由相同的CEN路由学习进来。此时建议您将高速通道路由进行拆分，在CEN完成路由学习后再删除拆分的路由，保证平稳迁移。

    以下图中的CEN路由192.168.1.0/24为例，该路由比指向高速通道的路由192.168.0.0/16更明细，所以出现了路由冲突。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630370/156145090849949_zh-CN.png)

    -   如果采用闪断迁移可以直接删除高速通道路由192.168.0.0/16，CEN路由自动生效。

        闪段时长和CEN路由条目数量成正比，对于重要的业务建议您使用平滑迁移方式。

    -   如果采用平滑迁移，需要按照比CEN路由192.168.1.0/24更明细的目标拆分，可以将高速通道路由192.168.0.0/16拆分为192.168.1.0/25和192.168.1.128/25两条明细路由。
        1.  在[高速通道控制台](https://expressconnectnext.console.aliyun.com/vbr/cn-hangzhou/detail/vbr-bp1qg7vzlr2kjeak81e28)VBR详情页面，单击**路由条目**进入VBR路由表页面。
        2.  单击**添加路由条目**分别添加两条目标网段为192.168.1.0/25和192.168.1.128/25，下一跳为专有网络的路由条目。

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630370/156145090849950_zh-CN.png)

        3.  如果是BGP路由，需要添加192.168.1.0/25和192.168.1.128/25相关的网段宣告。

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630370/156145090849951_zh-CN.png)

        4.  删除高速通道路由192.168.0.0/16。

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630370/156145090849952_zh-CN.png)

        5.  单击**刷新**查看CEN路由是否生效。

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/630370/156145090949953_zh-CN.png)

        6.  在VBR路由表中删除192.168.1.0/25和192.168.1.128/25两条明细路由，并删除宣告BGP路由。
        7.  在CEN控制台，为已迁移的VBR配置健康检查。配置详情，请参见[配置健康检查](../cn.zh-CN/用户指南/健康检查.md#section_hv3_qzn_tdb)。

