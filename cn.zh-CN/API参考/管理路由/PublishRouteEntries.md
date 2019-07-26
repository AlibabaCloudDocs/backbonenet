# PublishRouteEntries {#doc_api_Cbn_PublishRouteEntries .reference}

调用PublishRouteEntries将加载到CEN中的VPC或VBR的路由条目发布到CEN中。

## 可发布的路由条目 {#description .section}

下表列举了可以发布到CEN的路由条目：

|路由条目

|路由条目所属实例

|是否默认发布到CEN

|
|------|----------|------------|
|指向ECS实例的路由条目

|VPC

|否

|
|指向VPN网关的路由条目

|VPC

|否

|
|指向高可用虚拟IP的路由条目

|VPC

|否

|
|VPC系统路由

|VPC

|是

|
|指向IDC的路由条目

|VPC

|是

|
|BGP路由

|VPC

|是

|

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cbn&api=PublishRouteEntries&type=RPC&version=2017-09-12)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CenId|String|是|cen-7qthudw0ll6jmc\*\*\*\*|云企业网的ID。

 |
|ChildInstanceId|String|是|vpc-rj9gt5nll27onu\*\*\*\*|加载的网络实例ID（VPC或VBR的ID）。

 |
|ChildInstanceRegionId|String|是|us-west-1|加载的网络实例的地域ID。

 |
|ChildInstanceRouteTableId|String|是|vtb-bp174d1gje7\*\*\*\*|网络实例的路由表ID。

 |
|ChildInstanceType|String|是|VPC|网络实例类型，取值： **VPC|VBR**。

 |
|DestinationCidrBlock|String|是|172.16.xx.xx/24|要发布的网段。

 |
|Action|String|否|PublishRouteEntries|要执行的操作，取值：**PublishRouteEntries**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|FBDB18D8-E91E-4978-8D6C-6E2E3EE10133|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=PublishRouteEntries
&CenId=cen-7qthudw0ll6jmc****
&ChildInstanceId=vpc-rj9gt5nll27onu****
&ChildInstanceRegionId=us-west-1
&ChildInstanceRouteTableId=vtb-bp174d1gje7****
&ChildInstanceType=VPC
&DestinationCidrBlock=172.16.xx.xx/24
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<PublishRouteEntriesResponse>
      <RequestId>FBDB18D8-E91E-4978-8D6C-6E2E3EE101330</RequestId>
</PublishRouteEntriesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"FBDB18D8-E91E-4978-8D6C-6E2E3EE10133"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|ParameterIllegal.AliUid|The parameter of aliUid is illegal.|UID信息不正确|
|400|ParameterIllegal.CenInstanceId|The parameter of CEN instance id is illegal.|云企业网ID不正确|
|400|ParameterIllegal.ChildInstanceRegionId|The parameter of child instance region id is illegal.|网络实例所属地域信息不正确。|
|409|InvalidOperation.ChildInstanceStatus|The child-instance is not in a valid state for the operation.|网络子实例正在处理状态，请稍后再操作|
|409|InvalidOperation.CenInstanceStatus|The CEN instance is not in a valid state for the operation.|CEN实例正在处理状态，请稍后再操作|
|400|ParameterIllegal.ChildInstanceType|The parameter of child instance type is illegal.|网络子实例类型不正确|

访问[错误中心](https://error-center.aliyun.com/status/product/Cbn)查看更多错误码。

