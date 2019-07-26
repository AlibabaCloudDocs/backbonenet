# EnableCenVbrHealthCheck {#doc_api_Cbn_EnableCenVbrHealthCheck .reference}

调用EnableCenVbrHealthCheck开启边界路由器（VBR）的健康检查，确保及时发现出现故障的物理专线。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=EnableCenVbrHealthCheck&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-hahhfskfkseig\*\*\*\*|云企业网实例的ID。

 |
|HealthCheckSourceIp|String|是|192.168.1.xx|健康检查的源IP地址。

 |
|HealthCheckTargetIp|String|是|10.0.0.xx|健康检查的目的IP地址。

 |
|VbrInstanceId|String|是|vbr-wz95o9aylj181n5mzk\*\*\*\*|VBR的ID。

 |
|VbrInstanceRegionId|String|是|cn-shenzhen|VBR所在的地域。您可以通过调用[DescribeRegions](~~36063~~)接口查询地域ID。

 |
|Action|String|否|EnableCenVbrHealthCheck|要执行的操作，取值：**EnableCenVbrHealthCheck**。

 |
|VbrInstanceOwnerId|Long|否|1233233323445689999|VBR所属账户的UID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=EnableCenVbrHealthCheck
&CenId=cen-hahhfskfkseig****
&HealthCheckSourceIp=192.168.1.xx
&HealthCheckTargetIp=10.0.0.xx
&VbrInstanceId=vbr-wz95o9aylj181n5mzk****
&VbrInstanceRegionId=cn-shenzhen
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<EnableCenVbrHealthCheckResponse>
      <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
      <CenId>Cen-atlpf6evc5kqch****</CenId>
      <VbrId>vbr-il7ldy0ux6rb15lc2****</VbrId>
      <RegionId>cn-hangzhou</RegionId>
      <SourceIp>10.10.10.xx</SourceIp>
      <TargetIp>10.10.10.xx</TargetIp>
      <PacketNum>3</PacketNum>
      <Status>Enable </Status>
</EnableCenVbrHealthCheckResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Status":"Enable",
	"PacketNum":"3",
	"RegionId":"cn-hangzhou",
	"RequestId":"A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A",
	"TargetIp":"10.10.10.xx",
	"CenId":"Cen-atlpf6evc5kqchp****",
	"VbrId":"vbr-il7ldy0ux6rb15lc2****",
	"SourceIp":"10.10.10.xx"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|RouteConflict|The specified route already exists.|输入的路由已存在。|
|400|Illegal.SourceIpOrTargetIp|The specified source IP address or destination IP address is invalid.|源IP或者目的IP非法|

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

