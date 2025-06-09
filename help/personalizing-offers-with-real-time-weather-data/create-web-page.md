---
title: 测试解决方案
description: 创建一个简单的网页，以使用实时温度数据测试上下文选件个性化。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: a9fc14da78e1c67b01aef5dcdd417ce02d36d50a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# 测试解决方案

构建了一个网页，以使用实时温度数据测试上下文选件个性化。 当用户访问页面时，浏览器会提示用户访问地理位置。 获得批准后，页面将通过OpenWeatherMap API获取当前天气详细信息，例如温度、条件和城市。 此上下文数据会向用户显示，并使用Adobe Web SDK (Alloy)发送到Adobe Experience Platform。

sendEvent调用使用renderDecisions： false进行配置，这意味着手动处理Adobe Journey Optimizer返回的选件。 该脚本会处理决策响应、解码内容并将最相关的选件动态插入指定容器(#offerContainer)中。

## JavaScript的功能

JavaScript会根据用户的位置动态获取天气信息，并使用Adobe Experience Platform (AEP)来提供个性化优惠。 以下是步骤的细目：

1. **等待加载Alloy**

   该脚本可确保在发出任何个性化请求之前完全加载Adobe Web SDK (Alloy)。

2. **获取用户的位置**

   它使用浏览器的地理位置API检索用户当前的纬度和经度。

3. **获取天气数据**

   它调用OpenWeatherMap API以获取当前天气详细信息：

   温度（以°F为单位）

   天气条件（例如，“下雨”、“晴”）

   城市名称

   湿度

4. **在网页上显示天气信息**

   使用如下消息更新DOM：

   “圣地亚哥目前的气温是华氏72度，晴空万里。”

5. **将天气上下文发送到AEP**

   使用alloy(&quot;sendEvent&quot;)将上下文天气数据发送到AEP

   ```javascript
   xdm: {
   eventType: "decisioning.request",
   _techmarketingdemos: {
   temperature: temp,
   weatherConditions: condition,
   cityName: city
     }
   }
   ```

6. **检索并渲染选件**

   接收AJO返回的优惠。

   解码HTML内容。

   将选件动态注入到 <div id="offerContainer"> 元素。

7. **示例Assets**

   用于测试解决方案的网页可供下载

[网页](assets/weather-offers.html)

[JavaScript 代码](assets/weather-related-offers-script.js)

