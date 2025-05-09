---
title: 使用Web SDK创建受众
description: 在本教程中，您将了解如何通过Web表单捕获用户偏好设置，实时将该数据发送到Adobe Experience Platform (AEP)，以及根据用户的选择动态地授予目标受众资格。 通过将Adobe Tags (Launch)、AEP Web SDK (Alloy.js)和Edge Segmentation整合在一起，您能够为对股票、债券或存款证(CD)感兴趣的客户带来即时的个性化机会。
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
exl-id: ebaa3aa5-0a08-43fd-8d06-8e4b5d8dee05
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# 使用Web SDK创建受众

在本教程中，您将了解如何通过Web表单捕获用户偏好设置，实时将该数据发送到Adobe Experience Platform (AEP)，以及根据用户的选择动态地授予目标受众资格。 通过将Adobe Tags (Launch)、AEP Web SDK (Alloy.js)和Edge Segmentation整合在一起，您能够为对股票、债券或存款证(CD)感兴趣的客户带来即时的个性化机会。

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

用户通过Web表单提交其偏好设置，这些偏好设置通过AEP Web SDK使用Adobe Launch摄取，从而实现实时受众资格。

## 使用的工具

* Adobe Experience Platform (AEP)

* Adobe Experience Platform标记

* AEP Web SDK (Alloy.js)

* AEP Edge分段

* 带有偏好设置表单的网页
