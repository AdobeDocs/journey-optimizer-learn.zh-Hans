---
title: 产品补货挑战
description: 运用您在创建区段方面学到的知识并检验您的技能。
jira: KT-8417
feature: Segments
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 5c763ec877c75c07132f4cc714d63695e12638dc
workflow-type: ht
source-wordcount: '580'
ht-degree: 100%

---

# 产品补货挑战

| 挑战 | 产品补货 |
|---|---|
| 角色 | 历程管理者 |
| 所需技能 | <ul><li>[创建区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=zh-Hans)</li><li> [导入和编辑 HTML 电子邮件内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=zh-Hans)</li><li>[用例 - 读取区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=zh-Hans)</li> |
| 可供下载的资源 | [产品重新上架电子邮件文件](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip) |

## 案例

在浏览 Luma 网站时，客户可以将他们感兴趣的产品添加到愿望清单，这样 Luma 就可以向客户发送有针对性的营销消息和产品信息。

## 您的挑战

Luma 要求您在 Journey Optimizer 中实施一个历程，如果客户的愿望清单中有一个以前缺货的商品，当该商品再次有存货时，该历程会通知客户。创意团队为您提供[产品重新上架电子邮件文件](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip)。

>[!BEGINTABS]

>[!TAB 任务]

## 1. 定义区段 – 缺货的愿望清单商品

要在产品重新上架时定位潜在的感兴趣的客户，请创建一个由客户组成的受众：

* 这些客户的愿望清单中至少添加了一个商品（使用事件类型：[!UICONTROL 商务暂存]）
* 这些商品最近三个月缺货（使用库存数量 = 0）
* 而且这些客户从那以后就没买过该商品。

>[!TIP]
>排除所有与&#x200B;*暂存事件*&#x200B;的 SKU 匹配的购买事件类型。您可以在&#x200B;*浏览变量*&#x200B;部分中找到相关字段。

将此区段命名为：`Out-of-stock-Wishlist`


### 2. 创建历程 – 产品重新上架通知

当以前缺货的商品重新上架时，通知添加了缺货商品并设置了到货通知的客户，该商品现在又有了存货，号召他们开始购买。

1. 调用历程：`Product Restock`
2. 当产品重新上架时，应触发历程
3. 发送&#x200B;*产品重新上架电子邮件*&#x200B;给
4. 在此商品缺货时将其添加到愿望清单的用户

>[!TAB 成功标准]

测试您的历程：

1. 确保读取区段事件的命名空间 = `Luma CRM ID`
1. 覆盖默认的电子邮件参数并将其设置为您自己的电子邮件地址（有关说明，请参阅电子邮件 1）
1. 将历程设置为测试模式
1. 触发事件 - 输入以下数据：

   * 描述：忘记那些花哨的机器和昂贵的会员资格吧 - 拥有 Harmony Lumaflex Strength Band Kit，就拥有了畅快健身所需的一切。该套装提供您进行一系列强化和塑身运动所需的一切。
   * 名称：Harmony Lumaflex Strength Band Kit
   * 价格：22
   * 产品 ID：24-UG03
   * 产品图像 URL：https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU: 24-UG03
   * 库存事件类型：重新上架
   * 用户档案标识符：Jenna_Palmer9530@emailsim.io

您应会收到“Luma 电子邮件产品补货”电子邮件，其中包含产品详细信息和针对 Jenna 的个性化设置。

>[!TAB 检查您的工作]

您的区段应如下所示：

![区段 - 缺货的愿望清单商品](/help/challenges/assets/C1-S2.png)


您的历程应如下所示：

![产品补货历程](/help/challenges/assets/c3-j3-journey.png)

条件：在愿望清单中

![条件 - 在愿望清单中](/help/challenges/assets/c3-j3-condition.png)

条件代码：

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```


>[!TIP]
> * 在 *Browse Variables* 部分中选择“暂存”下的 SKU
> * 将“暂存”下的 SKU 放入事件字段时，请使用比较选项

检查“事件”下“编辑区段”屏幕右下角的代码。代码应如下所示：

代码：
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

>[!ENDTABS]

### 创建电子邮件 - Luma 产品补货

通知添加了缺货商品并设置了到货通知的客户，该商品现在又有了存货，可以开始购买。



>[!TIP]
>
> 使用现有业务事件。添加一个条件，以检查（任何）“暂存”事件类型中是否包含将重新上架的 SKU。
>




