---
title: 捕获与Adobe Web SDK的优惠交互以进行AI模型训练
description: 本文主要介绍如何使用Adobe Experience Platform Web SDK (alloy.js)捕获用户交互数据，例如优惠展示次数和点击次数。 此数据用作在Adobe Journey Optimizer (AJO)中训练AI模型的基础，以便根据用户行为和上下文信号对选件进行智能排名。
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
source-git-commit: dfb280df3453e7811dffd95b9af664b873a9af31
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---


# 捕获与Adobe Web SDK的优惠交互以进行AI模型训练

本文演示了如何通过在Adobe Experience Platform Web SDK代码中直接调用alloy(“sendEvent”， ...)来使用JavaScript捕获优惠交互事件（如展示次数或单击次数）。 数据将被摄取到AEP中，并用于在Adobe Journey Optimizer (AJO)中训练AI模型，以便根据实时行为对更智能的优惠进行排名。

## 先决条件

在开始之前，请确保已具备以下条件：

- 安装了Adobe Web SDK扩展且正在使用的Adobe Experience Platform Launch资产。

- 已配置一个[数据流](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset)并将其映射到您的AEP沙盒。

- 部署Launch的网站。


## 为优惠交互事件创建架构和数据集

要收集体验事件，您首先需要创建一个将发送这些事件的数据集。

按照此[文章中提到的步骤创建所需的架构和数据集](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset)

## 在AEP中创建数据流

![数据流](assets/ai-model-data-stream.png)
将Adobe Experience Platform服务添加到数据流
![数据流服务](assets/data-stream-service.png)

## 使用Web SDK配置Adobe Experience Platform标记

在扩展设置中：

配置Adobe Experience Platform Web SDK扩展以使用创建的数据流
