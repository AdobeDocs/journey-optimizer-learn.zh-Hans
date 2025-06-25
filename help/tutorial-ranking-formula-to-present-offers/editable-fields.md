---
title: 在基于AJO代码的体验中使用可编辑的表单字段
description: 了解如何使用Adobe Journey Optimizer基于代码的体验模板中的内联表单字段创建可编辑的内容块，从而为营销人员提供动态、可重复使用的营销活动内容。
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-22T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18416
exl-id: 0ba695d6-becb-440d-b0d0-de5b51b42562
source-git-commit: 264dde0445306a6d75d8aa4e10459d02e34b2aa8
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 1%

---

# 在基于AJO代码的体验中使用可编辑的表单字段

在许多营销历程（尤其是在受监管的行业）中，包含法律免责声明至关重要，该声明可能因促销活动、地理位置或产品而异。 通过直接在AJO Personalization编辑器中使用[可编辑字段](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences)，营销人员和法律团队可以保持对免责声明文本的完全控制，而无需涉及开发人员或修改决策逻辑。

这样可以实现快速更新，并确保跨营销活动的合规性，同时利用优惠等决策内容。

## 在个性化编辑器中插入可编辑字段

- 打开在之前步骤中创建的营销活动。
- 单击&#x200B;_&#x200B;**修改营销活动**&#x200B;_
- 导航到&#x200B;_&#x200B;**内容**&#x200B;_&#x200B;选项卡
- 单击&#x200B;_&#x200B;**编辑代码**&#x200B;_，并在个性化编辑器中使用以下语法插入一个名为legalDisclaimer的可编辑字段，该字段具有默认值

- &#x200B;
  <pre><code>&#123;&#123;#inline &quot;legalDisclaimer&quot; name=&quot;Legal Disclaimer&quot;&#125;&#125; Legal Disclaimer will go here &#123;&#123;/inline&#125;&#125;</code></pre>

- 使用<code>{{{legalDisclaimer}}}</code> 变量填充模板的位置，如下所示

- ![可编辑的字段](assets/editable-fields.png)

- 营销人员可以轻松编辑法律免责声明字段，而无需打开个性化编辑器。
- ![可编辑的字段营销人员](assets/editable-field-marketer-view.png)



## 发布营销活动

激活营销活动以开始实时提供个性化优惠。
