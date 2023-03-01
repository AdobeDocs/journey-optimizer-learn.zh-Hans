---
title: 配置培训沙盒 — 简介
description: 了解如何为培训目的配置沙盒。 完成配置架构、摄取示例数据和创建事件所需的步骤。
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
hide: true
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: 2a671ad01f1cdb60c731a707b0584bf2f4262d9b
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 9%

---

# 配置培训沙盒 — 简介和先决条件

![横幅教程 — 配置培训沙盒](./assets/ajo-banner-configure-training-sandbox.png)

本教程专为负责提供Adobe的管理员和数据工程师设计 [!DNL Journey Optimizer] 训练环境。 了解配置架构、摄取示例数据和创建事件所需的步骤。 您还可以创建三个测试用户档案，以允许学习者检查其工作。

提供的示例数据基于一家名为的虚构的运动服装公司 _[!DNL Luma]_. [!DNL Luma] 在多个国家/地区开店、在线开设网站和移动应用程序。 [!DNL Luma] 使用 Adobe Journey Optimizer 为客户提供互联、情境式和个性化的体验。

在本教程的结尾，您有一个沙盒支持 [!DNL Luma] 的动手练习中涵盖的用例 [Journey Optimizer挑战](/help/challenges/introduction-and-prerequisites.md) 部分。

## 先决条件

在开始设置培训沙盒之前，请确保您具有：

1. 一个专门的开发 [沙盒](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).

1. [电子邮件预设](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=en) 针对营销和事务型消息传递进行了配置。

1. **[!UICONTROL 历程管理员]** 和 **[!UICONTROL 数据管理器]** 培训沙盒的权限。

1. 您的 [组织ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=zh-Hans).

1. 包含示例数据的JSON文件，已配置为您的Journey Optimizer实例：

   1. 下载 `luma-sample-data.zip` 文件 [此处](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip)，其中包含本教程所需的所有JSON文件。

   1. 从您的下载文件夹中，移动 `luma-data.zip` 文件到计算机上的所需位置，然后解压缩。

      这些文件包含培训沙盒的示例数据。

   1. 打开每个文件并查找 **`yourOrganizationID`** 并将其替换为 [组织ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=zh-Hans).

   1. 保存文件。

## 让我们开始吧

开始于 [手动数据设置](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md).

在此步骤中，您将定义所需的数据结构。 完成数据设置后，您可以将数据摄取到沙盒中，然后设置事件。
