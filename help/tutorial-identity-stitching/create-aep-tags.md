---
title: 将CRMID发送到Adobe Experience Platform
description: 创建Adobe Experience Platform标记以将从浏览器收到的CRMID发送到Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 894ad6b7-c4b4-465e-8535-3fdcd77e00eb
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 9%
---
# 将CRMID发送到Adobe Experience Platform

Adobe Experience Platform Tags用于将CRMID发送到Adobe Experience Platform (AEP)，因为它为直接从浏览器传输身份数据提供了灵活的事件驱动机制。 在用户登录后发送CRMID可让AEP将匿名ECID与已知CRM配置文件关联，从而实现准确的身份拼接。 这种关联构成了在Adobe Journey Optimizer (AJO)中构建统一客户档案、确定受众资格和提供实时个性化体验的基础。

已创建名为&#x200B;_**FinWise**_&#x200B;的Experience Platform Tags属性。 已将以下扩展添加到Tags属性

![标记 — 扩展](assets/tags-extensions.png)

使用在上一步创建的Financial Advisors DataStream配置AEP Web SDK扩展。
Experience Cloud ID服务是一个为调试目的添加到标记属性的可选扩展。

## 标记数据元素

创建以下数据元素

| 数据元素 | 扩展 | 数据元素类型 | 自定义设置 |
|--------------|-----------------------------------|---------------------------|----------------------------------------|
| crmid | Adobe客户端数据层 | 数据层计算状态 | user.crmid |
| ECID | Experience Cloud ID 服务 | ECID |                                        |
| 身份标识 | Adobe Experience Platform Web SDK | 标识映射 | ![图像](assets/identity-settings.png) |
| XDMVariable | Adobe Experience Platform Web SDK | Variable | ![图像](assets/xdmvariable.png) |

## 创建规则

使用以下事件和操作创建一个名为LoginEvent的规则

活动
![事件](assets/data-pushed-event1.png)

更新变量操作
![更新变量](assets/update-variable1.png)
发送事件操作
![发送事件](assets/send-event1.png)

## 保存并构建

保存更改，创建并构建库。
