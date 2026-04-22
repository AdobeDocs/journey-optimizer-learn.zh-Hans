---
title: 捕获用户权限
description: 创建网页以捕获用户接收推送通知的同意。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# 捕获用户权限

此网页捕获用户接收推送通知的同意。 它会提示用户使用浏览器的通知API启用通知，并在接受通知后，使用Web SDK向Adobe Experience Platform注册推送订阅。 这可确保只有选择加入的用户才有资格通过Adobe Journey Optimizer中的营销活动和历程接收推送通知。

为了启用Web推送通知，页面首先通过在初始化函数中调用fetch(&quot;/config&quot;)来加载配置文件。 此配置由Node.js应用程序提供，包括数据流ID、组织ID、VAPID公钥、应用程序ID和跟踪数据集ID等键值。 加载配置后，将初始化Adobe Web SDK，并注册Service Worker以支持推送消息。 当用户单击启用通知时，浏览器会提示他们使用Web通知API获取权限。 如果授予权限，Web SDK会将推送订阅发送到Adobe Experience Platform，并且用户在24小时内标记为已选择加入，以避免重复提示。 启动服务器后，您可以在[示例应用程序](http://localhost:3000/)中包含的本地网页shop-smart.html上尝试此流程。

![请求权限](assets/request-notifications.png)

