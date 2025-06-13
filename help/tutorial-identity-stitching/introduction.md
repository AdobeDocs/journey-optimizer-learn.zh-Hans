---
title: AEP中的身份拼合
description: 在已知用户(CRMID)和匿名Web访客(ECID)之间建立身份拼接，从而在Adobe Journey Optimizer (AJO)中实现统一的用户档案以实现实时个性化和优惠决策。
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
exl-id: d6a1201a-3779-4718-8ea8-b88f925f53b6
source-git-commit: 96d9d525a3d9be399f7fa229b67166acf8130721
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# 用例描述

在现代客户体验中，跨设备和渠道统一用户身份至关重要。 此用例演示了如何在Adobe Experience Platform (AEP)中实施身份拼接，方法是将已知CRM ID（在用户登录期间捕获）与Adobe Web SDK生成的匿名Experience Cloud ID (ECID)关联。 通过实时将这些身份拼合在一起，AEP可以构建更加完整的客户档案，该档案跨越匿名行为和经过身份验证的数据。 这可以在Adobe Journey Optimizer (AJO)等工具中实现更准确的受众分段、个性化和决策。

## 身份拼接教程需要🧠技能

为了充分利用本教程，建议熟悉以下内容：

- **Adobe Experience Platform (AEP)核心概念**\
  了解架构、数据集、身份、合并策略和实时配置文件。

- **架构和身份建模**\
  能够在基于配置文件和基于事件的架构中配置身份字段。

- **Adobe Launch （标记）和Web SDK (Alloy.js)**\
  具有使用Web SDK设置数据元素和规则以将数据发送到AEP的经验。

- **JavaScript基础知识**\
  熟悉使用函数来捕获用户输入、触发事件和调试API调用。

- **AEP调试工具**\
  能够使用AEP Debugger和Identity Graph Viewer验证身份拼合。

- AEP中的&#x200B;**数据摄取**\
  熟悉如何将样本数据上传到数据集并确保数据质量。


