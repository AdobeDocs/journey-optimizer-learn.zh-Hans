---
title: 创建Adobe Experience Platform标记
description: 根据用户投资偏好创建AJO受众（股票、债券、CD）
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 6823ce13-bc77-4e2b-89e0-606e403c15f2
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%
---
# 创建Adobe Experience Platform标签

在网页上配置Experience Platform标记以加载Adobe Experience Platform Web SDK，从而启用sendEvent API调用以触发个性化体验。 此设置可确保正确初始化必要的客户端库，从而允许与Adobe Journey Optimizer实时交互以提供选件。

1. 登录到数据收集。
1. 单击&#x200B;**[!UICONTROL 标记]** > **[!UICONTROL 新建属性]**。
1. 创建一个名为“ECID服务”的Adobe Experience Platform标记。
1. 将以下扩展添加到标记中：

   ![标记 — 扩展](assets/ecid-tag.png)

1. 配置Adobe Experience Platform Web SDK以使用正确的环境以及在上一教程中创建的Financial Advisors数据流

   ![web-sdk-configuration](assets/web-sdk-configuration.png)

Adobe客户端数据层和核心扩展无需额外配置

## 创建数据元素

Experience Platform标记中的ECID数据元素仅用于调试和测试目的。 数据元素允许开发人员查看分配给用户浏览器会话的Experience Cloud ID，这有助于验证身份拼接并确保`sendEvent`调用与正确的配置文件关联。 此元素不是个性化正常工作所必需的，但在实施和QA期间非常有用

![ecid](assets/ecid-data-element.png)


## 在HTML页面中包含AEP标记

构建和发布Adobe Experience Platform标记。

发布AEP Tags属性时，Adobe会为您提供一个必须放置在HTML `<head>`中或`<body>`标记底部的脚本标记。

1. 转到标记（ECID服务）资产。

1. 单击环境，然后单击所需环境的安装图标（例如，开发、暂存和生产）。

1. 记下嵌入的代码。

   此代码需要放置在HTML页面中的结束`</body>`标记之前。
