---
title: 第3课 — 创建Web应用程序内营销活动
description: 创建和触发Web应用程序内营销活动。
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-13983
thumbnail: KT-13983.jpeg
exl-id: 0f84adfb-edb1-47fa-b696-58eec2b33bb1
source-git-commit: 4f5c92f79eba3651b3633b7850e993160cb1f72c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# 第3课 — 创建Web应用程序内营销活动

现在，您已为该应用程序创建了移动体验，在本课程中，您将创建在Fréscopa网站上看到的其中一个体验。 您可以创建一个Web应用程序内促销活动。 您可以设计和自定义消息，并定义触发消息的触发器。

## 学习目标

* 了解如何创建Web应用程序内营销活动。
* 触发应用程序内消息。

## 练习3.1创建Web应用程序内营销活动

在本练习中，您将创建营销策划，并定义应用程序内消息出现在哪个网页上。

1. 在Journey Optimizer的左侧导航区域中，在&#x200B;**历程管理**&#x200B;下选择&#x200B;**营销活动**。

1. 单击&#x200B;**创建营销活动**。

   ![创建营销活动](/help/summit/l820-lab-workbook/assets/4-1-create-campaign.png)

1. 在&#x200B;**创建营销活动**&#x200B;页面的&#x200B;**操作**&#x200B;部分中，选中&#x200B;**应用程序内消息**&#x200B;复选框。

1. 从&#x200B;**发送至**&#x200B;下拉列表中，选择&#x200B;**Web.**

1. 输入以下URL： **https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *这是您的邮件将显示的网页。*

   ![应用程序内URL](/help/summit/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. 单击&#x200B;**[!UICONTROL 创建]**。

## 练习3.2配置活动

在此页面上，您可以定义活动的属性以及触发应用程序内消息在网页中显示的事件。 将所有其他设置保留为默认设置。 对于本练习，您无需定义特定受众。

### 3.2.1 [!UICONTROL 属性节]

1. 在&#x200B;**属性**&#x200B;部分中，为营销活动提供一个唯一的&#x200B;**名称**：

   >[!NOTE]
   > 请确保以您的座位号开始命名，这样您就可以
   > 稍后查找您的营销活动。
   > 
   > 例如，如果您的座位号为99： 
   >
   > ![属性名称](/help/summit/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2设置自定义触发器规则

在此部分中，您可以定义消息在网站上显示的触发器。 您可以定义一个唯一触发器，以便仅向自己发送消息。

1. 向下滚动到&#x200B;**[!UICONTROL 触发器部分]**，然后单击&#x200B;**[!UICONTROL 编辑触发器]**。

   ![修改](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. 在规则生成器中，单击&#x200B;**[!UICONTROL 应用程序启动项]**，然后从下拉列表中选择&#x200B;*将数据发送到Platform*。
   ![触发器事件下拉列表](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. 通过单击&#x200B;**[!UICONTROL +添加条件]**&#x200B;添加条件。

   ![添加条件按钮](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. 从&#x200B;**[!UICONTROL 选择特征]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL XDM事件类型]**。

   ![XDM事件类型](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. 在下面的文本字段中，添加一个您可以记住的&#x200B;*`<custom string value>`*，然后按&#x200B;**[!UICONTROL 添加]** `<custom string value>`保存该值。

   此自定义字符串值稍后将用于触发消息。

   >[!TIP]
   > 将您的名额编号添加到自定义字符串值，将使您拥有唯一性且更容易记忆。
   > 
   > 例如：`99web`
   > 

   ![添加自定义触发器字符串值](/help/summit/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. 按右上角的&#x200B;**[!UICONTROL 完成]**&#x200B;按钮。

>[!SUCCESS]
>
>您现在已使用自定义触发器事件定义了Web应用程序内消息。
>
>![定义了自定义触发器的Web营销活动](/help/summit/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3编辑应用程序内消息的内容

在此部分中，您可以定义消息的内容、设计和布局。

1. 单击&#x200B;**操作**&#x200B;部分中的&#x200B;**编辑内容**&#x200B;按钮可访问创作构造。

   ![编辑内容按钮](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. 创作过程与您在上述移动设备应用程序内练习中完成的过程相同。 花些时间自由编辑您自己的标题、正文和媒体内容的消息。

   如果使用模态布局或全屏布局，则可以添加按钮。 您可以使用此URL打开产品页面： **https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. 编辑完邮件后，单击&#x200B;**[!UICONTROL 查看以激活]**。

1. 如果评论屏幕上一切正常，请单击&#x200B;**[!UICONTROL 激活]**&#x200B;以发布您的Web应用程序内消息。

1. 您将返回到Campaign信息板。

   等待单元：您的营销活动状态更改为&#x200B;**实时**，然后再更改为4.1.4。

## 练习3.3触发Web应用程序内消息

1. 转到Fréscopa网站，然后导航到浏览器上的&#x200B;**练习**&#x200B;页面。

   ![Web练习链接](/help/summit/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. 确保刷新网页。

1. 键入您在营销活动中定义的唯一字符串值。

   ![练习页面](/help/summit/l820-lab-workbook/assets/4-2-exercise-page.png)

1. 单击&#x200B;**[!UICONTROL 发送]**。

>[!SUCCESS]
>
>单击具有唯一值的发送按钮将触发您的Web应用程序内消息。 您应该会在屏幕上看到您的Web应用程序内消息。
>
>此练习模拟了一个自定义XDM发送事件，您通过Fréscopa客户体验看到了该事件。


## 其他资源

**操作方法视频：**

* [创建应用程序内营销活动](/help/channels/create-an-in-app-campaign.md)
* [创建应用程序内消息](/help/channels/author-in-app-messages.md)

**产品文档：**

* [开始使用应用程序内频道](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/in-app/get-started-in-app)
* [创建Web应用程序内消息](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/in-app/create-in-app-web)
* [设计应用程序内内容](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/in-app/design-in-app)
* [检查并发送应用程序内通知](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/in-app/send-in-app)
