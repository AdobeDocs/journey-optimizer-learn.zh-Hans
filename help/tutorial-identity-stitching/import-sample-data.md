---
title: 将示例CRM数据导入AEP配置文件数据集
description: 导入样本记录（例如，包含CRMID、电子邮件、收入、邮政编码），以验证AEP能否根据共享标识符（如ECID）将这些用户档案与匿名Web访客正确拼合。
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 4%

---

# 将示例CRM数据导入AEP配置文件数据集

要开始身份拼接，请将示例CRM配置文件数据导入到Adobe Experience Platform中与启用了配置文件的架构绑定的数据集

## 创建自定义命名空间

* 导航到客户 — >身份 — >创建身份命名空间
* 选择单个跨设备ID ，并提供显示名称和标识符号，如下面的屏幕快照所示。
  ![自定义命名空间](assets/custom-namespace.png)

## 创建启用配置文件的架构

创建名为&#x200B;**_FinWiseProfileSchema_**的单个配置文件架构。 包括字段，如annualIncome、email、firstName、lastName和loyaltyStatus。
在SystemIdentifier对象下添加标识字段**_crmid_**。 将crmid字段标记为标识和主字段


![配置文件架构](assets/finwise-profile-schema.png)

## 准备样本数据

| crmId | firstName | 姓氏 | 电子邮件 | loyaltyStatus | 年收入 |
|--------|-----------|----------|---------------------------|---------------|--------------|
| FIN001 | Alice | 黄 | alice.wong@example.com | 金级 | 336104 |
| FIN002 | Brian | Smith | brian.smith@example.com | 银级 | 191065 |
| FIN003 | 凯西 | Johnson | cathy.johnson@example.com | 铜级 | 117015 |
| FIN004 | 大卫 | 李 | david.lee@example.com | 铜级 | 61869 |
| FIN005 | Eva | 马丁内斯 | eva.martinez@example.com | 银级 | 191371 |
| FIN006 | 弗兰克 | 棕色 | frank.brown@example.com | 银级 | 196132 |
| FIN007 | Grace | Kim | grace.kim@example.com | 金级 | 309851 |
| FIN008 | 亨利 | 戴维斯 | henry.davis@example.com | 金级 | 318378 |
| FIN009 | 伊斯拉 | 克拉克 | isla.clark@example.com | 银级 | 181776 |
| FIN010 | Jack | 洛佩斯 | jack.lopez@example.com | 银级 | 186643 |

## 摄取CSV文件

* 根据上一步中创建的&#x200B;**_FinWiseProfileSchema_**，创建名为&#x200B;**_FinWiseCustomerDataSetWithAnnualIncome_**&#x200B;的数据集

* 导航到连接 — >源 — >本地系统
* 在本地文件上传下选择&#x200B;**_添加数据_**。 确保选择&#x200B;_**FinWiseCustomerDataSetWithAnnualIncome**_作为目标数据集。
  ![摄取 — csv](assets/ingest-csv-into-dataset.png)
* 导航到下一个屏幕。 上传[csv文件](assets/sample_crm_data.csv)并验证映射
  ![映射](assets/mappings.png)

* 单击完成以开始数据摄取过程

## 验证配置文件

* 导航至客户 — >用户档案并搜索等于FIN001或任何其他有效值的FinWise CRM ID
  ![验证配置文件](assets/verify-profiles.png)
