---
title: 配置事件
description: 配置 Journey Optimizer 实践挑战所需的三个事件
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: 81f5cc22d46f89ee1c7164a92988311ca6036b8b
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 100%

---

# 配置事件

在此部分中，您将设置 [Journey Optimizer 挑战](/help/challenges/introduction-and-prerequisites.md)实践练习所需的三个事件。

以下视频介绍了如何创建事件：

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12&learn=on)

## 创建 Luma 在线购买事件

使用此事件时，Journey Optimizer 会在用户在线购买 Luma 产品时收到信息。

1. 使用以下参数创建事件：

   | [!UICONTROL 参数] | [!UICONTROL 值] |
   |-------------|-----------|
   | [!UICONTROL 名称] | `LumaOnlinePurchase` |
   | [!UICONTROL 类型] | [!UICONTROL 单一] |
   | [!UICONTROL 事件 ID 类型] | [!UICONTROL 基于规则] |
   | [!UICONTROL 架构] | `Luma Web Events Schema` |
   | [!UICONTROL 字段] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

1. 添加[!UICONTROL 事件 ID 条件]：`LumaOnlinePurchase.eventType is commerce.purchases`：

   1. 选择铅笔图标可编辑相关字段。

   1. 在&#x200B;**[!UICONTROL 添加事件 ID 条件]**&#x200B;模式中，将 `eventType` 拖放到画布上。
   1. 选择 `commerce.purchases`。
   1. 在画布上选择&#x200B;**[!UICONTROL 确定]**。
   1. 在模式窗口中选择&#x200B;**[!UICONTROL 确定]**。

   ![添加事件条件](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. 选择[!UICONTROL 命名空间]：`Luma CRM ID (lumaCrmId)`

1. 选择&#x200B;**[!UICONTROL 保存]**。

## 创建 *[!DNL Luma Wishlist Add]* 事件

| [!UICONTROL 参数] | [!UICONTROL 值] |
|-------------|-----------|
| [!UICONTROL 名称] | `LumaWishlistAdd` |
| [!UICONTROL 类型] | [!UICONTROL 单一] |
| [!UICONTROL 事件 ID 类型] | [!UICONTROL 基于规则] |
| [!UICONTROL 架构] | `Luma Product Interactions` |
| [!UICONTROL 字段] | EventType<br>productListItem.quantity<br><b>In Product List Items > Luma Products > _*[!DNL yourOrganizationID]* > Product:</b> <br>名称<br>价格<br> ProductImageURL<br>ProductURL |
| [!UICONTROL 条件] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL 命名空间] | 电子邮件（电子邮件） |

## 创建 *[!DNL Luma Product Restock]* 事件

| [!UICONTROL 参数] | [!UICONTROL 值] |
|-------------|-----------|
| [!UICONTROL 名称] | `LumaProductRestock` |
| [!UICONTROL 类型] | [!UICONTROL 商业] |
| [!UICONTROL 架构] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL 字段] | SKU <br> stockEventType<br><b> yourOrganizationID > product:</b> <br>名称<br>价格<br> ImageURL<br>描述 |
| [!UICONTROL 条件] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType is restock |

恭喜！您的沙盒现已准备就绪，可供使用。
