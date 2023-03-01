---
title: 创建忠诚度状态欢迎电子邮件 - 挑战
description: 了解在历程画布中构建历程的基础知识。
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: e9553da0fd85ee6e48d3089a93d51a994635de81
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 65%

---

# 创建忠诚度状态欢迎电子邮件 - 挑战

![忠诚度状态欢迎电子邮件 - 挑战横幅](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 挑战 | 创建忠诚度状态欢迎电子邮件 |
|---|---|
| 角色 | 历程管理者 |
| 所需技能 | <ul><li>[创建区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=zh-Hans)</li> <li>[区段鉴别](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=zh-Hans)</li><li>[导入 HTML 内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=zh-Hans)</li></ul> |
| 可供下载的资源 | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style=&quot;table-layout:auto&quot;}

## 案例

Luma 提供忠诚度计划，作为吸引和留住客户的一种方式。该计划提供了四个不同的等级：青铜、白银、黄金和白金。 每个忠诚度等级都会获得不同的奖励、折扣和其他特殊激励，作为对其重复业务的奖励。

为了强调特殊的白金等级，Luma希望在客户达到白金等级时向客户发送欢迎电子邮件。

## 您的挑战

该公司要求您设置一个历程，当客户达到白金忠诚度等级时，该历程会自动向客户发送欢迎电子邮件。

>[!BEGINTABS]

>[!TAB 任务]

当忠诚客户符合白金级别的条件时，他们应收到一封电子邮件，祝贺他们并告知可享受的新福利。 创意团队提供了HTML文件 **[Luma — 状态升级 — 欢迎电子邮件](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** 使用电子邮件正文。

1. 在 Journey Optimizer 中创建称为 `Luma - platinum status` 的[!UICONTROL 区段]。

1. 创建称为 `Luma - New Status - platinum` 的历程。

   1. 当客户符合白金忠诚度等级条件时，即会进入历程。

   1. 客户应收到一封电子邮件，标有 `Luma - Platinum Status - Welcome`，主题行为 `Welcome to Platinum Status, {firstName}!`，且使用创意团队提供的电子邮件正文。这是 [!UICONTROL 事务性] 电子邮件。

   1. 上传 HTML 文件时，您会注意到电子邮件引用的是“钻石”状态，而不是“白金”状态。 请在[!UICONTROL 电子邮件设计工具]中更新电子邮件，而不是向创意团队请求新文件。

>[!TAB 成功标准]

测试您的历程：

1. 确保 [!UICONTROL 读取区段活动] 具有 [!UICONTROL 命名空间] 设置为 **[!DNL Luma CRM id(lumaCrmId)]**.

1. 覆盖默认[!UICONTROL 电子邮件参数]并将其设置为您自己的电子邮件地址:
   * 在 **[!UICONTROL 电子邮件参数]**，单击T符号（启用参数覆盖）

   * 单击 **[!UICONTROL 地址]** 字段。

   * 在下一个屏幕中，将您的电子邮件地址添加到括号中： `"yourname@yourdomain"` 在表达式编辑器中，然后单击 **[!UICONTROL 确定]**.

1. 将历程设置为测试模式.

1. 选择&#x200B;**[!UICONTROL 触发事件]**.

1. 添加以下内容 `CRM ID` 对象 `Stanleigh Stooke` 在 **[!UICONTROL 配置文件标识符]** 字段： `4f34057d9d9e792c28ba18ecae378e98`

**结果：** 您应会收到个性化的 *Luma — 白金状态 — 欢迎* 电子邮件。

电子邮件应如下所示：

![Luma — 状态升级 — 欢迎电子邮件](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB 检查您的工作]

区段应如下所示：

![Luma - 白金状态 - 区段](/help/challenges/assets/segment-luma-platinum-status.png)

您的历程应如下所示：

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
