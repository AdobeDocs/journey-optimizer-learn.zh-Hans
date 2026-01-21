---
title: 测试解决方案
description: 创建简单网页以捕获优惠上的展示和点击事件。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18526
exl-id: 6b6c66d3-218d-4f5b-adb0-a2eca05989ab
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 0%

---

# 测试解决方案

## 部署示例资源

如果未安装Node.js，请从此处[下载并](https://nodejs.org/)安装它

通过运行以下命令来验证安装：

`node -v`

`npm -v`

## 设置项目文件夹

使用以下命令为示例应用程序创建新目录：

`mkdir frequency-capping `

`cd frequency-capping `

## 初始化项目

`npm init -y`

## 安装所需的框架

`npm install express`

## 复制资源文件

* 解压缩[server.zip](assets/server.zip)的内容，并将其放在`frequency-capping`文件夹中。
* 将[public.zip](assets/public.zip)的内容提取到“frequency-capping”文件夹中

## 更新javascript文件中的表面url

打开位于`frequency-capping.js`中的`public\scripts`并更新表面属性以匹配营销活动中使用的渠道配置

## 启动节点js服务器

导航到`c:\frequency-capping`文件夹。 执行`node server.js`命令以启动端口3000上的节点js服务器


## 更新Adobe Experience Platform标记属性

在文本编辑器中打开位于`frequency-capping.html`文件夹中的`public`文件，并将脚本标记替换为在本教程的前一步中创建的Adobe Experience Platform标记属性的脚本标记。 确保保存文件

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## 与选件交互

* 在您最喜爱的浏览器中打开[网页](http://localhost:3000)。
* 与选件交互
* 刷新页面
* 根据频率封顶规则，您应该会看到一个新选件

## 查看报告

* 登录Journey Optimizer
* 导航到“历程管理” — >“促销活动”
* 单击该营销策划，然后从报表菜单中选择相应的报表。
