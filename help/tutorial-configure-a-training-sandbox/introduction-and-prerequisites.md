---
title: 配置培训沙盒 — 简介
description: 了解如何为培训目的配置沙盒。 执行配置架构、摄取示例数据和创建事件所需的步骤。
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
hide: true
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: 7ecbed1b722d7f05ffd4a7c7071358d993cb1392
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 9%

---

# 配置培训沙盒 — 简介和先决条件

![横幅教程 — 配置培训沙盒](./assets/ajo-banner-configure-training-sandbox.png)

本教程专为负责提供Adobe Journey Optimizer培训环境的管理员和数据工程师而设计。 了解配置模式、摄取示例数据和创建事件所需的步骤。 您还可以创建三个测试用户档案，让学习者检查其工作。

提供的示例数据基于一个虚构的运动服装公司，名为 _[!DNL Luma]_. [!DNL Luma] 在多个国家/地区拥有商店、在线提供网站和移动应用程序。 [!DNL Luma] 使用 Adobe Journey Optimizer 为客户提供互联、情境式和个性化的体验。

在本教程结束时，您有一个沙盒，它支持 [!DNL Luma] 在 [Journey Optimizer挑战](/help/challenges/introduction-and-prerequisites.md) 中。

## 先决条件

在开始设置培训沙盒之前，请确保您具有：

1. 专门开发 [沙盒](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).
1. [电子邮件消息预设](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=en) 为营销和事务型消息传递配置。
1. **[!UICONTROL 历程管理员]** 和 **[!UICONTROL Data Manager]** 培训沙盒的权限。
1. 您的 [组织ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=zh-Hans).
1. 包含示例数据的JSON文件，已配置为您的Journey Optimizer实例：
   1. 下载 `luma-sample-data.zip` 文件 [此处](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip)，其中包含本教程所需的所有JSON文件。
   1. 从下载文件夹中，移动 `luma-data.zip` 文件到计算机上的所需位置，然后将其解压缩。 这些文件包含培训沙盒的示例数据。
   1. 打开每个文件并查找 **`yourOrganizationID`** 用 [组织ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=zh-Hans).
   1. 保存文件。

## 我们开始吧

从 [手动数据设置](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md).

在此步骤中，您定义了所需的数据结构。 完成数据设置后，您可以将数据摄取到沙盒中，然后设置事件。
