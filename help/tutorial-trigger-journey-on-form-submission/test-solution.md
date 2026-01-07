---
title: 测试解决方案
description: 创建历程以在表单提交时发送电子邮件
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25T00:00:00Z
jira: KT-20014
source-git-commit: 043f41acd8f7f7165d9ec416d8f789f78d407ca1
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# 测试解决方案


测试解决方案
>[!VIDEO](https://video.tv.adobe.com/v/3478546)

## 部署示例资源

如果未安装Node.js，请从此处[下载并](https://nodejs.org/)安装它

通过运行以下命令来验证安装：

`node -v`

`npm -v`

## 设置项目文件夹

使用以下命令为示例应用程序创建新目录：

`mkdir trigger-journey `

`cd trigger-journey`

## 初始化项目

`npm init -y`

## 安装所需的框架

`npm install express dotenv axios cors`

## 复制资源文件

* 解压缩[project-root.zip](assets/project-root.zip)的内容，并将其放置到`trigger-journey`文件夹中。

* 在`public`文件夹中创建名为`trigger-journey`的文件夹
* 将[index.zip]的内容解压缩到公共文件夹中
* 使用适当的值更新`.env`文件。 创建HTTP Source连接时，可通过下载的cURL命令获得这些值

## 运行服务器

确保您位于`trigger-journey`目录中。
执行命令`node server.js`
将浏览器指向[网页](http://localhost:3000/)
填写并提交表单。 旅程会触发，并会向在表单中输入的电子邮件ID发送电子邮件。


