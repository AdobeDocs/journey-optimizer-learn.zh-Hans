---
title: 捕获与Adobe Web SDK的优惠交互以进行AI模型训练
description: 本文提供了有关如何使用Adobe Experience Platform Web SDK (alloy.js)捕获用户交互数据（例如优惠展示次数和点击次数）的指导。 此数据用作在Adobe Journey Optimizer (AJO)中智能训练AI模型的基础，以根据用户行为和上下文信号对选件进行排名。
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
source-git-commit: 41f0d44fb39c9d187ee8c97d54202387fa9eda56
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 0%

---


# 捕获与Adobe Web SDK的优惠交互以进行AI模型训练

>[!NOTE]
>
> 仅当您计划在Adobe Journey Optimizer中使用基于人工智能的排名方法来根据预测参与度个性化显示哪个选件时，才应完成本文。



本文演示了如何通过直接在Adobe Experience Platform Web SDK代码中调用alloy(“sendEvent”……)来使用JavaScript捕获优惠交互事件（如展示次数或单击次数）。 数据被摄取到AEP中，并用于在Adobe Journey Optimizer (AJO)中训练AI模型，以根据实时行为对选件进行更智能的排名。

要在Adobe Journey Optimizer中创建优惠排名的AI模型，您的数据集必须基于包含建议交互字段组的架构。 此字段组支持关键决策事件（如decisioning.propositionDisplay和decisioning.propositionInteract）以及必需字段（如incomdedPropositions、display和interact）。

实现此目标的有效方法有两种：

- 创建专门为交互跟踪配置的新架构、数据集和数据流
- 更新现有架构 — 本教程将这样做



## 更新现有架构以捕获优惠交互事件

更新了用于天气相关优惠的现有Experience Event架构，以支持交互跟踪，而不是创建新架构。

在Adobe Experience Platform中：

- 打开您用于基于天气的选件的现有&#x200B;_&#x200B;**天气架构**&#x200B;_&#x200B;体验事件架构。

- 添加字段组：
体验事件 — 建议交互

您无需创建新数据集或数据流 — 继续使用现有设置进行天气选件。 发送的事件符合Adobe Journey Optimizer对训练AI模型和跟踪选件性能的期望。


继续使用当前数据集（无需创建新数据集）

现有数据流已配置并在Adobe Experience Platform Tags属性中使用 — 无需进行更改。

Web SDK会自动将新的交互事件路由到正确的目标。

这种简化的设置可确保将所有决策和天气事件摄取到单个统一的数据集中，该数据集非常适合于在Adobe Journey Optimizer中训练AI模型。


## 捕获优惠显示事件（展示次数）

优惠的HTML结构已修改为包含交互式元素（尤其是`<a>`和`<button>`标记），允许用户参与优惠（例如，“报销申请优惠”或“了解更多”按钮）。

每个按钮都包含一个data-offer-id属性，以便可以正确跟踪相应的交互。



要记录何时向用户显示选件，已更新用于呈现天气选件的现有JavaScript文件，以包含显示事件跟踪。

现在，当显示一个或多个选件时，将使用Adobe Web SDK (alloy.sendEvent)发送decisioning.propositionDisplay事件。 此事件包括必需的显示： 1个标志并引用相关建议。


```javascript
if (offerIds.length > 0) {
  alloy("sendEvent", {
    xdm: {
      _id: generateUUID(),
      timestamp: new Date().toISOString(),
      eventType: "decisioning.propositionDisplay",
      _experience: {
        decisioning: {
          propositionEvent: {
            display: 1
          },
          involvedPropositions: offerIds.map(id => ({
            id,
            scope: "web://gbedekar489.github.io/weather/weather-offers.html#offerContainer"
          }))
        }
      }
    }
  });
}
```

## 捕获优惠点击事件（交互）

为了跟踪用户何时单击选件，我们更新了现有的JavaScript以侦听对选件容器中呈现的`<a>`和`<button>`元素的点击。

检测到点击时，将使用Adobe Web SDK发送decisioning.propositionInteract事件。 该事件包括必要的交互：1个标志并引用特定优惠ID和决策范围。

```javascript
// Attach click tracking to <a> and <button> elements
wrapper.querySelectorAll("a, button").forEach(el => {
  el.addEventListener("click", () => {
    const offerId = el.getAttribute("data-offer-id") || item.id;
    console.log("Clicked element offerId:", offerId);

    alloy("sendEvent", {
      xdm: {
        _id: generateUUID(),
        timestamp: new Date().toISOString(),
        eventType: "decisioning.propositionInteract",
        _experience: {
          decisioning: {
            propositionEvent: {
              interact: 1
            },
            involvedPropositions: [{
              id: offerId,
              scope: "web://gbedekar489.github.io/weather/weather-offers.html#offerContainer"
            }]
          }
        }
      }
    });
  });
});
```

## 在Adobe Journey Optimizer Offer Decisioning中创建选件排名的AI模型

通过现已通过Web SDK捕获并存储在Adobe Experience Platform中的优惠展示次数和点击次数，此数据可用于训练一个AI模型，该模型可预测哪些优惠最有可能促进参与。

排名公式或选择策略中引用此AI模型，以确定为每个用户优先提供哪些选件。
- 登录到Journey Optimizer
- 导航到“决策” — >“策略设置” — >“AI模型” — >“创建AI模型”
- 确保使用正确的数据集
  ![ai-model](assets/ai-model.png)
- 保存并激活AI模型。
- 更新在之前步骤中创建的选择策略，以将AI模型用于Ranking方法
  ![update-selection-strategy](assets/update-selection-strategy.png)

## 测试解决方案

将[更新的JavaScript文件](assets/ai-model.js)包含在[现有网页](assets/weather-offers.html)中