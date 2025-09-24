---
title: 测试解决方案
description: 测试解决方案
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: b7bad65d-c978-4981-a914-6cb039433c8b
source-git-commit: 71b42350370d12ce677bf075d8b48edcbe541ab4
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# 测试身份拼接

此示例应用程序模拟了一个真实登录流程，在将CRM ID发送到Adobe Experience Platform (AEP)之前，将在服务器端验证用户凭据。 本地Node.js服务器用于安全地提供网页、处理基本身份验证逻辑以及避免可能会妨碍Adobe Launch或Web SDK功能的浏览器限制（例如阻止本地文件访问或缺少CORS标头）。 这种设置可确保体验更接近真实的生产环境。

## 安装节点.js

如果未安装Node.js，请从此处[下载并](https://nodejs.org/)安装它

通过运行以下命令来验证安装：

`node -v`

`npm -v`

## 设置项目文件夹

使用以下命令为示例应用程序创建新目录

`mkdir aep-demo`

`cd aep-demo`

## 初始化项目

`npm init -y`

## 安装Express （Web服务器框架）

`npm install express`

## 创建server.js文件

```javascript
const express = require('express');
const path = require('path');
const app = express();
const PORT = 3000;

// Serve static files from the current directory
app.use(express.static(__dirname));

app.listen(PORT, () => {
  console.log(`Server is running at http://localhost:${PORT}`);
});
```

## 添加HTML/Assets

将提供的所有[HTML和CSS文件](assets/login-app-files.zip)复制到此文件夹中。 将AEP Tags脚本复制并粘贴到index.html文件的`<head>`部分中。

## 运行服务器

`node server.js`

## 测试

打开`http://localhost:3000` url。 登录使用alice/pass123

## 使用AEP调试器

Adobe Experience Platform Debugger是一个功能强大的浏览器扩展，可帮助验证从您的网站发送到Adobe Experience Platform的数据。 它对于检查是否正确配置了identityMap并通过Adobe Web SDK (alloy.js)传输尤为有用。

在测试登录事件、验证身份拼接（例如，正在传递的ECID和CRMID）并确保按预期触发AEP Tags规则和数据元素时，请使用AEP Debugger。 它提供对传出事件、身份信息和XDM有效负载的实时可见性，这对于用户档案扩充和受众资格故障排除至关重要。

以下屏幕截图显示了正确传递的ID“FIN001”。
![aep-debugger](assets/aep-debugger.png)

## 在AEP中验证身份拼接的步骤

* 登录AEP
* 导航到客户 — >配置文件 — >浏览
* 搜索FinWise CRM ID = FIN001
* 打开配置文件并查看身份部分。 您应该会看到CRMID和ECID都已列出。   这可以确认这两个身份已合并到单个个人资料中。
* 历程也应该被触发。通过查看历程报告验证这一点
* ![历程报告](assets/journey-triggered-report.png)


