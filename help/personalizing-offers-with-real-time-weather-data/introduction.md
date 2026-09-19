---
title: 使用 Web SDK 在 Adobe Journey Optimizer 中通过实时天气数据对产品建议进行个性化设置
description: 本教程展示如何在 Adobe Journey Optimizer 中结合使用实时上下文数据和 Adobe Web SDK Personalization API，投放动态的、具备天气感知能力的个性化产品建议。 您将了解如何将网站中的天气属性（如温度和条件）传递到 Adobe Experience Platform，如何将它们映射到事件架构，并在决策规则和排名公式中使用这些属性，以便在页面加载时提供个性化产品建议。 非常适合希望通过实时环境上下文增强数字体验的营销人员和开发人员。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10
jira: KT-18258
exl-id: f40dd541-470c-4f42-8181-eb1c277ebaa3
source-git-commit: b4cf9b677c6bc142e1013649db16b3a70b405052
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 42%
---
# 用例描述

通过在Adobe Journey Optimizer (AJO)中使用与天气相关的数据来提供选件，企业可以根据实时的真实环境条件来对客户体验进行个性化设置。 天气是一个强大的情境信号。 人们的需求和行为会因天气而改变。 通过使用天气数据：

提供符合客户心情和环境的相关优惠

炎热的天气下，可以购买冷饮料或空调设备。 下雨天促销夹克或雨伞的

基于天气的选件示例


![天气优惠](assets/offers-use-case.png)



## 本教程的先决条件

* 访问Experience Platform。

* 对Adobe Experience Platform标记的基本了解。

* 基本了解Experience Platform概念（用户档案、受众、数据集）。

* 熟悉Journey Optimizer。

* JavaScript基础知识（读写简单函数）。

* 能够使用浏览器DevTools（“控制台”和“网络”选项卡）。
