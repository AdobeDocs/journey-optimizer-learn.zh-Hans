---
title: Web push in AJO
description: This tutorial demonstrates how to implement web push notifications using Adobe Journey Optimizer (AJO). 您将了解如何通过Web SDK捕获用户选择加入、通过计划的营销活动发送通知，以及通过AEP Tags使用自定义price.drop事件触发实时推送消息。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Adobe Journey Optimizer中的Web推送

Web推送通知是一种让用户实时重新参与的强大方法，本教程将指导您使用Adobe Journey Optimizer (AJO)实施这些通知。 首先，您可以使用Web SDK捕获推送通知的用户选择加入偏好设置，从而确保无缝且合规的订阅体验。 接下来，您将创建一个营销活动，向已选择加入的用户发送推送通知，从而实现基于受众的参与。 最后，您将了解如何利用AEP Tags触发自定义降价事件，该事件会在AJO中启动历程，并根据实时用户行为提供及时、个性化的推送通知。

允许用户选择加入通知的示例网页

![启用通知](assets/enable-notifications.png)

用于触发价格下降事件的示例网页

![trigger price drop](assets/trigger-price-drop-event.png)

## 先决条件

This tutorial is designed to be hands-on and easy to follow. While no deep expertise is required, a basic familiarity with the following concepts will be helpful:

- Adobe Journey Optimizer（创建历程或营销活动）
- AEP数据收集（标记）和Web SDK
- 架构和事件等基本Adobe Experience Platform概念
- 一些JavaScript和一般Web开发概念
- 基本Node.js知识（用于生成VAPID密钥并提供简单的配置端点）

如果您是这些区域的新手，请不要担心，本教程将指导您完成过程中的关键步骤。
本教程重点介绍如何实施端到端Web推送通知用例，因此，了解上述工具和概念的工作知识将有助于您有效地遵循这些工具和概念。


## 🔔启用浏览器通知

If notifications are blocked or not appearing, you may need to enable them in your browser settings. Refer to the guides below:

- **Google Chrome (Windows/macOS)**\
  <https://support.google.com/chrome/answer/3220216>

- **Microsoft Edge (Windows)**\
  <https://support.microsoft.com/en-us/microsoft-edge/manage-website-notifications-in-microsoft-edge>

- **Safari (macOS)**\
  <https://support.apple.com/guide/safari/customize-website-notifications-sfri40734/mac>

- **Safari (iPhone/iPad)**\
  <https://support.apple.com/en-us/HT213893>


## 示例应用程序


为了帮助您完成这些工作，提供了一个完整的示例应用程序。

- [实时演示 — 选择加入：](https://ajo-web-push.onrender.com/)

- [触发价格下降事件：](https://ajo-web-push.onrender.com/price-drop-trigger.html)

- [Source代码：](https://github.com/gbedekar489/ajo-web-push)

您可以浏览实时演示以查看操作流程，或克隆存储库以本地运行项目。

