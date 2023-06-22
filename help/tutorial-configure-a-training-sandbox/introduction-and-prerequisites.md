---
title: 配置培训沙盒 – 简介
description: 了解如何为培训目的配置沙盒。完成配置架构、摄取样本数据和创建事件所需的步骤。
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: 81f5cc22d46f89ee1c7164a92988311ca6036b8b
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# 配置培训沙盒 – 简介和先决条件

![横幅教程 – 配置培训沙盒](./assets/ajo-banner-configure-training-sandbox.png)

本教程专为负责提供 Adobe [!DNL Journey Optimizer] 培训环境的管理员和数据工程师而设计。了解配置架构、摄取样本数据和创建事件所需的步骤。您还可以创建三个测试个人资料，以便学习者检查其工作。

提供的样本数据基于一家虚构的运动服装公司，名为 _[!DNL Luma]_。[!DNL Luma] 在多个国家/地区设有商店、在线展示网站以及移动应用程序。[!DNL Luma] 使用 Adobe Journey Optimizer 为客户提供互联、情境式和个性化的体验。

在本教程结束时，您将获得一个沙盒，支持 [Journey Optimizer 挑战](/help/challenges/introduction-and-prerequisites.md)部分中的实践练习所涉及的 [!DNL Luma] 用例。

## 先决条件

在开始设置培训沙盒之前，请确保您具有：

1. 一个专门的开发[沙盒](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=zh-Hans)。

1. 针对营销和事务型消息传递配置的[电子邮件预设](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=zh-Hans)。

1. 培训沙盒的&#x200B;**[!UICONTROL 历程管理员]**&#x200B;和&#x200B;**[!UICONTROL 数据管理员]**&#x200B;权限。

1. 您的[组织 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=zh-Hans)。

1. 包含样本数据的 JSON 文件，已配置到您的 Journey Optimizer 实例：

   1. 点击[此处](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip)下载 `luma-sample-data.zip` 文件，其中包含本教程所需的所有 JSON 文件。

   1. 从下载文件夹中，将 `luma-data.zip` 文件移动到计算机上的所需位置，然后将其解压缩。

      这些文件包含培训沙盒的样本数据。

   1. 打开每个文件，找到 **`yourOrganizationID`**，然后将其替换为您的 [组织 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=zh-Hans)。

   1. 保存文件。

## 让我们开始吧！

从[手动数据设置](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md)开始。

在此步骤中，您将定义所需的数据结构。完成数据设置后，您可以将数据摄取到沙盒中，然后设置事件。
