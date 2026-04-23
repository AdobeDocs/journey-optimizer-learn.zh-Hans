---
title: 在本地运行应用程序
description: 在本地设置示例应用程序以使用AJO浏览Web推送通知流程。
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 2635641b-5ae2-4303-bac7-02c3702950f0
source-git-commit: c339fe796af1e691cd3b1c98cd6ba8a8772551e4
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# 在本地运行应用程序

此页面将指导您本地设置示例应用程序，以便您可以使用Adobe Journey Optimizer测试和浏览Web推送通知流程。 您将克隆存储库、配置环境变量并在本地系统上运行应用程序。


按照以下步骤在本地系统上运行示例应用程序。

## 1.安装Node.js

确保在系统上安装了&#x200B;**Node.js（版本16或更高版本）**。

您可以[在此下载：](https://nodejs.org/)

验证安装

```node -v```

```npm -v```


## 2.克隆存储库

```git clone https://github.com/gbedekar489/ajo-web-push.git```

```cd ajo-web-push```

## 3.安装依赖项

```npm install```

## 4.配置环境变量

在根目录中创建.env文件，并添加以下内容：

```
DATASTREAM_ID=your_datastream_id
ORG_ID=your_org_id
VAPID_PUBLIC_KEY=your_vapid_public_key
APP_ID=your_app_id
DATASET_ID=your_event_dataset_id
PORT=3000
```


在本地运行时，将从.env文件中读取这些值。 在生产（例如，渲染）中，它们被配置为环境变量。
