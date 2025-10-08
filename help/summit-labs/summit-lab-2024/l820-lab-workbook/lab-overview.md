---
title: 实验室工作簿 — L820 — 使用Adobe Journey Optimizer构建个性化的移动时刻
description: 探索各种移动场景，并了解如何使用Journey Optimizer为Web和移动实施个性化体验。
feature: Overview
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
jira: KT-14977
thumbnail: KT-14977.jpeg
last-substantial-update: 2024-03-26T00:00:00Z
exl-id: e6d029f9-c936-427b-9d6e-4e296fd3c3ce
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# 实验室工作簿

![Adobe Summit — 替换文本](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/adobe-summit.png "Adobe Summit")

## L820 — 使用Adobe Journey Optimizer构建个性化的移动时刻

在这个实验操作中，您将探索各种移动场景，并了解如何使用Journey Optimizer为Web和移动实施个性化体验。


>[!IMPORTANT]
>
>请避免在社交媒体上发布会议的任何照片或截图。
>><br>
>>**Adobe机密性**
>>本实验今天分享的信息和产品披露信息是Adobe的机密信息。
>>参与者不得复制、使用、散布或向任何个人或实体披露机密信息。
>>产品披露仅供参考，并不保证任何未来功能或特性，并且随时可能更改。 因此，此类产品特性或功能绝不是您与Adobe之间协议的一部分，也不会以任何方式提供给您。
>><br>
>>**免责声明**
>>Adobe为您提供对各项功能的抢先访问，这些功能利用创新型人工智能技术。 请注意，这些功能仍在开发中，可能会产生意外或不准确的响应。 在将此功能推向市场时，我们欢迎您提供反馈。


### 主要要点

* 了解支持的各种移动体验。
* 配置推送营销活动。
* 了解如何配置移动应用程序内营销活动。
* 设置Web应用程序内消息。
* 测试您自己的个性化方案。

### 先决条件

* 知道您的座位编号：您可以在实验室机器的桌面上找到您的座位编号：

![名额编号](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/locate-seat-number.png)
您需要访问：

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"} — 在练习中提供了登录详细信息。
* [Fréscopa网站](https://dsn.adobe.com/p/adobe-summit-2024?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsImlzc3VlciI6InNoYXJlZC1saW5rIiwiYXJnb24iOnsiYWNjZXNzIjoicmVhZC1wcm9qZWN0IiwicHJvamVjdElkIjoiYWRvYmUtc3VtbWl0LTIwMjQifSwiaWF0IjoxNzEwNTI0MTIwLCJleHAiOjE3MTIzMzg1MjB9.q2uGVst6HjJw8SCWl-3pViNzepkdGnNCvGqZnbbkTsY){target="_blank"}


### 了解用例

Fréscopa是一家富有活力和创新精神的公司，专门通过在其网站和移动应用程序上提供的独一无二的咖啡订阅服务和多种与咖啡相关的产品来彻底改变咖啡的体验。 Fréscopa致力于提供卓越的品质和口味，满足咖啡爱好者对便利和优质选择的需求。

Fréscopa业务的核心在于咖啡订购服务，为客户提供精选的优质咖啡豆，直接送至其门口。 这种个性化的方式确保咖啡爱好者可以享受根据自己的喜好定制的清新而愉快的体验。

作为订阅服务的补充，Fréscopa的网站和移动应用程序提供全面的咖啡相关产品，使客户能够探索和改进他们的咖啡仪式。 从酿酒设备到手工配件，Fréscopa酒店为追求品质和便利的咖啡爱好者提供一站式商店。

Fréscopa对卓越的承诺超越了其产品，因为该公司致力于创造无缝和愉快的客户历程。 创新技术和以客户为中心的途径相结合，使Fréscopa处于不断发展的咖啡行业的前沿。 从本质上说，弗雷斯科帕体现了激情与技术的融合，重新定义了个人体验和享受咖啡的方式。 Fréscopa专注于提供优质、方便和个性化的产品，邀请咖啡爱好者踏上口味之旅，直接送货上门。
