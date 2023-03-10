---
title: L731备忘单
description: 本页包含 L731 Summit Lab 中当前正在使用的文本和链接。
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: e68fc9ac728abe79936090c6fa1b0874e021f3b8
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 49%

---

# Summit Lab L731  — 备忘单

本页包含 L731 Summit Lab 中当前正在使用的文本和链接。您可以通过它将内容复制并粘贴到 Journey Optimizer 消息中。

## 练习1.1 — 下载并安装应用程序

扫描二维码以下载应用程序

>[!BEGINTABS]

>[!TAB iOS]

![iOS的二维码](/help/assets/lab731-ios-qr-code.png)

>[!TAB Android]

![适用于Android的二维码](/help/assets/lab731-android-qr-code.png)

>[!ENDTABS]

## 练习1.3：登录到Adobe Journey Optimizer

[单击此处登录Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**登录详细信息：**

* **用户名：** `L731+<your seat number>@summitlab.us` (示例： L731+001@summitlab.us)
* **密码：** Adobe2023！


## 练习 2.1 创建应用程序内营销活动

| 字段 | 文本 | 链接 |
|----|----|----|
| 营销活动名称 | `<your seat number> March Vegas Campaign` |  |
| 匹配程序 | booknow |  |
| 媒体 URL 选项 |  | https://mcfadyen.com/wp-content/uploads/2023/01/Adobe-Summit-2023-Banner.png |
| 标题 | 活动开始，速来围观！ |  |
| 正文 | Adobe Summit 将于 2023 年 3 月 21 日至 23 日重返拉斯维加斯。准备迎接鼓舞人心的演讲、技能拓展课程和结识新朋友的机会。 |  |
| 按钮 | 立即预订酒店即可享受九折优惠 | lab://booking?suite=presidential&amp;discount=10 |
| 按钮：交互式事件 | 应用程序内CTA |  |
| 基本 URL |  | iOS： lab:// <br>Android： https://lab |


## 第 3 课 - 创建全渠道历程

>[!BEGINTABS]

>[!TAB 推送消息]

**标题:**\
欢迎来到拉斯维加斯旅馆！

**正文:**\
免去排队的烦恼，直接使用移动应用程序登记

**深层链接：** lab://checkin

**媒体:**

https://experienceleague.adobe.com/docs/journey-optimizer-learn/assets/vegas_online_check_in.jpg?lang=en


这是我们用于推送通知的图像：

![在线登记](/help/assets/vegas_online_check_in.jpg)

|短信| ||| |电子邮件|{{profile.person.name.firstName}}，您已签入，立即查看我们的优惠供您停留！|||

>[!TAB 短信消息]

**消息：**
欢迎来到维加斯住宿酒店。 免去排队的烦恼，直接使用移动应用程序登记：lab://checkin

>[!TAB 电子邮件]

**主题行：**
{{profile.person.name.firstName}}，您已签入，立即查看我们的优惠供您留宿！

>[!ENDTABS]