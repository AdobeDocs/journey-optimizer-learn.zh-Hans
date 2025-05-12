---
title: 在Adobe Journey Optimizer中创建受众
description: 了解如何在AJO中定义和构建目标受众，以支持个性化的客户历程和实时决策
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: ba83be3caf214d2daaa8c99556d246686ff3f0cb
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# 在Adobe Journey Optimizer中创建受众


Adobe Experience Platform中的受众是指根据用户的操作、偏好或配置文件信息创建的用户组，用于提供个性化体验。

* 登录到Journey Optimizer
* 导航到客户 — >受众 — >创建受众
* 使用构建规则方法创建受众

  ![受众](assets/rule-based-audience.png)

* 创建以下3个受众

   * 对股票感兴趣的客户

   * 对债券感兴趣的客户

   * 对CD感兴趣的客户


* 确保将每个受众的评估方法设置为&#x200B;_&#x200B;**Edge**&#x200B;_以进行实时资格鉴定。
  ![边缘受众](assets/audience-edge.png)

* 使用PreferredFinancialInstrument字段根据用户选择的投资利息（如股票、债券或CD）划分用户

![事件](assets/event-attribute.png)

![首选金融工具](assets/stock-customers.png)




>[!NOTE]
>
>&#x200B;>如果PreferredFinancialInstrument字段在events选项卡中不可见，请单击设置图标并切换显示完整XDM架构。



![toggle-full-xdm-schema](assets/show-custom-fields.png)


