---
title: L535备忘单
description: 本页包含在L535 Summit Lab中使用的文本和链接。
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: 1c3f4341-1293-463d-bee0-57440fcff23a
source-git-commit: 5a3133830b3606008764ccb2c7130dea063d48f1
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 22%

---

# Summit Lab L535 — 备忘单

本页包含在L535 Summit Lab中使用的文本和链接。 您可以通过它将内容复制并粘贴到 Journey Optimizer 消息中。

## 链接

* [SecurFinancial网站](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U){target="_blank"}
* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys){target="_blank"}
* [L535工作簿](/help/summit-lab-assets/assets/summit_lab-manual-l535-final.pdf){target="_blank"}
* [下载应用](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html){target="_blank"}

## 复制并粘贴练习

### 练习2.1 — 登录到Journey Optimizer

使用以下详细信息登录：

电子邮件地址：    L535+*您的座位号*@adobeeventlab.com

密码：       Adobe4峰会！


### 练习2.3 — 撰写电子邮件

#### 提示

```
Generate a welcome email for new SecurFinancial customers who just opened a new checking account. 
Add a call to action to install the SecurFinancial mobile app.
```

### 练习3.1 — 将动态内容应用于短信消息

#### 代码

```
{%#if select _Push_details1 from profile.pushNotificationDetails where
_Push_details1.token.isNotNull()%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Open the
app
{%else%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Click here
to install the app: https://demo-systemnext.
s3.amazonaws.com/dxdemo/summit/index.html
{%/if%} 
```

### 练习4.2 — 配置处理

#### 标题

```
Welcome to SecurFinancial
```

#### 正文文本

```
Did you know you can find an ATM near in the SecurFinancial app? Try it now!
```

#### URL

```
dxdemo://atm
```

### 练习6 — 内容卡

#### 标题

```
Welcome to SecurFinancial!
```

#### 正文

```
Thank you for downloading the app. You can find ATMs, track your spending and more. All within the app.
```

#### 媒体 URL

```
https://demo-system-next.s3.amazonaws.com/assets/securfinancial/home-loan.jpg
```

#### 按钮标题

```
Find ATMs
```

#### 目标 URL

```
dxdemo://atm
```

## 图像

![安全财务徽标](/help/summit-lab-assets/assets/SecureFinancial-logo.png)


![手机](/help/summit-lab-assets/assets/online-banking-app-01.png)


