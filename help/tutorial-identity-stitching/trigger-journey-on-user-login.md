---
title: 使用Adobe Journey Optimizer Web SDK触发Adobe历程
description: 了解如何利用通过Adobe Journey Optimizer标记配置的AEP Web SDK从用户登录等网站事件开始Adobe Experience Platform历程
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-09-24T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-19287
source-git-commit: c9d62ef509d557b2dfa49c698580df7c4942d299
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---

# 使用Adobe Journey Optimizer Web SDK触发Adobe历程

在身份拼接教程的这个扩展中，会触发Adobe Journey Optimizer历程，从而使用登录用户拼接的配置文件向其发送电子邮件。 **本文假定您熟悉电子邮件渠道并为电子邮件渠道创建内容。**

## 创建电子邮件渠道配置

* 登录到&#x200B;_**Journey Optimizer**_
* 导航到&#x200B;_**管理 — >渠道 — >创建渠道配置**_
* 从渠道列表中选择&#x200B;**电子邮件**。 提供有意义的名称和描述。
* 填写电子邮件设置。
* 提供如下所示的执行详细信息。 电子邮件将发送到存储在字段中的用户档案的电子邮件地址
* ![电子邮件渠道](assets/email-channel-execution.png)
* 激活电子邮件渠道配置

## 创建事件

* 登录到&#x200B;_**Journey Optimizer**_
* 导航到&#x200B;_**管理 — >配置**_
* 单击事件信息卡的管理按钮，然后单击创建事件。 指定如下所示的值
* ![历程事件](assets/journey-event.png)

* 检查事件的eventType是否等于UserLoggedIn。 为简单起见，在此例中，事件名称和事件类型是相同的。`in(@event{event1.eventType}, ['UserLoggedIn'])`
* 保存事件

## 创建旅程

* 登录到&#x200B;_**Journey Optimizer**_
* 导航到&#x200B;_**历程管理 — >历程->创建历程**_
* 将&#x200B;_**UserLoggedIn**_&#x200B;事件拖放到画布上
* 从操作菜单中拖放电子邮件。 配置电子邮件操作以使用之前创建的电子邮件渠道配置
* 发布历程

## 历程的触发方式

当通过Web SDK发送的事件有效负载与旅程中配置的匹配时，将触发旅程。 在此示例中，事件和事件类型为&#x200B;**UserLoggedIn**



