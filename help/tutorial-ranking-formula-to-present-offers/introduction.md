---
title: 根据邮政编码和收入使用排名公式实现产品建议个性化
description: 使用 Adobe Journey Optimizer 的排序公式，基于每位用户的邮政编码和收入水平动态投放最相关的金融产品建议，实现更高参与度与更智能的个性化体验。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-27T00:00:00.000Z
jira: KT-18188
exl-id: 11685f7c-8048-4318-9c28-71bd7da8f7ff
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
source-wordcount: '338'
ht-degree: 16%
---
# 使用基于用户邮政编码和收入的排名公式个性化优惠

此用例演示了如何利用Adobe Journey Optimizer中的用户属性（如邮政编码和年收入）来提供个性化的财务优惠。 通过使用排名公式，可以根据特定于位置的促销活动以及基于收入的资格，对优惠进行智能评分和优先排序。 例如，高收益CD可以推广给富裕邮政编码的用户，而新兴投资者可以有多样化的投资选择。 排名公式可确保每个用户都收到相关且经济上适当的选件。 排名标准是使用用户档案属性、上下文信号和可选AI模型来定义的，以进一步提高决策精度。 选件通过Web或电子邮件渠道实时交付，从而提高参与度和转化率。 此方法将业务逻辑与数据驱动的个性化相结合，可提高用户体验和营销影响。

## 先决条件

本教程以Adobe Journey Optimizer和Adobe Experience Platform的关键概念为基础。 在继续之前，请确保满足以下先决条件：

* [身份拼接教程](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorial-on-identity-stitching-in-aep/introduction)已完成，CRM ID已成功与Adobe Experience Platform中的ECID关联。

* 熟悉如何在AJO中创建选件项目，包括内容定义、元数据设置和资格规则。

* 熟悉如何为选件交付配置渠道（如Web或电子邮件）。

* 熟悉如何在AJO中创建和激活营销活动。

* 熟悉如何使用Adobe Launch （标记）来部署Web SDK，并发送包含身份和配置文件数据的事件。

本教程涵盖Offer Decisioning中的后续步骤：

* 使用个人资料属性（如邮政编码和年收入）创建排名方法。

* 定义选择策略以对优惠进行分组和优先级排序。

* 构建决策策略以向每个人提供最相关的优惠。
