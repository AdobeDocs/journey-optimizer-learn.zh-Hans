---
title: 创建订单确认电子邮件
description: 检验您所掌握的有关如何创建和个性化事务型消息的知识
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 4268144ade6588e48fc38cae7e542c227af96827
workflow-type: ht
source-wordcount: '686'
ht-degree: 100%

---


# 创建订单确认电子邮件

![订单确认](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| 挑战 | 创建订单确认事务型电子邮件 |
|---|---|
| 角色 | 历程管理者 |
| 所需技能 | <ul><li>[使用消息编辑器创建电子邮件内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=zh-Hans)</li> <li>[使用上下文事件信息进行个性化](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=zh-Hans)</li><li>[使用辅助函数进行个性化](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=zh-Hans)</li></ul> |
| 可供下载的资源 | [订单确认资源](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## 故事

Luma 将启动其在线商店，并希望在客户下订单后通过提供订单确认电子邮件，由此确保客户获得良好的体验。



## 您的挑战

创建一个历程，该历程会在 Luma 客户完成在线订单时发送订单确认电子邮件。Luma

>[!BEGINTABS]

>[!TAB 任务]

1. 创建一个名为 `Luma - Order Confirmation` 的历程
2. 使用事件：`LumaOnlinePurchase` 作为触发器
3. 创建名为 `Luma - Order Confirmation` 的订单确认电子邮件：

* 类别事务型 - 确保选择事务型电子邮件界面
* 必须使用收件人的名字对主题行进行个性化设置，并且必须包含语句“感谢您购买我们的产品”
* 使用 `Luma - Order summary` 模板并对其进行修改：

电子邮件的结构应如下所示：
<table>
<tr>
<td>
  <div>
     <strong> 标题部分</strong>
      </div>
  </td>
  <td>
    <strong>Luma 徽标</strong>
      <p>
     <li>luma_logo.png</li>
    <li>它应具有指向 luma 网站的链接：https://publish1034.adobedemo.com/content/luma/us/en.html</li>
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
    <em>{名字}，您好！</em><p>
    <li>Alignment: left  </li>
   <li>Text color: rgb(69, 97, 162) #4461a2; 
   <li>font-size: 20px</li>
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
      <p><li>将模板中的硬编码地址替换为送货地址 
      <li>地址详细信息是事件中的上下文属性（街道、城市、邮政编码、州/省）
      <li>名字和姓氏来自用户档案
      <li> 移除折扣、总计、到达时间</p>
  </td>
  <td>
  <p> 收货地址：</p>
      <em>姓名<br>
地址</em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>订单详情部分</strong>
      </div>
       <p><li>在<b>收货地址</b>部分后添加此部分和<b>查看订单</b>按钮。
      </p><br>
      <p><b>提示：</b>
      <li>这是上下文事件信息。
      <li>使用 [!UICONTROL helper function]：[!UICONTROL Each]
      <li>切换到代码编辑器格式以添加上下文数据。
      <li>使用 DIV 标记将信息放入容器中。
  </td>
  <td>
    <strong>标题</strong>
    <p>
    <em>订单：`purchaseOrderNumber`</em>
    </p>
    <strong>已订购的产品列表：
 </strong>
  <p>每个商品的格式应如下所示：
 <img alt="订单" src="./assets/c2-order.png"> 
</p>
<strong>产品图像：</strong>
<li>class: cart-item-chair
<li>style: border-box: min-height:40px</li>
<li>上边距和下边距：20 像素</li>
<li>左侧内边距：80 像素</li>
<li>边框半径：0 像素</li>
<li>用作容器的背景图像</li>
<li>background-position: 0% 50%</li>
<li>background-size: 60px</li>
<li>background-repeat: no-repeat</li>
<p>
<strong>价格：</strong>
<li>格式 = H5</li>
<li>样式 = 方框大小：边框</li>
<li>底端边距：5 像素</li>
<li>顶端边距：0 像素</li>
<p>
<strong>名称和数量：</strong>
<li>类别 = 小文本</li>
<li>style=box-sizing: border-box</li>
<li>padding-top: 5px</li>
<li>color: rgb(101, 106, 119)</li>
<li>font-size:14px</li>
<p>
</td>
  </tr>
</table>


>[!TIP]
>
>为了让您能够对历程进行故障排除，最佳实践是为所有消息操作添加替代路径，以防出现超时或出错的情况。

>[!TAB 成功标准]

触发您在测试模式下创建的历程，并向您自己发送电子邮件：

1. 通过单击眼睛符号显示隐藏值：
   1. 在电子邮件参数中，单击 T 符号启用参数覆盖
      ![覆盖电子邮件参数](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. 单击地址字段
   3. 在下一个屏幕上，在表达式编辑器中将您的电子邮件地址 *yourname@yourdomain* 添加到括号中，然后单击“确定”。
2. 将历程置于测试模式
3. 使用以下参数触发事件：
   * 将用户档案标识符设置为：标识值：`a8f14eab3b483c2b96171b575ecd90b1`
   * 事件类型：commerce.purches
   * 名称：雪碧瑜伽伴侣套装
   * 数量：1
   * `Price Total:` 61
   * `Purchase Order Number:` 6253728
   * `SKU:` 24-WG080
   * `productImageURL:` <https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/luma-yoga-kit-2.jpg>
   * `City:` 圣何塞
   * `Postal Code:` 95110
   * `State`：CA
   * `Street:` 345 Park Ave

您应会收到包含指定产品的个性化购买确认电子邮件。

* 主题行应具有测试用户档案的名称：Leora
* 应使用在测试时输入的订单详情填充订单详情部分

>[!TAB 检查您的工作]

**历程**

![历程](/help/challenges/assets/c2-journey.png)


**电子邮件**

**主题行：**

{{ profile.person.name.firstName }}，感谢您购买我们的产品！

**收货地址部分：**

以下是您的代码所应显示的内容：

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416* 不同于您将会使用的数字。

提示：单独个性化每个行

**订单详情部分：**

![订单详情部分](/help/challenges/assets/c2-order-detail-section.png)

以下是您的代码所应显示的内容：

标题：

```javascript
Order: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**产品列表：**

使用辅助函数“each”创建产品列表。可在表格中显示它们。以下是您的代码所应显示的内容：

```javascript
<div class="text-container" contenteditable="true">
  <p><span class="acr-expression-field" contenteditable="false">{{#each context.journey.events.454181416.productListItems as |product|}}
    </span></p>
  <div class="cart-item-chair" style="box-sizing:border-box;min-height:40px;padding-top:20px;padding-bottom:20px;padding-left:80px;border-radius:0px;background-image:url({{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}});background-position:0% 50%;background-size:60px;background-repeat:no-repeat;">
    <h5 style="box-sizing:border-box;margin-bottom:5px;font-size:16px;line-height:20px;margin-top:0px;">${{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</h5>
    <div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">{{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</div>
    <div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">Quantity: {{product.quantity}}</div>
  </div>
  <div class="divider-small" style="box-sizing:border-box;height:1px;margin-top:10px;margin-bottom:10px;background-color:rgb(209, 213, 223);"> </div>
  {{/each}}<p></p>
  <p></p>
</div>
```

**总价：**

合计：`${{context.journey.events.1627840522.commerce.order.priceTotal}}`

**客户信息部分**

![客户地址](assets/c2-customer-information.png)

个性化设置应当如下所示：

```javascript
{{profile.homeAddress.street1}}
{{profile.homeAddress.city}},{{profile.homeAddress.state}} {{profile.homeAddress.postalCode}}
```

>[!ENDTABS]