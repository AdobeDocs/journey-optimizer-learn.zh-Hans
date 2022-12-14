---
title: 创建订单确认电子邮件
description: 测试有关如何创建和个性化事务型消息的知识
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: d361a15661642f770ab7f5527f561eb0bce16b9d
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 4%

---


# 创建订单确认电子邮件

![订单确认](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| 挑战 | 创建订单确认事务型电子邮件 |
|---|---|
| 角色 | 历程管理器 |
| 所需技能 | <ul><li>[使用消息编辑器创建电子邮件内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[使用上下文事件信息进行个性化](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[使用辅助函数进行个性化](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| 要下载的资产 | [订单确认资产](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## 故事

Luma将启动其在线商店，并希望在客户下订单后通过提供订单确认电子邮件来确保客户获得良好的体验。



## 您的挑战

创建一个旅程，在Luma客户完成在线订单时发送订单确认电子邮件。 《鹿马》

>[!BEGINTABS]

>[!TAB 任务]

1. 创建名为 `Luma - Order Confirmation`
2. 使用事件： `LumaOnlinePurchase` 作为触发器
3. 创建名为 `Luma - Order Confirmation`:

* 类别事务型 — 确保选择事务型电子邮件界面
* 主题行必须使用收件人的名字进行个性化，并且必须包含“感谢您的购买”短语
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
    <strong>Luma徽标</strong>
      <p>
     <li>luma_logo.png</li>
    <li>它应具有指向luma网站的链接：https://publish1034.adobedemo.com/content/luma/us/en.html</li>
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
    <em>{名字}</em><p>
    <li>对齐方式：left  </li>
   <li>文本颜色：rgb(69, 97, 162)#4461a2; 
   <li>字体大小：20px</li>
   <div>
    <p>
     <em>已下订单。
    <p>包发货后，我们会向您发送一封包含跟踪号码的电子邮件，以便您跟踪订单。</p></em>
    </strong>
    </tr>
  </td>
 <td>
  <div>
     <strong> 收货区</strong>
      </div>
      <p><li>将模板中的硬编码地址替换为送货地址 
      <li>详细信息是事件（街道、城市、邮政编码、州）中的上下文属性
      <li>名字和姓氏来自配置文件
      <li> 删除折扣、总计、到达</p>
  </td>
  <td>
  <p> 收货方：</p>
      <em>名字姓氏<br>
      地址<br></em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>订单详细信息部分</strong>
      </div>
       <p><li>在 <b>收货方</b> 部分和 <b>查看顺序</b> 按钮
      </p><br>
      <p><b>提示:</b>
      <li>这是上下文事件信息。
      <li>使用[!UICONTROL帮助程序函数]:[!UICONTROL Each]
      <li>切换到代码编辑器格式以添加上下文数据。
      <li>使用DIV标记将信息放入容器中。
  </td>
  <td>
    <strong>头</strong>
    <p>
    <em>订单{采购订单编号}</em>
    </p>
    <strong>已订购的产品列表：
  </strong>
  <p>每个项目的格式应如下所示：
   <img alt="订购" src="./assets/c2-order.png"> 
</p>
<strong>产品图像：</strong>
<li>类：购物车椅
<li>样式：边框：min-height:40px</li>
<li>上边距和下边距：20px</li>
<li>padding-left:80px</li>
<li>border-radius:0px</li>
<li>用作容器的背景图像</li>
<li>背景位置：0% 50%</li>
<li>背景大小：60px</li>
<li>background-repeat:无重复</li>
<p>
<strong>价格:</strong>
<li>格式= H5</li>
<li>style = box-sizing:border-box</li>
<li>margin-bottom:5px</li>
<li>margin-top:0px;</li>
<p>
<strong>名称和数量：</strong>
<li>class=text-small</li>
<li>style=box大小：边框</li>
<li>padding-top:5像素</li>
<li>颜色：rgb(101, 106, 119)</li>
<li>font-size:14px</li>
<p>
</td>
  </tr>
</table>


>[!TIP]
>
>为了让您对历程进行故障诊断，最佳做法是在超时或出错的情况下为所有消息操作添加替代路径。

>[!TAB 成功标准]

触发您在测试模式下创建的历程，并向您自己发送电子邮件：

1. 通过单击眼睛符号显示隐藏值：
   1. 在电子邮件参数中，单击T符号（启用参数覆盖）
      ![覆盖电子邮件参数](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. 单击Address字段
   3. 在下一个屏幕上，将您的电子邮件地址添加到括号中： *yourname@yourdomain* 在表达式编辑器中，单击确定。
2. 将历程置于测试模式
3. 使用以下参数触发事件：
   * 将配置文件标识符设置为：Jenna_Palmer9530@emailsim.io
   * 事件类型：commerce.purches
   * 名称：雪碧瑜伽伴侣套件
   * 数量：1
   * 总价：61
   * 订单编号：6253728
   * SKU:24-WG080
   * productImageURL: <https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/luma-yoga-kit-2.jpg>

您应会收到包含指定产品的个性化购买确认电子邮件。

* 主题行应以测试用户档案的名字开头：珍娜
* 在测试时输入的订单详细信息应填充订单详细信息部分
* 客户信息应包含测试用户档案的城市和邮政编码：

   华盛顿特里尔泰勒斯43913 20099



>[!TAB 检查您的工作]

** 历程

![历程](/help/challenges/assets/c2-journey.png)


** 电子邮件

**主题行：**

{{ profile.person.name.firstName }}，感谢您的购买！


**更详细的章节：**

![订单详细信息部分](/help/challenges/assets/c2-order-detail-section.png)

以下是您的代码所应显示的内容：

标头:

```javascript
Order: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

产品列表：

使用帮助程序函数“each”创建产品列表。 以下是您的代码所应显示的内容：

```javascript
{{#each context.journey.events.1911672547.productListItems as|product|}}
<div class="cart-item-chair" style="box-sizing:border-box;min-height:40px;padding-top:20px;padding-bottom:20px;padding-left:80px;border-radius:0px;background-image:url({{product._wwfovlab065.productImageURL}});background-position:0% 50%;background-size:60px;background-repeat:no-repeat;">
<h5 style="box-sizing:border-box;margin-bottom:5px;font-size:16px;line-height:20px;margin-top:0px;">${{product.priceTotal}}.00</h5>
<div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">{{product.name}}</div><div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">Quantity: {{product.quantity}}</div></div><div class="divider-small" style="box-sizing:border-box;height:1px;margin-top:10px;margin-bottom:10px;background-color:rgb(209, 213, 223);"> </div>
{{/each}}

Total: ${{context.journey.events.1627840522.commerce.order.priceTotal}} 
```

**客户信息部分**

![客户地址](assets/c2-customer-information.png)

个性化应当如下所示：

```javascript
{{profile.homeAddress.street1}}
{{profile.homeAddress.city}},{{profile.homeAddress.state}} {{profile.homeAddress.postalCode}}
```

>[!ENDTABS]