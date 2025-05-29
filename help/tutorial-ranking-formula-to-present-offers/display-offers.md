---
title: 创建网页以测试解决方案
description: 用于测试使用决策提供的个性化优惠的网页。
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-31T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---


# 创建网页以测试解决方案

此示例应用程序模拟了一个真实登录流程，在将CRM ID发送到Adobe Experience Platform (AEP)之前，将在服务器端验证用户凭据。 本地Node.js服务器用于安全地提供网页、处理基本身份验证逻辑以及避免可能会妨碍Adobe Launch或Web SDK功能的浏览器限制（例如阻止本地文件访问或缺少CORS标头）。 这种设置可确保体验更接近真实的生产环境。

个性化优惠仅在用户登录后显示，此时用户的CRM ID和ECID (Experience Cloud ID)之间的身份拼接已完成。 此身份拼接可确保Adobe Journey Optimizer (AJO)能够准确识别用户档案并返回目标选件。

成功登录后，个性化请求将发送到AJO以检索用户的可用选件。 这些优惠将作为HTML片段返回，每个片段嵌入了一个数据标记属性，例如data-tags=&quot;ajo offer-vacation-based-cd zip-92128 income-high&quot;，其中包括优惠名称和分段详细信息，如邮政编码和收入级别。

然后，JavaScript解析这些HTML块，并将每个块包装在轮播项目容器中。 这些项目在轮播轨道中水平排列，从而能够进行可滑动导航。 上一个和下一个按钮（◀和▶）允许用户一次翻阅一个个性化优惠。

这种设置提供了响应式且量身定制的体验，确保每位用户都能够看到与其财务资料相关的选件 — 仅在他们的身份已跨平台安全拼接后才可看到。

## 测试此解决方案

* 在现有Node.js项目内创建一个名为ranking-formula的文件夹。

* 将[提供的文件解压缩到此排名公式文件夹中。](assets/ranking-formula.zip)

* 导航到文件夹并启动服务器以运行应用程序：
   * `cd ranking-formula`

   * `node server.js`


* 打开浏览器，然后转到http://localhost:3000/formula.html。

* 使用alice/pass123登录

由于Alice位于92128邮政编码中，因此将显示针对该位置定制的优惠。