---
title: 使用AJO Decisioning（基于受众）个性化网页选件
description: 了解如何使用Adobe Journey Optimizer (AJO) Decisioning通过利用Adobe Experience Platform (AEP)中构建的受众分段在网页上提供个性化优惠。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
source-git-commit: 5ab637d9b9955ab334ee67ed887e34026b04206d
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 1%

---

# 使用AJO Decisioning（基于受众）个性化网页选件

本教程以之前使用Adobe Experience Platform (AEP) Web SDK创建的受众分段设置为基础。 在上一个教程中，捕获了用户偏好设置(如股票、债券或存款证(CD)中的利息)，并将其用于在Adobe Experience Platform (AEP)中将个人细分为目标受众。 本教程在此基础上再接再厉，使用Adobe Journey Optimizer (AJO) Decisioning实时为这些受众提供个性化的金融优惠，从而提高参与度和转化结果。

您可以使用以下链接实时测试个性化AJO优惠。
[单击此处查看实时演示](https://gbedekar489.github.io/finwise/welcome.html) — 该页面将根据您的投资偏好显示实时优惠。

## 本教程的先决条件

* 对Adobe Experience Platform的访问权限

* 基本了解Adobe Experience Platform概念（用户档案、受众、数据集）

* 熟悉Adobe Journey Optimizer

* JavaScript基础知识（阅读和编写简单的函数）

* 能够使用浏览器DevTools（“控制台”和“网络”选项卡）


## 目标

本教程将指导您在使用Adobe Journey Optimizer (AJO)的网站上提供个性化的投资选件，例如股票、债券或CD。 利用受众分段和决策策略，您可以了解如何确保每位访客都能根据其偏好看到最相关的选件。

## 使用的工具

* Adobe Experience Platform (AEP)
* Adobe Journey Optimizer (AJO)
* Adobe Experience Platform标记
* AEP Web SDK (Alloy.js)
* AEP Edge分段
* 显示优惠的网页
