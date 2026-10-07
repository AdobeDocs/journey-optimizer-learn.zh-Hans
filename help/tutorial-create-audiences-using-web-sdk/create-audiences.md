---
title: 在Adobe Journey Optimizer中创建受众
description: 了解如何在AJO中定义和构建目标受众，以支持个性化的客户历程和实时决策
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
jira: KT-17923
exl-id: d90f1868-0514-49b2-832d-82460883b6e4
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%
---
# 在Adobe Journey Optimizer中创建受众


Adobe Experience Platform中的受众是指根据用户的操作、偏好或配置文件信息创建的用户组，用于提供个性化体验。

* 登录到Journey Optimizer
* 导航到客户 — >受众 — >创建受众
* 使用构建规则方法创建受众

  ![audience（受众）](assets/rule-based-audience.png)

* 创建以下3个受众

  * 对股票感兴趣的客户

  * 对债券感兴趣的客户

  * 对CD感兴趣的客户


* 确保将每个受众的评估方法设置为&#x200B;_**Edge**_以进行实时资格鉴定。
  ![边缘受众](assets/audience-edge.png)

* 使用PreferredFinancialInstrument字段根据用户选择的投资利息（如股票、债券或CD）划分用户

![事件](assets/event-attribute.png)

![首选金融工具](assets/stock-customers.png)




>[!NOTE]
>
>>如果PreferredFinancialInstrument字段在events选项卡中不可见，请单击设置图标并切换显示完整XDM架构。



![toggle-full-xdm-schema](assets/show-custom-fields.png)
