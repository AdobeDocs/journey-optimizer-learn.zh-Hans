---
title: 创建订单确认电子邮件
description: 检验您所掌握的有关如何创建和个性化事务型消息的知识
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 02625ddf2348f2754c821c8e49a1e70154fd6e63
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 50%

---


# 创建订单确认电子邮件

![订单确认](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| 挑战 | 创建订单确认事务型电子邮件 |
|---|---|
| 角色 | 历程管理者 |
| 所需技能 | <ul><li>[使用消息编辑器创建电子邮件内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/create-content-with-the-email-designer.html?lang=en)</li> <li>[使用上下文事件信息进行个性化](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=zh-Hans)</li><li>[使用辅助函数进行个性化](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=zh-Hans)</li></ul> |
| 可供下载的资源 | [订单确认资源](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## 故事

Luma 将启动其在线商店，并希望在客户下订单后通过提供订单确认电子邮件，由此确保客户获得良好的体验。



## 您的挑战

创建一个历程，该历程会在 Luma 客户完成在线订单时发送订单确认电子邮件。

>[!BEGINTABS]

>[!TAB 任务]

1. 创建一个名为 `Luma - Order Confirmation` 的历程
2. 使用事件： `LumaOnlinePurchase`
3. 创建 **事务性**  电子邮件 `Luma - Order Confirmation`

* 主题行“谢谢您的购买， `FirstName`&quot;
* 使用 `Luma - Order summary` 模板并对其进行修改：
   * 删除 `You may also like` 章节
   * 在电子邮件底部添加取消订阅链接

电子邮件的结构应如下所示：
<table>
<tr>
<td>
  <div>
     <strong> 标题部分</strong>
      </div>
  </td>
  <td>
      <p>
     <li>luma_logo.png</li>
    <li>它应链接到luma网站：https://luma.enablementadobe.com/content/luma/us/en.html</li>
    <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>订单确认部分
 </strong>
  </td>
  <td>
    <p>
    <strong>文本</strong><p>
    <em>{firstName},</em><p>
   <div>
    <p>
     <em>您的订单已下达。
    <p>发货后，我们会向您发送一封包含跟踪号码的电子邮件，以便您跟踪订单。</p></em>
    </strong>
    </tr>
  </td>
 <td>
  <div>
     <strong> 收货地址部分</strong>
      </div>
      <p>
      <li>名字和姓氏来自用户档案
      <li>将模板中的硬编码地址替换为 <b>送货地址</b>
      <li>地址详细信息是事件（街1号、城市、邮政编码、州）中的上下文属性
      <li> 删除 <i>折扣、总计、到达</i></p>
  </td>
  <td>
  <p> 收货地址：</p>
      <em>{firstName} {lastName}<br>
     {街1}<br>
     {City},{State} {postalCode}<br></em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>订单详情部分</strong>
      </div>
       <p><li>在 <b>收货方</b> 中。
      </p><br>
      <p><b>提示：</b>
      <li>使用结构组件 <b>左1:2列</b> 此部分
      <li>这是上下文事件信息。
      <li>使用 [!UICONTROL helper function]：[!UICONTROL Each]
      <li>切换到代码编辑器格式以添加上下文数据。
  </td>
  <td>
    <strong>标题</strong>
    <p>
  顺序： <em>{purchaseOrderNumber}</em>
    </p>
    <strong>已订购的产品列表：
 </strong>
  <p>在订单中列出每个产品，并提供图像、价格和名称。
  <p>每个项目的布局应如下所示：
   <img alt="订单" src="./assets/c2-order.png"> 
<p><b>将链接添加到购物车</b>
<p>将URL中的订单ID替换为采购订单编号：
   <i>https://luma.enablementadobe.com/content/luma/us/en/user/account/order-history/order-details.html?orderId=90845952-c2ea-4872-8466-5289183e4607</i>
</td>
  </tr>
</table>


>[!TIP]
>
>为了让您对历程进行故障诊断，最佳做法是在出现超时或错误时为所有消息操作添加替代路径。

>[!TAB 成功标准]

触发您在测试模式下创建的历程，并向您自己发送电子邮件：

1. 在切换到测试模式之前，请覆盖要发送到测试电子邮件的电子邮件参数，以访问您的电子邮件地址：
   1. 打开电子邮件详细信息视图。
   2. 在Email parameters部分中，单击T符号（启用参数覆盖）
   3. 单击地址字段
   4. 在下一个屏幕上，将您的电子邮件地址添加到括号中： *&quot;yourname@yourdomain&quot;* 在表达式编辑器中，单击确定。
2. 将历程置于测试模式
3. 使用以下参数触发事件：
   * 将用户档案标识符设置为：标识值：`a8f14eab3b483c2b96171b575ecd90b1`
   * 事件类型：commerce.purches
   * `Quantity`: 1
   * `Price Total:` 69
   * `Purchase Order Number:` 90845952-c2ea-4872-8466-5289183e4607
   * `SKU:` LLMH09
   * `City:`圣何塞
   * `Postal Code:` 95119
   * `State`：CA
   * `Street:` 公园大道245号

您应会收到个性化的购买确认电子邮件。

* 主题行应具有测试用户档案的名称：Leora

* 您的电子邮件正文应如下所示：

![电子邮件](/help/challenges/assets/c2-email.png)

>[!TAB 检查您的工作]

**历程**

![历程](/help/challenges/assets/c2-journey.png)


**电子邮件**

**主题行：**

谢谢您的购买， {{ profile.person.name.firstName }}!

**收货地址部分：**

以下是您的代码所应显示的内容：

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416* 是另一个数字。

提示：单独个性化每个行

**订单详情部分:**

以下是您的代码所应显示的内容：

标题：

```javascript
Order #: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**产品列表：**

使用辅助函数“each”创建产品列表。可在表格中显示它们。这是您的代码应该显示的样子(包含特定变量，如事件ID — 而不是 `454181416` 和您的组织I，而不是 `techmarketingdemos` ):

```javascript
{{#each context.journey.events.454181416.productListItems as |product|}}<tr> <th class="colspan33"><div class="acr-fragment acr-component image-container" data-component-id="image" style="width:100%;text-align:center;" contenteditable="false"><!--[if mso]><table cellpadding="0" cellspacing="0" border="0" width="100%"><tr><td style="text-align: center;" ><![endif]--><img src="{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}}" style="height:auto;width:100%;" height="233" width="233"><!--[if mso]></td></tr></table><![endif]--></div></th> <th class="colspan66"><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p><span style="font-weight:700;">{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</span></p></div></div><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p>${{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</p></div></div></th></tr> {{/each}}
```

**查看顺序按钮：**

`https://luma.enablementadobe.com/content/luma/us/en/user/account/order-history/order-details.html?orderId={{context.journey.events.454181416.commerce.order.purchaseOrderNumber}}`

**总价：**

合计：`${{context.journey.events.1627840522.commerce.order.priceTotal}}.00`


>[!ENDTABS]