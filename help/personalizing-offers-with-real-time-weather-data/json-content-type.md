---
title: 在Adobe Journey Optimizer中交付包含JSON内容的Personalization
description: 利用Adobe Journey Optimizer (AJO)中的JSON内容类型构建灵活的数据驱动型个性化体验。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-18T00:00:00Z
jira: KT-18387
recommendations: noDisplay, noCatalog
source-git-commit: 9f5b52063605832a9b00c05fb1a93bf60ec7686f
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# 在Adobe Journey Optimizer中交付包含JSON内容的Personalization

此部分作为附加资源提供，供希望更好地控制选件在前端呈现方式的高级用户使用。

在基于代码的体验(CBE)中使用JSON内容类型可让您返回结构化选件数据，并使用JavaScript动态处理渲染。 JSON内容类型对于需要自定义布局、条件逻辑或与上下文数据（如天气、位置或设备类型）集成的场景特别有用。

虽然基本选件交付不需要此方法，但这种方法为开发人员提供了灵活性，让他们可以构建超出标准HTML渲染功能的个性化数据驱动体验。

## 创建具有JSON内容类型的基于代码的体验(CBE)。

首先，在Adobe Journey Optimizer中创建一个新的基于代码的体验(CBE)，并将内容格式设置为JSON。 内容类型告知AJO将结构化选件数据（如offerText、图像或元数据）作为JSON对象返回而不是渲染的HTML。 定义平台（例如Web）、显示选件的目标URL以及页面上的位置（例如像offerContainer这样的容器ID）。 此配置使您的Web应用程序能够接收选件数据，并使用JavaScript动态呈现该数据。

![json-content-type](assets/cbe-json-content.png)

## 将CBE与活动关联到决策策略

创建具有JSON内容类型的基于代码的体验(CBE)后，它将通过决策策略链接到营销活动。 决策策略根据用户档案或上下文数据定义优惠资格、排名和投放的逻辑。

将决策策略插入Personalization编辑器时（例如，对于应用程序内消息或电子邮件），请务必确保输出保持有效的JSON结构。

将决策策略插入营销活动的Personalization编辑器(PE)时，Adobe Journey Optimizer会根据所选策略自动生成Handlebars循环。 例如：
![默认代码](assets/handlebar-code-default.png)
此循环循环循环遍历策略返回的所有决策项目，并从每个选件中注入offerText字段。 此默认结构非常适用于HTML内容类型，但在使用JSON内容时，可能需要重新构建才能生成有效的JSON数组或对象，尤其是在以编程方式解析结果的情况下。

![重构代码](assets/restructured-code.png)

此Handlebars模板旨在输出选件对象的JSON数组，其中每个对象都包含单个offerText字段。 它循环执行指定的决策策略返回的决策项，并以JSON对象格式封装每个offerText。

## 解析JSON选件响应

来自AJO的响应在`propositions[].items[].data.content[]`结构下包含JSON格式的个性化决策项。 每个内容项都包含offerText等字段。

```javascript
(response.propositions || []).forEach(p => {
  (p.items || []).forEach(item => {
    const contents = item.data?.content || [];
    contents.forEach(contentItem => {
      const html = contentItem.offerText || "";
      const wrapper = document.createElement("div");
      wrapper.className = "offer";
      wrapper.innerHTML = html;
      document.getElementById("offerContainer").appendChild(wrapper);
    });
  });
});
```

### 示例资源

为了帮助您入门，请下载示例HTML文件和JavaScript文件，其中演示了如何使用基于JSON的选件并在您的网页上动态呈现它们。

[JavaScript代码](assets/weather-related-offers-script-multiple-json.js)
[HTML文件](assets/multiple-json.html)