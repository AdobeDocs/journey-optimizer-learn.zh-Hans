---
title: 测试解决方案
description: 创建简单网页以捕获优惠上的展示和点击事件。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18526
source-git-commit: 69bc8aace3cc502a18e691584824176833413c7e
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# 测试解决方案

要端到端地测试解决方案，[weather-offers.html](assets/weather-offers.html)和[capture-impressions-click-events.js](assets/capture-impressions-click-events.js)文件必须托管在Web服务器或公共托管服务（如Github Pages）上。 这是必需的，因为浏览器的地理位置API只能通过HTTPS或本地主机工作

## 下载提供的文件

[HTML文件](assets/weather-offers.html)

[Javascript文件](assets/capture-impressions-click-events.js)

## 更新javascript文件中的表面url

打开`capture-impressions-click-events.js`并通过将` "web://yourdomain.com/weather/weather-offers.html#offerContainer"`替换为托管HTML文件的实际域来更新`yourdomain.com`。


## 更新Adobe Experience Platform标记属性

在文本编辑器中打开weather-offers.html文件，并将脚本标记替换为在本教程的前面步骤中创建的Adobe Experience Platform标记属性的脚本标记。 确保保存文件

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## 与选件交互

- 在您最喜爱的浏览器中打开网页。

- 允许&#x200B;_&#x200B;**位置跟踪**&#x200B;_。 要根据您的位置获取天气详细信息，需要此项。

- 单击选件中的按钮以触发交互事件。

## 查看报告

- 登录Journey Optimizer

- 导航到“历程管理” — >“促销活动”

- 单击该营销策划，然后从报表菜单中选择相应的报表。
