---
title: 创建决策策略
description: 决策策略定义用于确定在个性化过程中将哪些选件交付给用户的逻辑。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 186e4a7d-6077-401f-9958-2f955214bc35
source-git-commit: 6bf0c2487afff4811aa94e9591ae29c38af15d34
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# 创建决策策略

决策策略是优惠的容器，它们利用决策引擎根据受众选择要投放的最佳内容。

在个性化编辑器中，单击左侧导航中的决策策略项目，然后单击添加决策策略

![create-decision-policy](assets/decision-policy.png)

单击添加以选择选择策略
单击选择回退以选择回退选件。
单击下一步以查看决策策略，然后单击创建以完成创建决策策略的过程。


![决策策略](assets/decision-policy2.png)


## 在代码编辑器中使用决策策略

在个性化编辑器中，单击插入策略。此时将添加与决策策略对应的代码。

在此阶段，您可以直接在代码中包含任何所需的决策属性。 这些属性在选件目录使用的架构中定义。 标准属性在__experience命名空间下组织，而特定于您的组织的任何自定义属性则存储在`_<imsOrg>`命名空间下。

![using_decision_polcy](assets/Insert-policy.png)

此代码会浏览为用户选择的个性化优惠列表，并在网页上显示每个优惠的文本。 该可视化图表在段落中显示来自每个选件的消息（称为offerText），以便用户清楚地看到其定制的内容。
如果没有可用的个性化优惠，则会显示一个后备优惠，以确保空间不会留空。

单击保存，然后单击激活营销活动。
