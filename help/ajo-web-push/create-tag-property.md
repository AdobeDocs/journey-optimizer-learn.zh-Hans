---
title: 创建标记属性
description: 标记属性通过Web SDK将数据从浏览器发送到AEP。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# 创建标记属性

在本教程的第二部分中，您将了解如何通过手动发送自定义price.drop事件来实时触发推送通知。 此方法使用AEP数据收集（标记）从网页中捕获事件并将其发送到Adobe Experience Platform。 摄取事件后，它会在Adobe Journey Optimizer中触发历程，允许您根据用户操作或业务事件按需发送推送通知。

此属性使用AEP Web SDK进行配置，后者连接到本教程前面创建的`WebPushDataStream`。 标记属性侦听Adobe数据层上的`price.drop`事件，并通过更新ProductListItems数据元素来映射相关的产品详细信息。 准备数据后，tag属性中的规则将触发，并通过Web SDK将price.drop事件发送到AEP。 然后，此事件将作为Adobe Journey Optimizer中历程的入口点，从而能够根据价格下降即时发送推送通知。

## 标记元素

用于保存产品详细信息的ProductListItems

![标记元素](assets/product-list-items-element.png)

xdmvariable映射到`schemaForPushNotification`

![xdm-variable](assets/xdmvariable-data-element.png)

## 创建规则

收听price.drop事件
![data-pushed-event](assets/tag-rule-event.png)

使用更新变量更新productListItems
![更新变量](assets/update-variable.png)
最后，将price.drop事件发送到具有更新后的xdmvariable的AEP
![发送事件](assets/send-event.png)

以下javascript代码会将price.drop事件从网页发送到AEP Tags

```javascript
 <script>
      window.adobeDataLayer.push({
        event: "price.drop",
        productListItems: productListItems
      });
  </script>
```



