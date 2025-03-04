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
source-git-commit: 51ab40981a42b0df56d3994f1155eb4ae7575b17
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 21%

---

# Summit Lab L535 — 备忘单

本页包含在L535 Summit Lab中使用的文本和链接。 您可以通过它将内容复制并粘贴到 Journey Optimizer 消息中。

## 链接

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys)
* [SecurFinancial网站](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U)
* [下载应用](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html)

## 练习

### 练习 2.3

**步骤12**&#x200B;电子邮件提示：

为新的SecurFinancial生成欢迎电子邮件
刚开立新储蓄账户的客户。 添加
安装SecurFinancial移动应用程序的行动动员。

### 练习 3.1

**步骤7**

```javascript
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


![安全财务徽标](/help/summit-lab-assets/assets/SecureFinancial-logo.png)

![手机](/help/summit-lab-assets/assets/online-banking-app-01.png)


