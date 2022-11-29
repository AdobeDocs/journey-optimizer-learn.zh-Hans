---
title: 产品补充难题
description: 应用您在创建区段方面学到的知识并测试您的技能。
kt: 8417
feature: Segments
role: User
level: Beginner
hide: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 2%

---

# 产品补充难题

| 挑战 | 产品补充 |
|---|---|
| 角色 | 历程管理器 |
| 所需技能 | <ul><li>[创建区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-segments.html?lang=en)</li><li> [导入和编辑 HTML 电子邮件内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/import-and-author-html-email-content.html?lang=en)</li><li>[用例 - 读取区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| 要下载的资产 | [季节性收藏集电子邮件文件](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## 故事

在浏览Luma网站时，客户可以将他们感兴趣的产品添加到愿望清单。 这允许Luma向客户发送有针对性的营销消息和产品信息。

## 您的挑战

Luma要求您在Journey Optimizer中实施一个历程，该历程会通知客户，如果客户的愿望列表中有一个以前缺货的项目，当该项目重新存货时。

## 定义区段 — 无现货愿望清单项目

要在重新存储产品时定位潜在的感兴趣的客户，请创建一个由客户组成的区段

* 在其愿望列表中至少添加了一个项目的用户(使用事件类型： [!UICONTROL 商务保存为延迟])
* 那是 **缺货** 最近3个月（使用库存数量= 0）
* 而且从那以后就没买过这个。

将此区段命名为： *你的名字 — 无现货清单*

+++**检查您的工作**

您的区段应如下所示：

![区段 — 无现货愿望清单项目](/help/challenges/assets/C1-S2.png)

在其愿望清单中添加过去3个月内无现货的项目的客户：

* 事件：为后期保存
   * 至少包括1个
   * 其中库存数量为0

并且此后从未购买过该项目：

* 从 **保存供以后使用的事件**.

>[!TIP]
> * 在 *浏览变量* 部分
> * 将SKU放入事件字段的保存以供以后使用时，请使用比较选项


检查“Edit segment（编辑）”屏幕右下角的“Events（事件）”下的代码。 代码应当如下所示：

代码:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

+++

### 创建电子邮件 — Luma产品补充

通知已添加缺货项目且调用开始购物的客户，该项目现已重新有现货。

### 创建历程 — 产品重新库存通知

当以前缺货的商品重新有现货时，通知已添加缺货商品并调用开始购物的客户，该商品现在已有现货。

1. 创建名为“your name_Luma - Product Restock”的历程
1. 当产品重新存货时，应触发历程
1. 发送 *Luma产品补充* 电子邮件至
1. 在此项目无现货时将此项目添加到其愿望清单的用户

>[!TIP]
>
> 使用现有业务事件。 您需要添加一个条件，以检查是否将重新存储的SKU包含在（任何）事件类型中，并将其保存为延迟。

+++**成功标准**

测试您的历程:

1. 确保区段鉴别事件具有命名空间=电子邮件
1. 覆盖默认的电子邮件参数并将其设置为您自己的电子邮件地址(有关说明，请参阅电子邮#1)
1. 将历程设置为测试模式
1. 触发事件 — 输入以下数据：

   * 描述：别想花哨的机器和昂贵的会员资格了 — Harmony Lumaflex Longth Band Kit是您进行令人惊叹的锻炼所需的一切。 该工具包提供您进行一系列增强和调音练习所需的一切。
   * 名称：谐音Lumaflex强度带套件
   * 价格：22
   * 产品ID:2003年8月24日
   * 产品图像URL:https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU网站：2003年8月24日
   * 股票事件类型：重新存储
   * 配置文件标识符：Jenna_Palmer9530@emailsim.io

您应会收到“Luma电子邮件产品补充”电子邮件，其中包含产品详细信息和Jenna的个性化设置。

+++

+++**检查您的工作**

您的历程应如下所示：

![产品补充历程](/help/challenges/assets/c3-j3-journey.png)

条件：在愿望清单中

![条件 — 在愿望列表中](/help/challenges/assets/c3-j3-condition.png)

条件代码：

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```

+++
