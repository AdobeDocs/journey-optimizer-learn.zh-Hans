---
title: 创建营销活动
description: 创建营销活动，以定向选择接收推送通知并在计划时间发送消息的用户。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%

---

# 创建营销活动

在此步骤中，您将在Adobe Journey Optimizer中创建一个营销活动，以向已选择加入的用户发送计划的Web推送通知。 营销活动以符合条件的受众为目标，在预定义的时间发送消息，从而实现计划的和基于受众的参与。

* 登录到Journey Optimizer
* 导航到历程管理|营销活动|创建营销活动

## 指定Campaign设置


指定营销活动名称

![营销活动名称](assets/campign-push-notification.png)

## 将操作与营销活动关联

关联本教程前面创建的推送渠道配置

![营销活动操作](assets/campign-push-notification-action.png)

## 将受众与营销活动关联

将受众`AudienceForPush`与营销活动关联

![营销活动受众](assets/campign-push-notification-audience.png)

## 为推送通知创建内容

创建基本推送内容以测试推送通知。 指定消息的标题和正文，如下所示

![针对推送通知的内容](assets/campign-push-notification-content.png)

## 计划营销活动

根据您的需求计划活动

![schedule-campaign](assets/campign-push-notification-schedule.png)

最后，确保激活营销策划。

## 测试活动

要测试营销活动，请在出现提示时通过选择加入[首先在](http://localhost:3000)网页上启用通知。 选择加入后，请等待营销活动在其计划时间运行。 当活动执行时，您应会在浏览器中收到推送通知。




