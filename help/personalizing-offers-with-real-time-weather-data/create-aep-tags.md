---
title: 创建Adobe Experience Platform标记
description: 根据用户投资偏好创建AJO受众（股票、债券、CD）
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 04fad076-e897-4831-9147-768721858a80
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%
---
# 创建Adobe Experience Platform标记

Adobe Experience Platform Tags（以前称为Adobe Launch）可帮助在您的网站上管理和部署*营销和分析技术，而无需更改网站的代码。

此[视频介绍了创建Adobe Experience Tags的过程](https://experienceleague.adobe.com/en/playlists/experience-platform-get-started-with-tags)

* 登录到数据收集
* 单击_**标记 — >新建属性**
* 创建名为&#x200B;_**personalization-on-weather**_&#x200B;的Adobe Experience Platform标记。
* 将以下扩展添加到标记

![标记 — 扩展](assets/tags-extensions1.png)

* 添加名为“ECID”的数据元素，如下所示。 此数据元素稍后在报表中使用

![ecid-data-element](assets/ecid-data-element.png)

* 确保将Adobe Experience Platform Web SDK配置为使用正确的环境以及在前一步中创建的&#x200B;**天气相关数据流**。

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

当您发布AEP Tags属性时，Adobe会为您提供一个必须放置在HTML ` <head>`中或` <body>`标记底部的脚本标记。

1. 转到Tags(Personalization-on-weather)属性。
2. 单击环境，然后单击所需环境的安装图标（例如，开发、暂存和生产）。
3. 记下嵌入的代码。 在本教程的后期阶段需要使用该功能。
