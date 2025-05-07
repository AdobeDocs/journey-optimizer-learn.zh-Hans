---
title: 创建Adobe Experience Platform标记
description: 根据用户投资偏好创建AJO受众（股票、债券、CD）
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17923
source-git-commit: 9695a4db0d0caa44a8c7d49e069320309ffc40a6
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---


# 创建Adobe Experience Platform

Adobe Launch在网页上配置为加载Adobe Experience Platform Web SDK，从而启用sendEvent API调用以触发个性化体验。 此设置可确保正确初始化必要的客户端库，从而允许与Adobe Journey Optimizer实时交互以提供选件。

* 登录到数据收集
* 单击“标记” — >“新建属性”
* 创建一个名为“ECID服务”的Adobe Experience Platform标记。

* 将以下扩展添加到标记
  ![标记 — 扩展](assets/ecid-tag.png)

* 确保将Adobe Experience Platform Web SDK配置为使用正确的环境和上一个教程中创建的Financial Advisors数据流
  ![web-sdk-configuration](assets/web-sdk-configuration.png)

* Adobe客户端数据层和核心扩展无需额外配置

## 创建数据元素

Adobe Launch中的ECID数据元素仅用于调试和测试目的。 它允许开发人员查看分配给用户浏览器会话的Experience Cloud ID，这有助于验证身份拼接并确保sendEvent调用与正确的配置文件关联。 此元素不是个性化正常工作所必需的，但在实施和QA期间非常有用

![ecid](assets/ecid-data-element.png)


## 在HTML页面中包含AEP标记

构建和发布Adobe Experience Platform标记

发布AEP Tags属性时，Adobe会为您提供一个必须放置在HTML ``` <head>```中或``` <body>```标记底部的脚本标记。

* 转到Tags（ECID服务）资产。

* 单击环境，然后单击所需环境的安装图标（例如，开发、暂存和生产）。

* 记下嵌入的代码。 此代码需要置于HTML页面中结束```</body>```标记的前面。

