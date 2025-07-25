---
title: 创建Adobe Experience Platform标记
description: 根据用户投资偏好创建AJO受众（股票、债券、CD）
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 04fad076-e897-4831-9147-768721858a80
source-git-commit: 40690024e5348dd3ac05f350e49a67a99d5e455e
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# 创建Adobe Experience Platform标记

Adobe Experience Platform Tags(以前称为Adobe Launch)可帮助在您的网站上管理和部署*营销和分析技术，而无需更改网站的代码。

此[视频介绍了创建Adobe Experience Tags的过程](https://experienceleague.adobe.com/en/playlists/experience-platform-get-started-with-tags)

- 登录到数据收集
- 单击&#x200B;_&#x200B;**标记 — >新建属性**&#x200B;_

- 创建名为&#x200B;_&#x200B;**personalization-on-weather**&#x200B;_&#x200B;的Adobe Experience Platform标记。

- 将以下扩展添加到标记
  ![标记 — 扩展](assets/tags-extensions1.png)
- 添加名为“ECID”的数据元素，如下所示。 此数据元素稍后在报表中使用
  ![ecid-data-element](assets/ecid-data-element.png)

- 确保将Adobe Experience Platform Web SDK配置为使用正确的环境以及在前一步中创建的&#x200B;**天气相关数据流**。
  ![web-sdk-configuration](assets/tags-extensions.png)



## 构建和部署AEP标记


创建一个新库并将所有已修改的资源添加到其中，如下面的屏幕截图所示。

**添加库**

![新库](assets/tag-add-library.png)

**创建库**

在“创建库”屏幕中，指定库名称和环境。

将所有已更改的资源添加到此库
![标记库](assets/tag-build-library.png)

然后单击Save and Build to Development按钮以生成库

## 在HTML页面中包含AEP标记

当您发布AEP Tags属性时，Adobe会为您提供一个必须放置在HTML ``` <head>```中或``` <body>```标记底部的脚本标记。

- 转到Tags(Personalization-on-weather)属性。

- 单击环境，然后单击所需环境的安装图标（例如，开发、暂存和生产）。

- 记下嵌入的代码。 在本教程的后期阶段需要使用该功能。
