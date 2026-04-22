---
title: 创建受众
description: 在Adobe Experience Platform中定义一个区段，以定向符合接收推送通知条件的用户。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 3%

---

# 创建受众

要为营销活动创建受众，请在Adobe Experience Platform中定义一个区段，以定向有资格接收推送通知的用户。 在本教程中，用户具有活动的推送订阅（存在推送令牌），尚未选择退出通知（阻止列表标志为false），并且与指定的应用程序配置相关联（应用程序标识符等于`my-first-push`）。 这些用户完全有资格通过Adobe Journey Optimizer中的营销活动或历程接收Web推送通知。创建受众后，请确保对其进行评估，以便填充用户档案并准备好定位。
然后，该受众在营销活动中用于仅向订阅的用户投放计划的Web推送消息。

![创建受众](assets/push-audience.png)

