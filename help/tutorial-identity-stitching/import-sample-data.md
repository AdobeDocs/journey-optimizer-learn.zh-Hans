---
title: 将示例CRM数据导入AEP配置文件数据集
description: 导入样本记录（例如，包含CRMID、电子邮件、收入、邮政编码），以验证AEP能否根据共享标识符（如ECID）将这些用户档案与匿名Web访客正确拼合。
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 33c8c386-f417-45a8-83cf-7312d415b47a
source-git-commit: 83b23f54594b796ec528526a360c5c40164fb5cb
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 5%

---

# 将示例CRM数据导入AEP配置文件数据集

要开始身份拼接，请将示例CRM配置文件数据导入到Adobe Experience Platform中与启用了配置文件的架构绑定的数据集

## 创建自定义命名空间

* 导航到客户 — >身份 — >创建身份命名空间
* 选择单个跨设备ID ，并提供显示名称和标识符号，如下面的屏幕快照所示。
  ![自定义命名空间](assets/custom-namespace.png)

## 创建启用配置文件的架构

创建名为&#x200B;**_FinWiseProfileSchema_**的单个配置文件架构。 包括字段，如annualIncome、email、firstName、lastName和loyaltyStatus。
添加标识字段**_crmid_**，如图所示。 将crmid字段标记为标识和主字段。
将_**同意和偏好设置详细信息**_&#x200B;字段组添加到架构。 [同意和偏好设置](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/field-groups/profile/consents)是XDM Individual Profile类的标准字段组，用于捕获单个客户的同意和偏好设置信息。此处存储的偏好设置决定渠道级别的通信偏好设置。


![配置文件架构](assets/finwise-profile-schema.png)

## 准备样本数据

将虚拟电子邮件地址更新为真实地址。 稍后在通过Adobe Journey Optimizer发送消息时将使用这些变量。 将emailConsent设置为y可启用用户档案的电子邮件投放。

|   | crmId | firstName | 姓氏 | 电子邮件 | loyaltyStatus | zipCode | 年收入 | emailConsent |
|---|--------|-----------|----------|-------------------------|---------------|---------|--------------|--------------|
|   | FIN001 | Alice | 黄 | alice.wong@example.com | 金级 | 92128 | 120000 | y |
|   | FIN002 | Bob | Smith | bob.smith@example.com | 银级 | 92126 | 85000 | y |
|   | FIN003 | 查理 | Kim | charlie.kim@example.com | 白金 | 60614 | 175000 | y |
|   | FIN004 | Diana | 李 | diana.lee@example.com | 金级 | 30303 | 98000 | y |
|   | FIN005 | Ethan | 棕色 | ethan.brown@example.com | 铜级 | 75201 | 60000 | y |

## 摄取CSV文件

* 根据上一步中创建的&#x200B;**_FinWiseProfileSchema_**，创建名为&#x200B;**_FinWiseCustomerDataSetWithAnnualIncome_**&#x200B;的数据集

* 导航到连接 — >源 — >本地系统
* 在本地文件上传下选择&#x200B;**_添加数据_**。 确保选择&#x200B;_**FinWiseCustomerDataSetWithAnnualIncome**_作为目标数据集。
  ![摄取 — csv](assets/ingest-csv-into-dataset.png)
* 导航到下一个屏幕。 上传[csv文件](assets/finwise_profiles.csv)并验证映射
  ![映射](assets/mappings.png)

* 单击完成以开始数据摄取过程

## 验证配置文件

* 导航至客户 — >用户档案并搜索等于FIN001或任何其他有效值的FinWise CRM ID
  ![验证配置文件](assets/verify-profiles.png)
