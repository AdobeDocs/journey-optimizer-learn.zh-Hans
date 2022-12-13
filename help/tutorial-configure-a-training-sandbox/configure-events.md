---
title: 配置事件
description: 配置完成Journey Optimizer挑战所需的三个事件
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: 08dfd48d34fac09d05e57438728e1afa5f6cdef9
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 8%

---

# 配置事件

在本节中，您可以在 [Journey Optimizer挑战](/help/challenges/introduction-and-prerequisites.md).

观看视频 [创建事件](/help/set-up-journeys/create-events.md) ，以获取有关如何创建事件的指导。

## 创建Luma在线购买事件

1. 从左侧导航中，导航到 [!UICONTROL 管理] 选择 *[!UICONTROL 配置]*
1. 从 [!UICONTROL 功能板]，选择 *[!UICONTROL 管理*]* 事件

![管理事件](assets/create-events.png)

1. 单击 *[!UICONTROL 创建事件]*
1. 填写事件详细信息和参数：

   | [!UICONTROL 参数] | [!UICONTROL 值] |
   |-------------|-----------|
   | [!UICONTROL 名称] | `LumaOnlinePurchase` |
   | [!UICONTROL 类型] | [!UICONTROL 单一] |
   | [!UICONTROL 事件ID类型] | [!UICONTROL 基于规则] |
   | [!UICONTROL 架构] | Luma产品交互 |
   | [!UICONTROL 字段] | EventType <br>Order.priceTotal<br>purchaseOrderNumber<br>productListItems.quantity<br><b>在产品列表项> Luma产品目录架构> _中&#x200B;*[!DNL yourOrganizationID]* >产品：</b> <br> 名称<br>价格<br>ProductImageURL<br>产品URL |

1. 添加 [!UICONTROL 事件ID条件]: **[!DNL LumaOnlinePurchase.eventType is commerce.purchases]**

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

## 创建*[!DNL Luma Product Restock] 事件

| [!UICONTROL 参数] | [!UICONTROL 值] |
|-------------|-----------|
| [!UICONTROL 名称] | `LumaProductRestock` |
| [!UICONTROL 类型] | [!UICONTROL 商业] |
| [!UICONTROL 架构] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL 字段] | productID <br> stockEventType<br><b>在产品> Luma产品> *[!DNL yourOrganizationID]* >产品：</b> <br>名称<br>价格<br> ProductImageURL<br>描述 |
| [!UICONTROL 条件] | LumaProductRestock。_`your organization's ID`.inventoryEvent.stockEventType为restock |

## 恭喜

您的沙盒现已准备就绪！
