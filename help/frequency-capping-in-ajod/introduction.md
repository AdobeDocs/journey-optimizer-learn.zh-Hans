---
title: 对通过Adobe Journey Optimizer Decisioning交付的AJO (AJO)选件实施频率封顶
description: 本教程通过允许对使用Adobe Journey Optimizer Decisioning提供的选件设置频率上限，扩展了现有的AJO (AJO)实施。 它概述了如何捕获频率上限中使用的展示和交互事件。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# 对通过Adobe Journey Optimizer Decisioning交付的AJO (AJO)选件实施频率封顶

本教程将演示如何对Adobe Journey Optimizer中的选件应用频率封顶，以控制用户随时间查看同一选件的频率。

通过通过Adobe Web SDK捕获decisioning.propositionDisplay和decisioning.propositionInteract事件并将它们映射到Adobe Experience Platform (AEP)中的XDM架构，Adobe Journey Optimizer可以准确地跟踪优惠展示和交互，从而启用频率上限来限制向用户显示优惠的频率。

## 本教程的先决条件

在继续操作之前，请确保您拥有一个有效的Adobe Journey Optimizer营销活动，该活动使用Decisioning积极向Web表面提供选件。

本教程假定选件投放已在运行，并专门侧重于配置和验证频率上限行为。


