---
title: 在AEP中设置XDM架构、数据集、数据流和受众
description: 创建XDM架构、数据集、数据流和受众
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---


# 在AEP中设置XDM架构、数据集、数据流和受众

* 登录到Adobe Experience Platform

* 在Journey Optimizer中创建一个名为财务顾问的基于XDM事件的架构。 如果您不熟悉如何创建架构，请按照此[文档](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)进行操作

* 将以下结构添加到架构中。 PreferredFinancialInstrument元素存储用户对股票、债券、CD的偏好
  ![xdm-schema](assets/xdm-schema.png)

* PreferredFinancialInstrument元素具有如下定义的枚举值
  ![枚举值](assets/enum-values.png)

* 确保为配置文件启用架构。

## 根据架构创建数据集

Adobe Experience Platform (AEP)**中的**&#x200B;数据集是一个结构化存储容器，用于根据定义的XDM架构摄取、存储和激活数据。

* 根据上一步创建的XDM架构（财务顾问）创建一个名为&#x200B;_财务顾问数据集_&#x200B;的数据集。

* 确保为配置文件启用数据集

## 创建数据流

Adobe Experience Platform中的数据流就像一条安全管道（或高速公路），它将您的网站或应用程序连接到Adobe服务，允许数据传入并返回个性化内容。

* 转到AEP >数据流，然后单击新建数据流。 命名数据流&#x200B;_财务顾问数据流_

* 提供以下详细信息，如下面的屏幕快照所示
  ![数据流](assets/datastream.png)
* 单击保存，然后单击添加映射并添加Adobe Experience Platform服务和事件数据集，如下所示
  ![数据流映射](assets/datastream-service.png)

* 选择相应的事件数据集（之前创建）。

* 保存数据流

## 创建受众

Adobe Experience Platform中的受众是指根据用户的操作、偏好或配置文件信息创建的用户组，用于提供个性化体验。

* 导航到客户 — >受众
* 使用构建规则方法创建受众

* 使用事件架构中的PreferredFinancialInstrument元素在AJO中创建以下3个受众。

   * 对股票感兴趣的客户

   * 对债券感兴趣的客户

   * 对CD感兴趣的客户

确保将每个受众的评估方法设置为Edge以进行实时资格鉴定。

以下屏幕截图应有助于您创建受众。

![受众](assets/rule-based-audience.png)

![事件](assets/event-attribute.png)


![首选金融工具](assets/stock-customers.png)

![边缘受众](assets/audience-edge.png)