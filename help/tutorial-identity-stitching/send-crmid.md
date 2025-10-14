---
title: 构建示例应用程序以模拟登录活动
description: 构建示例Node.js应用程序以模拟登录流程
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: e080149c-0ac0-4559-b99d-ebad9f03b98b
source-git-commit: 667f146639635515a5572e9ace41d83ab4452bb8
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# 构建示例应用程序以模拟登录活动

此示例应用程序构建并部署在Node.js服务器上，用于演示在用户登录时如何将CRM ID发送到Adobe Experience Platform (AEP)。 该应用程序模拟登录流程，其中在服务器端验证用户凭据。 成功登录后，将会检索用户的CRM ID并将其推送到adobeDataLayer，从而触发Adobe Experience Platform Tags(以前称为Adobe Launch)中的相应规则。

attachLoginHandler函数将提交事件侦听器附加到登录表单。 在提交表单时，它会阻止默认操作，根据预定义用户的对象验证凭据，然后检索CRM ID（如果有效）。 函数会将具有CRM ID和身份验证状态的userloggedin事件推送到adobeDataLayer，然后Adobe Experience Platform Tags会提取该事件以将数据发送到Adobe Experience Platform (AEP)。


```javascript
function attachLoginHandler() {
    const form = document.getElementById("loginForm");
    if (!form) return;

    form.addEventListener("submit", function(e) {
        e.preventDefault();
        const username = document.getElementById("username").value;
        const password = document.getElementById("password").value;

        if (users[username] && users[username].password === password) {
            const crmid = users[username].crmid;
            window.adobeDataLayer = window.adobeDataLayer || [];
            debugger;
            window.adobeDataLayer.push({
                event: "UserLoggedIn",
                user: {
                    crmid: crmid,
                    authenticatedState: "authenticated"
                }
            });
        }
    });
}
```

Adobe Experience Platform标记脚本使用`<head>`标记包含在HTML页面的`<script>`部分中，通常如下所示：

`<script src="https://assets.adobedtm.com/b5eu4857867/4e4d84957/launch-b69e276bb9b5-development.min.js" async crossorigin="anonymous"></script>`

AEP Tags脚本是通过发布在之前步骤中创建的启用了Web SDK的属性并从“环境”选项卡复制嵌入代码来获取的。
