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
source-git-commit: e2312c022f589ebf1218e1767bbc129b57fa1e2a
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 64%

---

# Summit Lab L731  — 备忘单

本页包含 L731 Summit Lab 中当前正在使用的文本和链接。您可以通过它将内容复制并粘贴到 Journey Optimizer 消息中。

## 练习1.1 — 下载并安装应用程序

### iOS

![iOS的二维码](/help/assets/lab731-ios-qr-code.png)

### Android — 占位符

![适用于Android的二维码](/help/assets/lab731-ios-qr-code.png)


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

| 消息 | 标题/主题行 | 文本 | 链接 |
|----|----|----|----|----|
| 推送 | 欢迎来到拉斯维加斯旅馆！ | 免去排队的烦恼，直接使用移动应用程序登记 | lab://checkin |  |
| 短信 |  | 欢迎来到 Vegas Stay。 免去排队的烦恼，直接使用移动应用程序登记：lab://checkin |  |
| 电子邮件 | {{profile.person.name.firstName}}，您已签入，立即查看我们的优惠供您留宿！ |  |  |


这是我们的短信和推送通知所使用的图像：

![在线登记](/help/assets/vegas_online_check_in.jpg)
