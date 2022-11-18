---
title: 创建忠诚度状态欢迎电子邮件 — 挑战
description: 了解在历程画布中构建历程的基础知识。
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
source-git-commit: 957515149af1281d29a45b24ca499ef097656eb8
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 8%

---


# 创建忠诚度状态欢迎电子邮件 — 挑战

![AJO忠诚度状态欢迎电子邮件 — 挑战横幅](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 挑战 | 创建忠诚度状态欢迎电子邮件 |
|---|---|
| 角色 | 历程管理器 |
| 所需技能 | <ul><li>[使用消息编辑器创建电子邮件内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[使用上下文事件信息进行个性化](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[使用辅助函数进行个性化](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| 要下载的资产 | [订单确认资产](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## 故事

Luma提供忠诚计划，作为吸引和留住客户的一种方式。 该计划提供了四个不同的级别：银、金、铂和钻石。

每个忠诚等级会获得不同的级别或奖励、折扣和其他特殊奖励，作为对其重复业务的奖励。

为特殊钻石状态添加下划线。 Luma希望在客户到达钻石层级时向客户发送欢迎电子邮件。

## 您的挑战

您的任务是设置一个旅程，当客户达到钻石忠诚度等级时，该旅程会自动向客户发送欢迎电子邮件。

>[!NOTE]
> 如果您在共享的培训沙盒中工作，最佳做法是将您的名称或缩写作为预修复添加到您创建的任何元素的名称中。

### 创建Luma Diamond Status区段。

在Journey Optimizer中创建一个名为 **您的名称 — Luma — 钻石状态**.

### 创建Luma — 新建状态 — 钻石 — 事务型电子邮件消息

创建欢迎电子邮件消息

1. 创建标题为的事务型电子邮件 `(your name)_Luma – New Status – Diamond – Transactional email message`.
2. 为电子邮件提供一个主题行 `Welcome to Diamond Status, (recipient's first name)!`.
3. 使用提供的HTML文件 **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** 邮件正文。


### **历程#3 - Diamond状态升级欢迎电子邮件**

当忠诚客户转到新层级时，发送电子邮件，祝贺并告知他们的新好处。

1. 创建一个在客户进入Diamond新忠诚层（特别是当客户进入为新Diamond级别成员定义的区段时）时触发的历程，以发送“Luma - New Status - Diamond - Transactional”电子邮件
2. 完成后，将历程置于测试模式并触发历程以发送给您自己  

成功标准

您应会收到个性化的“Luma - New Status- Diamond-Transactional”电子邮件。
