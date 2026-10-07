---
title: 创建受众
description: 在Adobe Experience Platform中定义一个区段，以定向符合接收推送通知条件的用户。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: 427bb35a-d607-48be-845d-9587c4cad86b
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 3%
---
# 创建受众

要为营销活动创建受众，请在Adobe Experience Platform中定义一个区段，以定向有资格接收推送通知的用户。 在本教程中，用户具有活动的推送订阅（存在推送令牌），尚未选择退出通知（阻止列表标志为false），并且与指定的应用程序配置相关联（应用程序标识符等于`my-first-push`）。 这些用户完全有资格通过Adobe Journey Optimizer中的营销活动或历程接收Web推送通知。创建受众后，请确保对其进行评估，以便填充用户档案并准备好定位。
然后，该受众在营销活动中用于仅向订阅的用户投放计划的Web推送消息。

![创建受众](assets/push-audience.png)
