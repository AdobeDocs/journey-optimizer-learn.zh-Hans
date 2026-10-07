---
title: 对通过Adobe Journey Optimizer Decisioning交付的AJO (AJO)选件实施频率封顶
description: 本教程通过允许对使用Adobe Journey Optimizer Decisioning提供的选件设置频率上限，扩展了现有的AJO (AJO)实施。 它概述了如何捕获频率上限中使用的展示和交互事件。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 7%
---
# 对通过Adobe Journey Optimizer Decisioning交付的AJO (AJO)选件实施频率封顶

本教程将演示如何对Adobe Journey Optimizer中的选件应用频率封顶，以控制用户随时间查看同一选件的频率。

本教程假定您已通过遵循有关根据天气条件个性化优惠的[教程](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction)来设置AJO营销活动

通过通过Adobe Web SDK捕获decisioning.propositionDisplay和decisioning.propositionInteract事件并将它们映射到Adobe Experience Platform (AEP)中的XDM架构，Adobe Journey Optimizer可以准确地跟踪优惠展示和交互，从而启用频率上限来限制向用户显示优惠的频率。

## 本教程的先决条件

在继续操作之前，请确保您拥有一个有效的Adobe Journey Optimizer营销活动，该活动使用Decisioning积极向Web表面提供选件。

本教程假定选件投放已在运行，并专门侧重于配置和验证频率上限行为。




