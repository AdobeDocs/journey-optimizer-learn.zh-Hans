---
title: 捕获展示和交互事件
description: 捕获展示和交互事件，并准备数据以在Journey Optimizer中报告。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
recommendations: noDisplay, noCatalog
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
exl-id: 7e6014b5-c5a6-467b-8e31-58c5d966464c
source-git-commit: bfeab1e933f2a510506c0ecf911df41e66cb959b
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# 捕获展示和交互事件

要启用AJO Decisioning中的选件展示次数和点击次数报表，必须配置以下组件：
>[!NOTE]
>
> [上一教程](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/create-schema-and-dataset)的创建架构和数据集部分中已完成这些先决条件

## &#x200B;1. Adobe Experience Platform (AEP)中的数据集

- 基于&#x200B;**XDM ExperienceEvent**&#x200B;架构的数据集。

架构必须包括`Web Details`字段组，用于捕获页面URL、反向链接等。

## 2.数据流配置

- 必须在Adobe Experience Platform中创建&#x200B;**数据流**。
- 此数据流必须链接到上面配置的数据集，以确保所有Web SDK事件都被正确摄取到正确的目标中。

## &#x200B;3. Adobe Experience Platform Tags资产

- AEP Web SDK扩展已配置为使用在上一步中创建的数据流。
- Experience Cloud ID服务已配置
- 名称为ECID的数据元素将添加到属性中
- 在呈现优惠的网站上实施。


要启用选件性能报表，第一步是捕获选件何时显示（展示次数）以及何时单击它们（交互）。 这些活动为衡量参与、计算点进率以及分析Adobe Experience Platform中的选件有效性奠定了基础。

alloy(“sendEvent”)函数用于记录用户与Adobe Journey Optimizer (AJO)返回的选件的交互。

sendEvent有效负载通过包含事件类型（用于展示次数的decisioning.propositionDisplay或用于点击的decisioning.propositionInteract）、唯一事件ID、时间戳和用户身份(identityMap)来捕获优惠交互。 它还包含已显示或已单击的优惠（建议）列表，以及跟踪令牌以确保准确归因。 此结构支持在Adobe Journey Optimizer中报告和优化个性化优惠表现。

捕获两种类型的交互事件：

## 展示事件

展示会在选件呈现在页面上并对用户可见时发生。 使用decisioning.propositionDisplay事件类型跟踪该事件。


```javascript
 alloy("sendEvent", {
            xdm: {
              _id: generateUUID(),
              timestamp: new Date().toISOString(),
              eventType: "decisioning.propositionDisplay",
              identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "authenticated",
                      primary: true
                    }]
                  },
              _experience: {
                decisioning: {
                  propositionEventType: {
                    display: 1
                  },
                    propositionAction: {
                            id: offerId,
                            tokens: [trackingToken]
                  },
                  
                   propositions: window.latestPropositions
                  
                }
              }
            }
          });
        }
```

## 优惠互动

当用户单击呈现的选件中的call-to-action (CTA)时，将记录交互。 使用decisioning.propositionInteract事件类型跟踪事件。

```javascript
alloy("sendEvent", {
                xdm: {
                  _id: generateUUID(),
                  timestamp: new Date().toISOString(),
                  eventType: "decisioning.propositionInteract",
                  identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "ambiguous",
                      primary: true
                    }]
                  },
                  _experience: {
                    decisioning: {
                      propositionEventType: {
                        interact: 1
                      },
                      propositionAction: {
                        id: offerId,
                        tokens: [trackingToken]
                      },
                       propositions: window.latestPropositions
                    }
                  }
                }
              })
```

在点击和展示事件中包含建议对于Adobe Journey Optimizer中的准确选件报表至关重要。 这些建议表示提供给用户的确切优惠，允许Adobe将用户交互（例如，展示次数或点击次数）归因于系统做出的特定决策。

建议中的每个选件都包含一个跟踪令牌，该令牌是Adobe生成的唯一标识符。 此令牌必须在相应的点击或展示事件中完全按照收到的样式传递（不会发生更改）。 匹配跟踪令牌可确保Adobe能够准确地将用户操作与正确的优惠决策相关联，从而实现下游报表和基于人工智能的优化。
