---
title: AEP中的身份拼合
description: 在已知用户(CRMID)和匿名Web访客(ECID)之间建立身份拼接，从而在Adobe Journey Optimizer (AJO)中实现统一的用户档案以实现实时个性化和优惠决策。
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# 用例描述

在现代客户体验中，跨设备和渠道统一用户身份至关重要。 此用例演示了如何在Adobe Experience Platform (AEP)中实施身份拼接，方法是将已知CRM ID（在用户登录期间捕获）与Adobe Web SDK生成的匿名Experience Cloud ID (ECID)关联。 通过实时将这些身份拼合在一起，AEP可以构建更加完整的客户档案，该档案跨越匿名行为和经过身份验证的数据。 这可以在Adobe Journey Optimizer (AJO)等工具中实现更准确的受众分段、个性化和决策。

