---
title: 在AEP中设置XDM架构、数据集和数据流
description: 创建XDM架构、数据集和数据流
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 1c7fe9e7-ab72-4d7b-960a-512d0e25808b
source-git-commit: 95a8abd08fbf57900870826112b01a8cd375fe96
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# 在AEP中设置XDM架构、数据集和数据流

## 创建XDM架构

要在网页上使用Adobe Experience Platform Web SDK (Alloy.js)，AEP Tags必须与映射到XDM事件架构的数据流关联。 Web SDK (alloy.sendEvent)将数据作为Experience Event发送到AEP，后者必须符合XDM架构（基于XDM ExperienceEvent类）。

创建XDM架构

- 登录到Adobe Experience Platform
- 导航到&#x200B;_**数据管理 — >架构 — >创建架构**_

- 创建名为&#x200B;**_Weather-Schema_**&#x200B;的基于XDM事件的架构。 如果您不熟悉如何创建架构，请按照此[文档](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)进行操作


- 确保架构具有以下具有相应数据类型的字段。

- ![天气模式](assets/weather-schema.png)

- 将字段组&#x200B;_**Web详细信息**_&#x200B;添加到架构。 此字段组是报告所必需的。

## 根据架构创建数据集

Adobe Experience Platform (AEP)**中的**&#x200B;数据集是一个结构化存储容器，用于根据定义的XDM架构摄取、存储和激活数据。

- 导航到&#x200B;_**数据管理 — >数据集 — >创建数据集**_
- 根据上一步创建的XDM架构（**_天气架构_**）创建名为&#x200B;_**天气架构数据集**_&#x200B;的数据集。


## 创建数据流

Adobe Experience Platform中的数据流就像一条安全管道（或高速公路），它将您的网站或应用程序连接到Adobe服务，允许数据传入并返回个性化内容。

- 导航到&#x200B;_**数据收集>数据流**_，然后单击“新建数据流”。 命名数据流&#x200B;**天气相关数据流**


- 提供以下详细信息，如下面的屏幕快照所示
  ![数据流](assets/datastream.png)
- 单击保存，然后单击添加映射并添加Adobe Experience Platform服务和事件数据集，并选中相应的复选框
  ![数据流映射](assets/datastream-service.png)

- 保存数据流。
