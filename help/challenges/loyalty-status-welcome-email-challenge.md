---
title: 创建忠诚度状态欢迎电子邮件 — 挑战
description: 了解在历程画布中构建历程的基础知识。
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: e148101f8404c8e2019ee17823bcf1d7a9668bc5
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 4%

---

# 创建忠诚度状态欢迎电子邮件 — 挑战

![AJO忠诚度状态欢迎电子邮件 — 挑战横幅](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 挑战 | 创建忠诚度状态欢迎电子邮件 |
|---|---|
| 角色 | 历程管理器 |
| 所需技能 | <ul><li>[创建区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html)</li> <li>[区段限定条件](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html)</li><li>[导入HTML内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html)</li></ul> |
| 要下载的资产 | [platinumStatusEmail.zip](/help/challenges/assets/email-assets/platinumStatusEmail.zip) |

## 故事

Luma提供忠诚计划，作为吸引和留住客户的一种方式。 该计划提供了四个不同的级别：铜、银、金和铂。 每个忠诚等级会获得不同的级别或奖励、折扣和其他特殊奖励，作为对其重复业务的奖励。

为特殊白金状态加下划线。 Luma希望在客户到达白金层时向客户发送欢迎电子邮件。

## 您的挑战

系统已要求您设置一个历程，当客户达到白金忠诚度等级时，该历程会自动向客户发送欢迎电子邮件。

>[!BEGINTABS]

>[!TAB 任务]

当忠诚客户符合白金级别时，他们应收到并发送电子邮件，祝贺并告知他们新的优势。 创意团队提供了HTML文件 **[Luma — 状态升级 — 欢迎电子邮件](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** 邮件正文。

1. 在Journey Optimizer中创建一个名为 `Luma – status upgrade`.
2. 创建一个名为“Luma - New Status - platinum”的历程。
   1. 客户在符合白金忠诚度等级资格时进入历程。
   2. 客户应收到一封标有 `Luma – Platinum Status - Welcome`，主题行 `Welcome to Platinum Status, (recipient's first name)!` 由创意团队提供的身体。
   3. 上传HTML文件时，您会注意到电子邮件引用的是“钻石”状态，而不是“白金”状态。 请在电子邮件设计工具中更新电子邮件，而不是向创意团队请求新文件。

>[小费！]
> 确保Luma - Platinum Status - Welcome eMail是事务型电子邮件。


>[!TAB 成功标准]

测试您的历程:

1. 确保读取区段活动的命名空间设置为 **Luma CRM id(lumaCrmId)**
2. 覆盖默认的电子邮件参数，并将其设置为您自己的电子邮件地址

+++ 单击此处以了解有关如何覆盖的详细信息
   * 通过单击眼睛符号显示隐藏值。
   * 在Email参数中，单击T符号（启用参数覆盖）

   ![覆盖电子邮件参数](/help/challenges/assets/c3-override-email-paramters.jpg)

   * 单击Address字段
   * 在下一个屏幕上，将您的电子邮件地址添加到括号中： `"yourname@yourdomain"` 在表达式编辑器中，单击确定。
+++


3. 将历程设置为测试模式
4. 触发事件
5. 将以下Stanleigh Stooke的CRM ID添加到用户档案标识符字段： `4f34057d9d9e792c28ba18ecae378e98`

您应会收到个性化的 *Luma — 白金状态 — 欢迎* 电子邮件。

>[!TAB 检查您的工作]

您的历程应如下所示：

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)


电子邮件应如下所示：

![Luma — 状态升级 — 欢迎电子邮件](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
