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
exl-id: 609a5ddf-d6c6-4f19-bd7f-bca8c266b759
source-git-commit: 3928a113f74d37b5b9cc2014c526326ef47d4919
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---

# 测试解决方案

要端到端地测试解决方案，请从[weather-offers.zip]中提取weather-offers.html和weather-related-offers-script.js。(assets/weather-offers.zip)这些文件必须托管在Web服务器或公共托管服务（如Github Pages）上。 这是必需的，因为：
 — 浏览器的地理位置API仅适用于HTTPS或本地主机

要使内容保持有序并确保相对路径正常工作，我们建议使用下列文件夹结构来托管解决方案：

![文件夹结构](assets/folder-structure.png)

## 下载提供的文件

从[weather-offers.zip]下载并解压缩HTML和javascript文件。(assets/weather-offers.zip)



## 更新javascript文件中的表面url

打开`weather-related-offers-script.js`并更新` "web://yourdomain.com/weather/weather-offers.html#offerContainer"`bt，将`yourdomain.com`替换为托管HTML文件的实际域。

## 更新Adobe Experience Platform标记属性

在文本编辑器中打开weather-offers.html文件，并将脚本标记替换为在本教程的前面步骤中创建的Adobe Experience Platform标记属性的脚本标记。 确保保存文件

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## 网页的功能

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

* 接收AJO Decisioning返回的优惠。

* 解码HTML内容。

* 将选件动态注入到 <div id="offerContainer"> 元素。

## 后续步骤

[测量和报告AJO Decisioning的影响。](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/experience-decisioning/cja-reporting)

