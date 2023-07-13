---
title: L731 备忘单
description: 本页包含 L731 Summit Lab 中当前正在使用的文本和链接。
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: d44943b27a1681a2f264e762a2eac9d993ce46be
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 76%

---

# Summit Lab L731- 备忘单

本页包含 L731 Summit Lab 中当前正在使用的文本和链接。您可以通过它将内容复制并粘贴到 Journey Optimizer 消息中。

## 练习 1.1 - 下载和安装应用程序

扫描 QR 代码以下载应用程序

>[!BEGINTABS]

>[!TAB iOS]

![适用于 iOS 的 QR 代码](/help/assets/lab731-ios-qr-code.png)

系统将要求您安装 Testflight，请参阅第 1 步至第 4 步。 安装 Testflight 后，请按照第 5 步至第 8 步的说明安装 Vegas Stay 应用程序：

<table>
<tr>
</tr>
<tr>
<td>
 <div>
      <p>
      <b>步骤 1 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-1.png"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>步骤 2 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-2.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>步骤 3 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-3.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>步骤 4 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-4.PNG"/>
      </a>
      </div>
  </td>
  </tr>
  <tr>
<td>
 <div>
      <p>
      <b>步骤 5 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-5.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>步骤 6 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-6.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>步骤 7 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-7.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>步骤 8 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-8.PNG"/>
      </a>
      </div>
  </td>
  </tr>
</table>

>[!TAB Android]

![适用于 Android 的 QR 代码](/help/assets/lab731-android-qr-code.png)

由于应用程序未在 Google Play 商店中注册，因此您将收到一条警告消息：

![Android 警告屏幕](/help/assets/lab731-install-android.png)

单击&#x200B;**仍要安装**

>[!ENDTABS]

## 练习 1：登录到 Adobe Journey Optimizer

[单击此处登录到 Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**登录详细信息：**

* **用户名：**`L731+<your seat number>@summitlab.us`（示例：L731+001@summitlab.us）
* **密码：** Adobe2023!


## 练习 2 创建应用程序内营销活动

| 字段 | 文本 | 链接 |
|----|----|----|
| 营销活动名称 | `<your seat number> Vegas Stay Campaign` |  |
| 匹配项 | booknow |  |
| 媒体 URL 选项 |  | https://i.ibb.co/NstLhjW/Firefly-Poster-with-heading-Adobe-Max-84773.jpg |
| 标题 | 抢先买到优惠券！ |  |
| 正文 | Adobe·麦克斯回到拉斯维加斯。 准备迎接鼓舞人心的演讲、技能拓展课程和结识新朋友的机会。立即预订套房，现享10%优惠。 |  |
| 按钮 | 享受10%的折扣！ | lab://booking?suite=presidential&amp;discount=10 |
| 按钮：交互式事件 | 应用程序内 CTA |  |
| 基本 URL 用于在设备上预览 |  | **iOS：** lab:// <br>**Android**： https://lab |


## 练习3：创建推送通知

| 字段 | 文本 | 链接 |
|----|----|----|
| 营销活动名称 | `<your seat number> Max Push Campaign` |  |
| 媒体 URL 选项 |  | https://i.ibb.co/NstLhjW/Firefly-Poster-with-heading-Adobe-Max-84773.jpg |
| 标题 | 嘿！ |  |
| 正文 | 你知道麦克斯Adobe要回拉斯维加斯吗。 现在预订房间，可享受10%的折扣。 |  |
