# 对等连接

## 产品概述

对等连接：京东云物理云对等连接是指两个CPS VPC之间的网络连接。支持京东云CPS VPC之间互通、京东云CPS VPC和客户的CPS VPC两个VPC之间进行通信，就像两个CPS VPC在同一个网络中一样。<br/>
目前仅支持同地域资源网络环境互通（物理云对等连接又称“对等连接”。专用于云物理服务器使用）。

## 产品功能

1、对等连接互通不具有传递性：对等连接能使CPS VPC两两建立互联，但是这种互通关系不发生传递。<br/>

2、使用场景如下：<br/>
   ①同地域同账号：同一地域内，您可以在自己的CPS VPC之间创建对等连接；<br/>
   ②同地域跨账号：同一地域内，也可以在自己的CPS VPC与其他账号的CPS VPC之间创建对等连接；<br/>

## 使用限制

1、只有发起端才可以发起连接，接收端只能等待发起端发起连接。要使对等连接两端实现真正的通信，发起端和接收端的相关路由表上需配置指向对端的路由规则。<br/>
2、若对方不接受对等连接请求，申请将在 24小时后自动过期失效。<br/>
3、请勿接受未知账户的对等连接申请，此类用户可能会给您的网络带来风险。<br/>
4、对等连接的两端 VPC CIDR 不可以重叠，重叠时创建会报错。<br/>
5、同地域对等连接时，一个 VPC 的多个对等网络间 CIDR 不可重叠，重叠时会报错。<br/>
6、对等连接中的任意一方可以随时中断连接。中断后两个 VPC 间流量会立即中断。<br/>
7、每个京东云账户支持每个地域（region）最多申请50个对等连接，且同一个VPC下可支持创建5个NAT网关，如需更多配额请提交工单申请。<br/>
8、支持包年包月和按配置计费方式。<br/>
9、目前包年包月的资源不允许删除。<br/>

## 计费规则

对等连接支持包年包月和按配置两种计费方式。NAT网关包括4种规格：小型、中型、大型、超大型，根据不同的规格收取不同的费用。<br/>
包年包月：按照带宽配置预付费。按配置：按照带宽配置每小时出账单。<br/>
公测期间，NAT网关不同规格的实例，所有region免费。如绑定了弹性公网IP资源，仅需单独支付弹性公网IP费用，详见弹性公网IP[价格总览](../../Pricing/Price-Overview.md)。<br/>

- 小型（SNAT最大连接数5万，SNAT最大新建数无限制）<br/>
- 中型（SNAT最大连接数20万，SNAT最大新建数无限制）<br/>
- 大型（SNAT最大连接数50万，SNAT最大新建数无限制）<br/>
- 超大型（SNAT最大连接数100万，SNAT最大新建数无限制）<br/>

**包年包月计费**

包年包月为预付费方式，一次性支付一个月、多个月或多年的费用，适用于提前预估NAT网关需求的场景，价格相比按配置计费更低廉。

详细说明：
提前支付数月或数年的费用，目前购买时间段支持1个月~9个月、1年、2年、3年；费用在您创建资源时一次性扣除；示例：您在2017-8-2 10:00:00购买1个月小型的NAT网关，月单价为127.00元，则您需要支付的费用为127=127* 1元，您可以使用该资源至2017-9-2 23:59:59，公测期间NAT网关免费，无需支持费用。如绑定了弹性公网IP资源，需单独支付弹性公网IP费用。

包年包月的资源在到期前不支持执行删除操作，为了保障您的使用权益，请确认业务需求后进行购买。

包年包月计费订单的到期时间为订单开始时间当日起向后第N个自然月或自然年的 23:59:59； 例如：订单的开始时间为2016年1月1日 15:00:00，购买时长为1个月，则到期时间为2016年月2日1日 23:59:59。

**到期停服说明**

当您的包年包月NAT网关到期时间早于或等于当前时间，则您的资源状态会变为已到期。到期后付费网络资源将被停止服务，不能继续使用；

