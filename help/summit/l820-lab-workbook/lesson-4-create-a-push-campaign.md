---
title: 第4课 — 创建推送活动
description: 查看配置文件数据，了解如何在Journey Optimizer中创建推送通知并将其发送给受众。
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
exl-id: 0f82d6a5-18c0-45f2-968e-a678fc2d5768
source-git-commit: befde57252ebc12c5d6df31fde8078e4535d1261
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 2%

---

# 第4课 — 创建推送活动

在上一个练习中，你是一个咖啡爱好者，一个弗雷斯科帕的顾客。 您通过其网站和Fréscopa应用程序与品牌互动，并收到许多事务型消息。 这些消息通过用户与网站或应用程序的交互触发。

在本练习中，您将让营销人员加入并实施Frésopa营销活动，该活动将利用推送渠道来定位Fréscopa应用程序用户。 推送通知用于通知应用程序用户（即使他们未使用应用程序），还可以让他们重新与应用程序互动。 目的是通过提供10%的折扣，鼓励客户购买混合房。

## 学习目标

* 了解如何创建推送营销活动。
* 了解如何设计推送消息。

<br>

## 练习4.1 — 创建推送营销活动

在本练习中，您将创建推送营销活动、设计和自定义推送通知，并将推送通知发送到您自己的设备。

1. 在Journey Optimizer的左侧导航栏中，位于 **[!UICONTROL 历程管理]** 部分，选择 **营销活动**.

1. 单击 **[!UICONTROL 创建营销活动]**.

   ![创建营销活动](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. 在 **[!UICONTROL 创建营销活动]** 页面，在  **[!UICONTROL 操作]** 部分，选择 **[!UICONTROL 推送通知]** 复选框。

1. 从 **[!UICONTROL 应用程序表面]** 下拉列表，选择 *[!DNL Frecopa-Push]*.

1. 单击 **[!UICONTROL 创建]** 以创建推送营销活动。

   ![应用程序表面](/help/summit/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>此时，您应位于Campaign属性页面上：
> ![营销活动属性](/help/summit/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## 练习4.2 — 配置活动

在此页面中，您可以配置营销策划的属性、受众、操作和计划。

### 4.2.1 [!UICONTROL “属性”部分]

为您的营销活动提供一个名称。 请确保以您的座位号作为名称的开头，以便在搜索促销活动时轻松找到它。

例如，如果您的座位号为99： `99 - 10% Discount Campaign`.

### 4.2.2 **[!UICONTROL “受众”部分]**

1. 在受众部分中，单击 **[!UICONTROL 选择受众]**.

   ![受众部分](/help/summit/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. 在 **[!UICONTROL 选择受众]** 屏幕，搜索受众：

   **实验室 — 座位`your seat number`**

1. 选择受众，然后单击 **[!UICONTROL 保存]**.

   ![受众选择](/help/summit/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3编辑推送通知的内容

在本练习中，您将设计和自定义推送通知。

1. 在 **[!UICONTROL 操作]** 部分，单击 **[!UICONTROL 编辑内容] 按钮**.

   ![“编辑内容”按钮](/help/summit/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. 在下一个屏幕上，根据您拥有的移动设备，选择 [!DNL iOS™] 或 [!DNL Android™] 选项卡以配置您的内容。

>[!BEGINTABS]

>[!TAB iOS]

![iOS选项卡](/help/summit/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Android选项卡](/help/summit/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 [!UICONTROL 撰写消息] 部分

1. **撰写消息：** 欢迎您随时添加任何所需的文本。 以下是您可以使用的示例：

   * 标题： `Get 10% off today!`
   * 正文文本： `Today only! Get 10% off on your House Blend coffee purchase!`

     ![撰写消息](/help/summit/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2将消息的单击行为更改为 **打开产品页面**

1. 在 **[!UICONTROL 单击行为]** 部分，选择 **[!UICONTROL 深层链接]** 从 **[!UICONTROL 正文点击行为]** 下拉菜单。

1. 将以下URL复制并粘贴到 **URL字段**：

   `dxdemo://exoticVibes`

   ![深层链接](/help/summit/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3向消息中添加图像

1. 在 **[!UICONTROL 添加媒体]** 部分，单击 **[!UICONTROL 添加媒体]**.

   ![添加媒体按钮](/help/summit/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. 在 **[!UICONTROL 选择资源]** 屏幕在左侧导航中打开 **Fréscopa文件夹** 并从该文件夹中选择图像。

   例如：`HouseBlend.png`

1. 单击图像，然后单击 **[!UICONTROL 选择] 按钮** 以将图像添加到推送通知。

   ![选择图像](/help/summit/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. 在预览屏幕上，单击 **[!UICONTROL 展开视图]**.
   > 1. 预览您的消息。
   > <br>
   >
   > ![展开视图](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

### 红利练习

如果您已完成这部分练习，但仍有一些时间，请尝试使用奖金练习：

+++ 红利练习

#### 通过添加收件人的名字对您发送的邮件进行个性化设置

1. 单击 **个性化对话框** 旁边的 **[!UICONTROL 正文]** 字段。

   ![“个性化”按钮](/help/summit/l820-lab-workbook/assets/2-3-personalization-button.png)

1. 在 **个性化对话框** 屏幕，将光标放在要在文本中添加名字的位置。

1. 确保 **配置文件属性** 将在左侧导航中选择。

   ![配置文件属性](/help/summit/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. 在 **搜索字段**，搜索： `first name`.

1. 单击 **+** 旁边的 **名字（配置文件属性>人员>全名）** 以向文本中添加个性化字段。

   ![搜索名字](/help/summit/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > 您的文本应如下所示：
   > 
   >![个性化令牌](/help/summit/l820-lab-workbook/assets/2-3-personalization-token.png)

1. 单击 **[!UICONTROL 保存]** 以保存个性化。


   >[!SUCCESS]
   >
   > 1. 在预览屏幕上，单击 **[!UICONTROL 展开视图]**.
   > 1. 预览您的消息。
   > 
   > ![展开视图](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4.查看和激活

如果您对消息的内容感到满意，则可以激活消息：

1. 单击 **[!UICONTROL 审查以激活]**.

   ![“查看并激活”按钮](/help/summit/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. 在 **[!UICONTROL 审查以激活]** 屏幕，单击 **[!UICONTROL 激活]**.

   ![审查以激活屏幕](/help/summit/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> 在 **营销活动概述页面**，查找您的营销活动并检查状态。
>
> ![营销活动状态](/help/summit/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> 状态从“正在处理”更改为“实时”，再更改为“已完成” — 这可能需要几分钟的时间。
> 一旦状态更改为“已完成”：
>
> ![推送结果](/help/summit/l820-lab-workbook/assets/2-3-push-notification-result.png)

## 其他资源

**操作方法视频：**

* [配置和发送推送营销活动](/help/channels/create-a-push-campaign.md)

**产品文档：**

* [推送通知入门](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/get-started-push)
* [创建推送通知](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/create-push)
* [设计推送通知](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/design-push)
* [检查并发送推送通知](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/send-push)
