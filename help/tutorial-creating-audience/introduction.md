---
title: 创建受众
description: 根据用户投资偏好创建AJO受众（股票、债券、CD）
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---


# 根据用户投资偏好创建AJO受众（股票、债券、CD）

在本教程中，您将了解如何通过Web表单捕获用户偏好设置，实时将该数据发送到Adobe Experience Platform (AEP)，以及根据用户的选择动态地授予目标受众资格。 通过将Adobe Tags (Launch)、AEP Web SDK (Alloy.js)和Edge Segmentation整合在一起，您可以为对股票、债券或存款证(CD)感兴趣的客户带来立竿见影的个性化机会。

## 本教程的先决条件

* 对Adobe Experience Platform的访问权限

* 基本了解Adobe Experience Platform概念（用户档案、受众、数据集）

* 熟悉Adobe Tags (Launch) — 设置数据元素和规则

* JavaScript基础知识（阅读和编写简单的函数）

* 能够使用浏览器DevTools（“控制台”和“网络”选项卡）


## 目标

本教程的目标是在Adobe Experience Platform (AEP)中构建并限定三个不同的受众：

* 对股票感兴趣的客户

* 对债券感兴趣的客户

* 对CD感兴趣的客户

用户将通过Web表单提交其偏好设置，这些偏好设置将使用Adobe Launch通过AEP Web SDK摄取，从而实现实时受众资格。

## 使用的工具

* Adobe Experience Platform (AEP)

* Adobe Experience Platform标记

* AEP Web SDK (Alloy.js)

* AEP Edge分段

* 带有偏好设置表单的网页





