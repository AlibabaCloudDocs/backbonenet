# DescribeCenVbrHealthCheck {#doc_api_Cbn_DescribeCenVbrHealthCheck .reference}

调用DescribeCenVbrHealthCheck查询指定地域内物理专线健康检查的状态。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=DescribeCenVbrHealthCheck&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|VbrInstanceRegionId|String|是|cn-hangzhou|VBR所在的地域。您可以通过调用[DescribeRegions](~~36063~~)接口查询地域ID。

 |
|Action|String|否|DescribeCenVbrHealthCheck|要执行的操作，取值：**DescribeCenVbrHealthCheckRequest**。

 |
|CenId|String|否|cen-kojok19x3j0q\*\*\*\*|云企业网实例的ID。

 |
|PageNumber|Integer|否|2|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|2|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|VbrInstanceId|String|否|vbr-wz95o9aylj181\*\*\*\*|VBR的ID。

 |
|VbrInstanceOwnerId|Long|否|123465253556777|VBR所属账户的UID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|2|当前页码。

 |
|PageSize|Integer|2|每页包含的条目数。

 |
|RequestId|String|A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A|请求ID。

 |
|TotalCount|Integer|2|列表条目数。

 |
|VbrHealthChecks| | |VBR健康检查。

 |
|CenId|String|cen-kojok19x3j0q6\*\*\*\*|云企业网实例ID。

 |
|Delay|Long|12|时延。

 |
|HealthCheckSourceIp|String|192.168.1.xx|健康检查的源IP地址。

 |
|HealthCheckTargetIp|String|192.168.1.xx|健康检查的目的IP地址。

 |
|LinkStatus|String|Active|用户配置的健康检查链路状态。

 |
|PacketLoss|Long|5|丢包率。

 |
|VbrInstanceId|String|vbr-il7ldy0ux6rb15l\*\*\*\*|VBR的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeCenVbrHealthCheck
&VbrInstanceRegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeCenVbrHealthCheckResponse>
      <HealthChecks>
            <HealthCheck>
                  <CenId>Cen-atlpf6evc5kqch****</CenId>
                  <VbrInstanceId>vbr-il7ldy0ux6rb15lc2s****</VbrInstanceId>
                  <HealthCheckSourceIp>10.10.10.xx</HealthCheckSourceIp>
                  <HealthCheckTargetIp>10.10.10.xx</HealthCheckTargetIp>
                  <Delay>3ms</Delay>
                  <Packetloss>5%</Packetloss>
            </HealthCheck>
      </HealthChecks>
      <PageNumber>1</PageNumber>
      <TotalCount>1</TotalCount>
      <PageSize>10</PageSize>
      <RequestId>A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A</RequestId>
</DescribeCenVbrHealthCheckResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DescribeCenVbrHealthCheckResponse":{
		"PageNumber":"1",
		"TotalCount":"1",
		"PageSize":"10",
		"RequestId":"A278B8A6-A5B8-4FDE-9F70-95F0F6A1D68A",
		"HealthChecks":{
			"HealthCheck":{
				"Delay":"3ms",
				"VbrInstanceId":"vbr-il7ldy0ux6rb15lc2s****",
				"Packetloss":"5%",
				"CenId":"Cen-atlpf6evc5kqch****",
				"HealthCheckSourceIp":"10.10.10.xx",
				"HealthCheckTargetIp":"10.10.10.xx"
			}
		}
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

