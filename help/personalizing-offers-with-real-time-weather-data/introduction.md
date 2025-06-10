---
title: 使用Web SDK在Adobe Journey Optimizer中使用实时天气数据个性化优惠
description: 本教程演示如何使用实时上下文数据和Adobe Web SDK Personalization API在Adobe Journey Optimizer中提供动态的天气感知选件。 您将了解如何将网站中的天气属性（如温度和条件）传递到Adobe Experience Platform，将它们映射到事件架构，并在决策规则和排名公式中使用这些属性，以便在页面加载时个性化优惠。 非常适合希望通过实时环境上下文增强数字体验的营销人员和开发人员。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18258
source-git-commit: c04a15418e31dc82597b7759386907013728bb0d
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# 用例描述

通过在Adobe Journey Optimizer (AJO)中使用与天气相关的数据来提供选件，企业可以根据实时的真实环境条件来对客户体验进行个性化设置。 天气是一个强大的情境信号。 人们的需求和行为会因天气而改变。 通过使用天气数据：

提供符合客户心情和环境的相关优惠

炎热的天气下，可以购买冷饮料或空调设备。 下雨天促销夹克或雨伞

基于天气的选件示例


![天气优惠](assets/offers-use-case.png)



## 本教程的先决条件

* 对Experience Platform的访问权限

* 对Adobe Experience Platform标记的基本了解

* 基本了解Experience Platform概念（用户档案、受众、数据集）

* 熟悉Journey Optimizer

* JavaScript基础知识（阅读和编写简单的函数）

* 能够使用浏览器DevTools（“控制台”和“网络”选项卡）
