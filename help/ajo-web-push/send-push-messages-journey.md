---
title: 在历程中发送推送消息
description: Adobe Journey Optimizer中的频率上限适用于单个选件级别，并且依赖于捕获选件展示和点击事件。 这需要使用Adobe Web SDK跟踪decisioning.propositionDisplay和decisioning.propositionInteract事件，并将它们映射到Adobe Experience Platform中更新的XDM Experience Event架构。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# 在历程中发送推送消息

根据价格下降事件触发历程支持与用户进行实时、行为导向的参与。 在现实场景中，此事件通常源自更新产品价格时的后端定价系统。 在本教程中，我们使用AEP标记通过Adobe数据层发送自定义price.drop事件来模拟该行为，包括产品详细信息，如名称和SKU。 此事件被摄取到Adobe Experience Platform中，并用作在Adobe Journey Optimizer中历程的进入触发器。 历程在收到消息后，可以立即向符合条件的用户发送个性化推送通知，告知他们价格下降情况并鼓励及时采取行动。

使用自定义事件触发历程涉及以下步骤

## 在Journey Optimizer中创建自定义事件

登录Adobe Journey Optimizer并导航到“管理” → “配置”→“事件” ，然后选择“创建事件” 。 创建一个名为PriceDropEvent的新事件，并将其与本教程前面创建的事件架构SchemaForPushNotification关联。 请确保事件属性已配置，如参考图像中所示。

![event-properties](assets/price-drop-event.png)

从架构中，选择所需的字段以使其可用于个性化。 具体而言，包括ProductListItems对象中的`Name`和`SKU`，以及identityMap中的标识符。 随后，可在个性化编辑器中访问这些字段，允许您根据产品和用户上下文动态撰写推送通知消息。

## 创建标记属性

此属性使用AEP Web SDK进行配置，该连接到本教程前面创建的WebPushDataStream。 tag属性侦听Adobe数据层上的price.drop事件，并通过更新ProductListItems数据元素来映射相关的产品详细信息。 准备数据后，tag属性中的规则将触发，并通过Web SDK将price.drop事件发送到AEP。 然后，此事件将作为Adobe Journey Optimizer中历程的入口点，从而能够根据价格下降即时发送推送通知。



