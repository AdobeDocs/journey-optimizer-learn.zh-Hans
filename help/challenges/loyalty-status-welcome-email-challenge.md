---
title: 创建忠诚度状态欢迎电子邮件 — 挑战
description: 了解在历程画布中构建历程的基础知识。
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 7a178b9c523ead0cf27aaa87d25b3752ef53f519
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 4%

---

# 创建忠诚度状态欢迎电子邮件 — 挑战

![忠诚度状态欢迎电子邮件 — 质询横幅](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 挑战 | 创建忠诚度状态欢迎电子邮件 |
|---|---|
| 角色 | 历程管理器 |
| 所需技能 | <ul><li>[创建区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html)</li> <li>[区段限定条件](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html)</li><li>[导入HTML内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html)</li></ul> |
| 要下载的资产 | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

## 故事

Luma提供忠诚计划，作为吸引和留住客户的一种方式。 该计划提供了四个不同的层：铜、银、金和铂。 每个忠诚度等级都会收到不同的奖励、折扣和其他特殊奖励，作为对其重复业务的奖励。

为特殊白金状态加下划线。 Luma希望在客户到达白金层时向客户发送欢迎电子邮件。

## 您的挑战

系统已要求您设置一个历程，当客户达到白金忠诚度等级时，该历程会自动向客户发送欢迎电子邮件。

>[!BEGINTABS]

>[!TAB 任务]

当忠诚客户符合白金级别时，他们应收到并发送电子邮件，祝贺并告知他们新的优势。 创意团队提供了HTML文件 **[Luma — 状态升级 — 欢迎电子邮件](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** 邮件正文。

1. 创建 [!UICONTROL 区段] 在Journey Optimizer `Luma – status upgrade`.
2. 创建名为 `Luma – New Status – platinum`.
   1. 客户在符合白金忠诚度等级资格时进入历程。
   2. 客户应收到一封标有 `Luma – Platinum Status - Welcome`，主题行 `Welcome to Platinum Status, (recipient's first name)!` 使用创意团队提供的电子邮件正文。 这是 [!UICONTROL 事务性] 电子邮件。
   3. 上传HTML文件时，您会注意到电子邮件引用的是“钻石”状态，而不是“白金”状态。 请在Email Designer中更新电子邮件，而不是向创意团队请求新文件。

>[!TAB 成功标准]

测试您的历程:

1. 确保 [!UICONTROL 读取区段活动] 具有 [!UICONTROL 命名空间] 设置为 **[!DNL Luma CRM id(lumaCrmId)]**
2. 覆盖默认 [!UICONTROL 电子邮件参数] 并将其设置为您自己的电子邮件地址
   * 通过单击眼睛符号显示隐藏值。
   * 在 [!UICONTROL 电子邮件参数]，单击T符号（启用参数覆盖）

       ![覆盖电子邮件参数](/help/challenges/assets/c3-override-email-paramters.jpg)
   
   * 单击 [!UICONTROL 地址字段]
   * 在下一个屏幕上，将您的电子邮件地址添加到括号中： `"yourname@yourdomain"` 在表达式编辑器中，单击确定。


3. 将历程设置为测试模式
4. 触发事件
5. 添加以下内容 [!DNL CRM ID] 表示 `Stanleigh Stooke` 到 [!UICONTROL 配置文件标识符] 字段： `4f34057d9d9e792c28ba18ecae378e98`

**结果：** 您应会收到个性化的 *Luma — 白金状态 — 欢迎* 电子邮件。

>[!TAB 检查您的工作]

您的历程应如下所示：

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)


电子邮件应如下所示：

![Luma — 状态升级 — 欢迎电子邮件](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
