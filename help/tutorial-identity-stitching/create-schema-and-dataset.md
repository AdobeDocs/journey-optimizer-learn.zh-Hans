---
title: 在AEP中设置XDM架构、数据集和数据流
description: 创建XDM架构、数据集和数据流
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 8bb85ba7-3c50-4596-88f8-e112c48a8253
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
source-wordcount: '299'
ht-degree: 0%
---
# 在AEP中设置XDM架构、数据集和数据流

## 创建XDM架构

要在网页上使用Adobe Experience Platform Web SDK (Alloy.js)，AEP Tags必须与映射到XDM事件架构的数据流关联。 Web SDK (alloy.sendEvent)将数据作为Experience Event发送到AEP，后者必须符合XDM架构（基于XDM ExperienceEvent类）。

创建XDM架构

* 登录到Adobe Experience Platform
* 数据管理 — >架构 — >创建架构

* 创建名为&#x200B;**_财务顾问_**&#x200B;的基于XDM事件的架构。 如果您不熟悉如何创建架构，请按照此[文档](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/tutorials/create-schema-ui)进行操作


* 确保为配置文件启用架构。

## 根据架构创建数据集

Adobe Experience Platform (AEP)**中的**&#x200B;数据集是一个结构化存储容器，用于根据定义的XDM架构摄取、存储和激活数据。


* 数据管理 — >数据集 — >创建数据集
* 根据上一步创建的XDM架构（财务顾问）创建一个名为&#x200B;**_财务顾问数据集_**&#x200B;的数据集。

* 确保为配置文件启用数据集

## 创建数据流

Adobe Experience Platform中的数据流就像一条安全管道（或高速公路），它将您的网站或应用程序连接到Adobe服务，允许数据传入并返回个性化内容。

* 导航到数据收集>数据流，然后单击新建数据流。 命名数据流&#x200B;**_财务顾问数据流_**

* 提供以下详细信息，如下面的屏幕快照所示
  ![数据流](assets/datastream.png)
* 单击保存，然后单击添加映射并添加Adobe Experience Platform服务和事件数据集，如下所示
  ![数据流映射](assets/datastream-service.png)

* 选择相应的事件数据集（之前创建）。

* 保存数据流。
