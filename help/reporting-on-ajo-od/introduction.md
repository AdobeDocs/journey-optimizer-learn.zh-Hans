---
title: 跟踪和报告通过Adobe Journey Optimizer Offer Decisioning提供的AJO (AJO)选件
description: 本教程扩展了现有的Adobe Journey Optimizer (AJO)实施，该实施根据上下文数据（如温度）提供个性化优惠。 它概述了如何捕获展示和交互事件，并准备数据以供在Journey Optimizer中报告。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
source-git-commit: 23832f2e59ca7558fd403f0a9753db3923023e6d
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# 跟踪和报告通过Adobe Journey Optimizer Offer Decisioning提供的AJO (AJO)选件

此用例侧重于为通过Adobe Journey Optimizer (AJO)提供的选件启用报表和性能分析。 当根据上下文信号（例如天气或位置）提供个性化优惠时，必须跟踪展示次数和用户交互以评估其有效性。

通过通过Adobe Web SDK捕获decisioning.propositionDisplay和decisioning.propositionInteract事件并将它们映射到Adobe Experience Platform (AEP)中的结构化XDM架构，即可获得选件级别的参与数据，以进行分析。 然后，此数据可用于Customer Journey Analytics (CJA)构建功能板，衡量点进率(CTR)等关键量度，并比较不同受众区段和上下文条件之间的选件表现。

目标是提供清晰、数据驱动的见解，了解个性化优惠的效果如何，并为未来决策策略提供信息。




![reporting-dashboard](assets/dashboard-reporting.png)



## 本教程的先决条件

在开始之前，请先完成[使用实时天气数据个性化选件教程。](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction)它建立了所有基础组件，包括：

- Web SDK集成

- Adobe Journey Optimizer (AJO)中的选件设置

- 使用天气和温度等上下文属性进行决策

- 网页上的实时优惠呈现

本教程直接基于该实施构建，并专门侧重于捕获选件展示次数和交互，以便在Journey Optimizer中进行报表和分析。