当您的包年包月NAT网关到期前，京东云会向您发送邮件、短信，提醒您的资源即将到期，请您注意查看并及时续费；

当您的NAT网关到期后立即停服，会向您发送邮件和短信通知您的资源到期停服，请您务必注意查看通知并及时充值，以免造成不必要的损失；

从停止服务时刻起，您的NAT网关保留7天，7天后系统回收资源，无法找回；控制台界面将只能执行续费操作；

您续费后被停用资源可正常使用。

**按配置计费**

开通要求：为保证您的正常使用，开通按配置计费的资源时您的账户余额及可用代金券之和不低于消费门槛50元。<br/>

**欠费停服说明**

NAT网关公测期间免费，本身不会欠费，但是用户账号可能因其他产品使用后欠费。<br/>

当您的NAT网关欠费后，可继续正常使用3小时，3小时后将欠费停止服务且停止扣费；控制台界面将只能执行删除操作；<br/>

当您的NAT网关欠费后，会向您发送邮件和短信，通知您的资源已欠费，请您务必注意查看通知并及时充值，以免造成不必要的损失；<br/>

从停止服务时刻起，您的NAT网关保留7天，7天后系统回收资源，无法找回；<br/>

当您补缴欠费金额后，被停用的NAT网关方可正常使用；<br/>

如您不想继续使用按配置的NAT网关，请及时将该资源进行删除。<br/>

## 价格总览

公测期间NAT网关免费使用。<br/>

## 创建NAT网关

打开控制台，在左侧导航栏依次点击云物理服务器->NAT网关，进入NAT网关页面，点击 **创建** ，进入创建页；<br/>

根据需求选择 **地域** ，可用区、规格类型（小型、中型、大型、超大型）、网络（私有网络、子网）、带宽（带宽计费模式（按固定带宽）、线路类型、带宽上限（1~200M）），购买时长，点击 **确定** ，即可创建1个NAT网关。<br/>

支持包年包月资源开通自动续费功能。勾选自动续费待资源创建后，自动续费属性和时长均修改。按月购买，则自动续费周期为1个月；按年购买，则自动续费周期为1年，按年自动续费享受自动续费折扣。<br/>

## 查看NAT网关

打开控制台，在左侧导航栏依次点击云物理服务器->NAT网关，进入NAT网关列表页，查看NAT网关信息；<br/>

或点击NAT网关 **名称/ID** ，跳转详情页，查看NAT网关详情信息。<br/>

## 绑定资源

打开控制台，在左侧导航栏依次点击云物理服务器->NAT网关，点击操作中的 **绑定弹性公网IP** 按钮，弹框选择所需绑定的弹性公网IP，选择即可完成绑定。<br/>

注意：NAT网关最多可绑定20个弹性公网IP。<br/>

## 解绑资源

打开控制台，在左侧导航栏依次点击云物理服务器->NAT网关->详情页弹性公网IP tab，点击操作中的 **解绑弹性公网IP** 按钮，选择即可完成解绑。<br/>

## 调整规格

打开控制台，在左侧导航栏依次点击云物理服务器->NAT网关，点击操作中的 **调整规格** 按钮，弹框选择需要调整的规格及带宽大小，即可完成操作。<br/>

注意：NAT网关支持升配和降配操作。<br/>

## 续费

打开控制台，在左侧导航栏点击NAT网关，进入NAT网关列表页，选择目标NAT网关，点击操作中的 **续费** 按钮，或进入详情页后点击操作中的 **续费** 按钮，选择需要续费的时长，点击 **确认** 按钮，跳转到支付确认页面，点击 **立即支付** ，即可完成操作。<br/>

注意：按配置计费的NAT网关进行续费操作后会转为包年包月资源。<br/>

## 删除

打开控制台，在左侧导航栏点击NAT网关，进入NAT网关列表页，选择目标NAT网关，点击操作中的 **删除** 按钮，或进入详情页后点击操作中的 **删除** 按钮，点击 **确认** 按钮，即可完成操作。<br/>

注意：包年包月计费的NAT网关不支持删除操作。<br/>
