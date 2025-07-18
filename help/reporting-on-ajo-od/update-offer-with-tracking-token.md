---
title: 跟踪和报告Adobe Journey Optimizer (AJO)通过AJO Offer Decisioning提供的优惠
description: 本教程扩展了现有的Adobe Journey Optimizer (AJO)实施，该实施根据上下文数据（如温度）提供个性化优惠。 它概述了如何捕获展示和交互事件，并准备数据以在Journey Optimizer中报告。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18526
source-git-commit: fa4795d92cf290b867df23277a297c99d6222224
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# 将跟踪令牌添加到选件项目

要在个性化编辑器中修改代码，请执行以下步骤：

导航到&#x200B;_**历程管理 — >营销活动**_

打开相应的营销活动，然后单击&#x200B;_**停止营销活动**_&#x200B;按钮以停止该营销活动。

打开已停止的营销活动，然后单击&#x200B;_**修改营销活动**_&#x200B;按钮。

单击&#x200B;_**内容**_&#x200B;选项卡，然后单击&#x200B;_**编辑代码**_&#x200B;按钮以打开个性化编辑器。

将两个新数据属性添加到div，如屏幕快照中所示
![tracking-token](assets/offer-item-with-tracking-code.png)

通过单击左侧导航中的“决策策略”图标，并向下展开决策树以选择itemID和trackingToken，可以添加trackingToken和ItemID。
![tracking-token](assets/insert-tracking-token.png)

这可确保每个渲染的选件都包含数据跟踪令牌，这对于准确展示和点击事件跟踪至关重要。

保存更改并激活营销活动。
