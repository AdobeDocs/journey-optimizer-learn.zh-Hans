---
title: 创建排名公式
description: Adobe Journey Optimizer中的排名公式在Offer Decisioning过程中使用，尤其是在选择策略中，用于确定符合条件的优惠的优先级顺序。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18188
exl-id: eee1b86e-b33f-408e-9faf-90317bc5e861
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
source-wordcount: '346'
ht-degree: 0%
---
# 创建排名公式

Adobe Journey Optimizer中的排名公式在Offer Decisioning过程中使用，尤其是在选择策略中，用于确定符合条件的优惠的优先级顺序。 资格筛选后，当多个选件符合给定用户档案的条件，但根据业务逻辑或用户档案上下文，只能呈现前一个（或少数个）时，排名公式就会起作用。

* 登录到Journey Optimizer

* 决策 — >策略设置 — >排名公式 — >创建公式

排名公式
![name_description](assets/formuala-ranking.png)

排名公式中的标准是指用于将分数分配给优惠的条件规则。 这些标准将比较选件和用户档案或上下文中的属性，以确定选件与特定个人的相关性。



标准1

此条件筛选决策项（优惠）**以仅包含**标记为“IncomeLevel”的优惠。
然后，这些过滤的选件将根据您定义的其他逻辑继续执行下一步，例如排名或投放。
![criteria_one](assets/income-related-formula.png)


以下表达式用于创建排名得分

```pql
if(   offer._techmarketingdemos.offerDetails.zipCode = _techmarketingdemos.zipCode,   _techmarketingdemos.annualIncome / 1000 + 10000,   if(     not offer._techmarketingdemos.offerDetails.zipCode,     _techmarketingdemos.annualIncome / 1000,     -9999   ) )
```

公式的作用

* 如果选件与用户具有相同的邮政编码，则将其分值设置为非常高，以便最先选择它。

* 如果选件根本没有邮政编码（它属于常规选件），请根据用户的收入为其提供正常分数。

* 如果选件的邮政编码与用户不同，请将其分值设得很低，这样就不会选中该选件。

这样，系统就可以：

* 始终首先尝试显示邮政编码匹配选件，

* 如果未找到匹配项，则回退到常规选件，并避免显示专用于其他邮政编码的选件。


如果选件项目不满足任何筛选条件（例如不具有“IncomeLevel”标记），则选件将获得默认排名得分10。




