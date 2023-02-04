---
title: 配置事件
description: 配置完成Journey Optimizer挑战所需的三个事件
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: a0f089635df6af8fce9127083ecf582a56b5d569
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# 配置事件

在本节中，您可以在 [Journey Optimizer挑战](/help/challenges/introduction-and-prerequisites.md).

以下视频介绍如何创建事件：

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12)

## 创建Luma在线购买事件

使用此事件时，Journey Optimizer会在用户在线购买luma产品时收到相应信息。

1. 使用以下参数创建事件：

   | [!UICONTROL 参数] | [!UICONTROL 值] |
   |-------------|-----------|
   | [!UICONTROL 名称] | `LumaOnlinePurchase` |
   | [!UICONTROL 类型] | [!UICONTROL 单一] |
   | [!UICONTROL 事件ID类型] | [!UICONTROL 基于规则] |
   | [!UICONTROL 架构] | `Luma Web Events Schema` |
   | [!UICONTROL 字段] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

2. 添加 [!UICONTROL 事件ID条件]: `LumaOnlinePurchase.eventType is commerce.purchases`

   1. 选择铅笔图标以编辑字段
   2. 在 [!UICONTROL 添加事件ID条件] 模式窗口中，拖放 `eventType` 画布上
   3. 选择 `commerce.purchases`
   4. 在画布上选择确定
   5. 在模式窗口中选择确定

![添加事件条件](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. 选择 [!UICONTROL 命名空间]: `Luma CRM ID (lumaCrmId)`

2. 选择&#x200B;**[!UICONTROL 保存]**。

## 创建 *[!DNL Luma Wishlist Add]* 事件

| [!UICONTROL 参数] | [!UICONTROL 值] |
|-------------|-----------|
| [!UICONTROL 名称] | `LumaWishlistAdd` |
| [!UICONTROL 类型] | [!UICONTROL 单一] |
| [!UICONTROL 事件ID类型] | [!UICONTROL 基于规则] |
| [!UICONTROL 架构] | `Luma Product Interactions` |
| [!UICONTROL 字段] | EventType<br>productListItem.quantity<br><b>在产品列表项> Luma产品> _*[!DNL yourOrganizationID]* >产品：</b> <br>名称<br>价格<br> ProductImageURL<br>产品URL |
| [!UICONTROL 条件] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL 命名空间] | 电子邮件（电子邮件） |

## 创建 *[!DNL Luma Product Restock]* 事件

| [!UICONTROL 参数] | [!UICONTROL 值] |
|-------------|-----------|
| [!UICONTROL 名称] | `LumaProductRestock` |
| [!UICONTROL 类型] | [!UICONTROL 商业] |
| [!UICONTROL 架构] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL 字段] | SKU <br> stockEventType<br><b> yourOrganizationID > product:</b> <br>name<br>价格<br> ImageURL<br>描述 |
| [!UICONTROL 条件] | LumaProductRestock。_`your organization's ID`.inventoryEvent.stockEventType为restock |

## 恭喜

您的沙盒现已准备就绪！
