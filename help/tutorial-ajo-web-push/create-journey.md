---
title: 创建历程
description: 创建在price.drop事件上触发的历程
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 14342b47-5485-4f7f-9312-cff1ee0f8972
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 0%

---

# 创建历程

在此步骤中，您将在Adobe Journey Optimizer中创建一个由自定义price.drop事件触发的历程。 收到此事件后，历程将实时启动并向已选择加入的用户发送推送通知，以启用事件驱动型参与。

要创建在price.drop事件中触发的历程，请执行以下步骤

* 登录到Journey Optimizer
* 导航到历程管理 |历程 |创建历程

![create-journey](assets/create-journey.png)

## 添加PriceDropEvent

将`PriceDropEvent`从事件部分拖到画布上。
![价格下降事件](assets/add-price-drop-event.png)

## 添加推送操作

展开操作部分。 将`Action`活动拖放到画布上，并选择“推送”作为操作类型
![推送操作](assets/add-push-action.png)

## 配置推送操作

选择推送通知活动，然后单击配置操作

![configure-push-action](assets/configure-push-action.png)

## 推送通知渠道配置

将此教程中先前创建的`MyFirstWebPushChannel`配置与此推送通知关联

![渠道配置](assets/journey-actions.png)

## 撰写推送通知消息

使用个性化编辑器将静态和动态内容的组合添加到推送通知，使消息更具吸引力且更相关。

要开始撰写邮件，请单击`Content`以打开内容选项卡，您可以在其中定义固定文本和从事件数据派生的动态字段。
![内容推送](assets/compose-message.png)

指定推送消息的标题，然后打开个性化编辑器以撰写消息正文。 内容将动态包含价格下降的产品名称。 要实现此目的，请使用each [辅助函数](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/content-management/personalization/functions/helpers#each)
对产品列表进行迭代，并在消息中呈现其名称。

## 撰写消息正文

从帮助程序函数菜单中选择`Each`函数并将其插入。
![辅助函数](assets/journey-content-helper-function.png)

选择上下文属性 |Journey Orchestration |活动 | PriceDropEvent | productListItems |名称

单击“+”图标，将数组插入个性化编辑器中的每个循环中。 然后，更新消息内容以匹配参考屏幕快照中显示的格式。 请注意，环境中显示的事件ID可能与显示的ID不同。

![上下文属性](assets/journey-content-context-attributes.png)

最后，保存所有更改并发布历程。 发布后，历程将变为活动状态并侦听传入的price.drop事件。 每当收到此类事件时，都会实时触发历程，并向选择接收通知的用户发送推送通知，确保及时且相关的参与。

## 测试解决方案

要触发price.drop事件，请打开[价格下降触发器页面，](http://localhost:3000/price-drop-trigger.html)选择一个或多个产品，然后单击“触发价格下降”。 这会使用AEP Tags通过Adobe Data Layer发送事件，然后会启动历程并实时发送推送通知。
