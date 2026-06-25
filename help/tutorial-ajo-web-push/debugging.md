---
title: 在AJO中调试Web推送
description: 本页提供了调试Web推送通知流的有用提示，包括验证Web SDK请求，
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 55cb0875-2953-4d5c-a240-4277aa2f746e
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---

# 在AJO中调试Web推送

本页提供了调试Web推送通知流的有用提示，包括验证Web SDK请求、在AEP中检查ECID和用户配置文件，以及确保正确发送和接收price.drop等事件。

- **使用Adobe Experience Platform Debugger （Chrome扩展）**\
  安装适用于Chrome[&#128279;](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob)的AEP Debugger扩展以更轻松地检查Web SDK活动：

此工具允许您：
 — 查看Web SDK请求和响应\
 — 检查ECID (Experience Cloud ID)\
 — 验证数据流配置和负载

- **检查用户是否已识别(ECID)**\
  使用AEP Debugger或浏览器控制台确认已生成ECID。 此ID用于在AEP和AJO中跟踪用户。

- **使用“网络”选项卡验证请求**\
  在浏览器的开发人员工具中打开&#x200B;**网络选项卡**，并筛选Web SDK发出的请求（查找`/collect`或`interact`）。
   - 确认请求在页面加载和操作触发时发送
   - 检查有效负载中是否包含`price.drop`事件

- **在AEP中查找用户配置文件**\
  使用ECID在Adobe Experience Platform中搜索用户配置文件。 这有助于确认用户已被识别，并且其数据（如推送订阅）存储正确。

- **验证是否收到`price.drop`事件**\
  从网页触发事件后，如果事件被摄取并与同一ECID关联，请签入AEP。
检查`feedback.status`的message.feedback事件的json。状态值应为`sent`
  ![降价](assets/price-drop-profile-event.png)

- **确认已启用推送通知**\
  确保：
   - 用户接受了浏览器通知提示
   - 用户的配置文件中存在推送令牌

- **检查历程设置**\
  确保已发布历程并将其配置为监听`price.drop`事件。
