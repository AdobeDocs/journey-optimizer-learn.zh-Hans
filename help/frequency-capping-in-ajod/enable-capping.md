---
title: 为AJO营销活动启用频度上限
description: Adobe Journey Optimizer中的频率上限适用于单个选件级别，并且依赖于捕获选件展示和点击事件。 这需要使用Adobe Web SDK跟踪decisioning.propositionDisplay和decisioning.propositionInteract事件，并将它们映射到Adobe Experience Platform中更新的XDM Experience Event架构。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
exl-id: 34027499-0037-4ea1-813b-51be15eafe24
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
source-wordcount: '230'
ht-degree: 0%
---
# 为AJO营销活动启用频度上限

要对选件应用频率封顶，请完成以下步骤：

## 更新事件架构

* 通过添加如下所示的字段组更新现有事件架构
* ![event-schema](assets/schema.png)

## 更新优惠的频率封顶


* ![offer（产品建议）](assets/offer-capping.png)

## 将跟踪令牌添加到选件

通过添加后备优惠编辑营销活动中使用的决策策略
![回退](assets/fallback.png)

通过单击左侧导航中的“决策策略”图标，并向下展开决策树以选择itemID和trackingToken，可以添加trackingToken和ItemID。

将项目id和跟踪令牌添加到包含选件的div中，如下所示
![id-and-tracking-token](assets/id-and-tracking-token.png)

这可确保每个渲染的选件都包含数据跟踪令牌，这对于准确展示和点击事件跟踪至关重要。


激活修改后的营销活动。


## 发送展示和跟踪事件

修改现有的JavaScript代码，以使用Adobe Web SDK捕获优惠展示和交互事件并将这些事件发送到Adobe Experience Platform。 请参阅此处提供的[示例代码。](capture-impression-click-events.md)
