---
title: 创建数据流
description: 本页将指导您在Adobe Experience Platform中创建数据流，这是从Web SDK收集数据并将其路由到AEP和Adobe Journey Optimizer所必需的。 数据流充当您的Web应用程序与Adobe服务之间的连接，以便处理推送订阅和事件数据。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# 创建数据流

Adobe Experience Platform (AEP)中的数据流充当接收从Web SDK发送的数据的端点。 它将此数据路由到配置的服务，如AEP、Adobe Analytics或Adobe Journey Optimizer。 在本教程中，数据流用于将Web推送订阅数据和price.drop事件发送到AEP以进行激活。

## 创建用于跟踪推送通知的事件架构

创建名为`SchemaForPushNotification`的新XDM ExperienceEvent架构。 将`Push Notification Tracking`和`Commerce Details`字段组添加到此架构。 Commerce详细信息字段组中的字段将用于捕获产品信息并触发自定义price.drop事件。

![event-schema](assets/event-schema.png)

## 创建配置文件架构以保存用户同意

在本教程中，我们使用现成的`AJO Push Profile Schema`。 此架构存储用户的推送订阅详细信息，包括发送Web推送通知所需的推送令牌。

![profile_schema](assets/profile-schema.png)

## 为架构创建数据集

使用之前创建的事件架构创建名为`DataSetForPushNotification`的数据集。 对于配置文件数据，请使用与推送配置文件架构关联的现成`AJO Push Profile Dataset`。 记下`DataSetForPushNotification` ID，因为稍后在教程中通过.env文件配置应用程序时，需要记下该ID。

## 使用事件和用户档案数据集创建数据流

使用上一步中创建的事件和配置文件数据集创建名为WebPushDataStream的新数据流。 记下数据流ID，因为稍后在教程中通过.env文件配置应用程序时，需要记下该ID。

![数据流](assets/datastream.png)
