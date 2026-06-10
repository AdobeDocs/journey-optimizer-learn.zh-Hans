---
title: 创建推送渠道
description: 推送渠道配置定义如何发送Web推送通知，包括应用程序设置和平台特定的详细信息。 它还将您的推送设置链接到所需的凭据，如VAPID密钥，从而使AJO可以向订阅的用户发送通知。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-20879
exl-id: 0a8be7eb-9962-466a-9fcc-022cb84c7b0a
source-git-commit: 108686aa75358f940b5d7d83e7f04bf55f72978f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# 创建推送渠道

第一步是在Adobe Journey Optimizer中创建推送渠道。 在此设置过程中，您需要生成VAPID密钥，验证和启用Web推送通知需要这些密钥。 然后，这些密钥将在推送渠道配置中使用，从而允许AJO安全地向订阅的用户发送通知。

## 生成VAPID密钥

VAPID（自愿应用程序服务器识别）是一种Web推送标准，允许您的服务器识别自己的身份以推送服务（如Chrome、Edge等） 使用公钥/私钥对，以便推送提供商知道谁在发送通知。

它使用web-push generate-vapid-keys之类的工具生成，该工具会创建公共密钥（与浏览器共享）和私钥（保存在服务器上），共同用于验证和安全发送推送消息。

在本教程中，我们已使用Node.js生成VAPID密钥。

确保已安装Node.js。 然后发出以下命令

`npm install web-push -g `

![Web推送](assets/install-web-push.png)

`web-push generate-vapid-keys`

![vapid](assets/vapid-keys.png)

## 创建推送凭据

* 登录Journey Optimizer

* 导航到管理 |渠道 |推送设置 |推送凭据|创建推送凭据

* ![推送凭据](assets/push-credential.png)

## 创建渠道配置

* 登录Journey Optimizer

* 导航到管理 |渠道 |创建渠道配置
  ![渠道配置](assets/push-channel.png)
