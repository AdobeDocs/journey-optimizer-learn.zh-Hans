---
title: 使用Web SDK在Adobe Journey Optimizer中使用实时天气数据个性化优惠
description: 本教程演示如何使用实时上下文数据和Adobe Web SDK Personalization API在Adobe Journey Optimizer中提供动态的天气感知选件。 您将了解如何将网站中的天气属性（如温度和条件）传递到Adobe Experience Platform，将它们映射到事件架构，并在决策规则和排名公式中使用这些属性，以便在页面加载时个性化优惠。 非常适合希望通过实时环境上下文增强数字体验的营销人员和开发人员。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18258
source-git-commit: d46c5a922b8448f57b8a730188284294c3caba96
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# 用例描述

通过在Adobe Journey Optimizer (AJO)中使用与天气相关的数据来提供选件，企业可以根据实时的真实环境条件来对客户体验进行个性化设置。 天气是一个强大的情境信号。 人们的需求和行为会因天气而改变。 通过使用天气数据：

    提供符合客户心情和环境的相关优惠。
    
    在炎热的天气下，显示冷饮料或空调设备的选件。 下雨天促销夹克或雨伞

![天气优惠](assets/offers-use-case.png)