---
title: 第2课 — 创建移动应用程序内促销活动
description: 创建和触发移动设备应用程序内促销活动。
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14983
thumbnail: KT-14983.jpeg
exl-id: fe18eca7-229c-4867-ab34-1862bad63124
source-git-commit: 4f5c92f79eba3651b3633b7850e993160cb1f72c
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 1%

---

# 第2课 — 创建移动应用程序内促销活动

在本课程中，您将创建并触发移动设备应用程序内消息。

## 学习目标

* 了解如何触发应用程序内消息。
* 了解如何创建移动应用程序内促销活动。
* 触发应用程序内消息。

## 练习2.1 — 登录到Journey Optimizer

1. 打开 [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}
2. 使用以下详细信息登录：
   <br>
   **用户名：** L820+**`<your seat number>`**@adobeeventlab.com
   **密码：**   Adobe2024！
   <br>
您可以在实验室计算机桌面上找到登录的详细信息。 使用Adobe ID和密码。
   ![桌面](/help/summit/l820-lab-workbook/assets/desk-top.png)

   ![“登录”屏幕](/help/summit/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. 您可以跳过以下两个屏幕：
   <br>
   ![电话号码](/help/summit/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![个性化弹出窗口](/help/summit/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>您应该登录到Journey Optimizer并在主页上：
>
>![AJO主页](/help/summit/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## 练习2.2创建移动应用程序内促销活动

在本练习中，您将创建一个应用程序内消息传送促销活动，此活动将在您打开应用程序时触发。

1. 在Journey Optimizer的左侧导航区域中，选择 **[!UICONTROL 营销活动]**.

1. 单击 **[!UICONTROL 创建营销活动]**.

   ![创建营销活动](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. 在 **[!UICONTROL 创建营销活动]** 页面，在  **[!UICONTROL 操作]** 部分，选择 **[!UICONTROL 应用程序内消息]** 复选框。

1. 从 **[!UICONTROL 发送至]** 下拉列表，选择 **[!DNL Mobile]**.

1. 从 **[!UICONTROL 应用程序表面]** 下拉列表，选择 **[!DNL Frecopa Mobile App]**.

1. 单击&#x200B;**[!UICONTROL 创建]**。

   ![应用程序表面](/help/summit/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>现在，您应该位于Campaign属性上：
>
> ![营销活动属性](/help/summit/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## 练习2.3配置活动

### 2.3.1 [!UICONTROL “属性”部分]

为您的营销活动提供一个名称。 请确保以您的座位号开始命名，以便您能够轻松地再次找到您的促销活动。

例如，如果您的座位号为99：  `99 - Welcome Campaign`.

![属性部分](/help/summit/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2设置自定义触发器规则

1. 向下滚动到 **[!UICONTROL “触发器”部分]**，然后单击 **[!UICONTROL 编辑触发器]**.

   ![修改](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. 在规则生成器中，单击 **[!UICONTROL 应用程序启动]** 并从下拉列表中选择  *将数据发送到Platform*.
   ![已发送到数据平台](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. 通过单击添加条件 **[!UICONTROL 添加条件]**.

   ![添加条件按钮](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. 从 **[!UICONTROL 选择特征]** 下拉列表，选择 **[!UICONTROL XDM事件类型]**.

   ![XDM事件类型](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. 在以下文本字段中，添加 *`<custom string value>`* 你记得的。

1. 要保存该值，请单击**[!UICONTROL 添加**] `<custom string value>`.

   此自定义字符串值稍后将用于触发消息。

   >[!TIP]
   > 将您的名额编号添加到自定义字符串值中会使您拥有唯一性且更易于记忆。
   > 
   > 例如：`99exerciseTrigger`

   ![添加自定义触发字符串值](/help/summit/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. 单击 **[!UICONTROL 完成]** 在右上角。

>[!SUCCESS]
>
>现在，您已使用自定义触发器事件定义应用程序内消息。
>
>![定义了自定义触发器的营销活动](/help/summit/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3编辑应用程序内消息的内容

在 **[!UICONTROL 操作]** 部分，单击 **[!UICONTROL 编辑内容]**.

![“编辑内容”按钮](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

此 [!UICONTROL 应用程序内消息] 此时将显示编辑器，您可以在其中配置应用程序内消息内容。

#### 2.3.3.1布局

选择应用于消息的布局。

例如，单击 **[!UICONTROL 模态]** 将应用程序内消息设置为模态布局。

![模式按钮](/help/summit/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2创作消息并发布营销活动

1. 在媒体部分中，粘贴以下URL：  `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
当您单击退出值字段时，您的图像应会显示。

   ![预览中显示的媒体](/help/summit/l820-lab-workbook/assets/3-1-3-2-media.png)

2. 在以下内容中 **[!UICONTROL 内容]** 部分，添加您自己的自定义文本，以便 **[!UICONTROL 页眉]** 和 **[!UICONTROL 正文]**.

   ![页眉和正文](/help/summit/l820-lab-workbook/assets/3-1-3-2-content.png)

3. 其他选项：
   1. **按钮：**

      ![按钮部分](/help/summit/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. 在编辑器的此部分中，您可以通过编辑按钮文本字段自定义CTA按钮的文本。

      2. 此 **[!UICONTROL Interact事件]** 字段用于定义当用户按下CTA时传递到SDK的值。

      3. 此 **[!UICONTROL Target]** 字段用于定义您希望CTA将用户带到的位置。 这包括URL和深层链接。 例如，您可以将此深层链接添加到产品页面，例如 `dxdemo://exoticVibes`.

      4. 您可以通过按添加其他按钮 **[!UICONTROL +添加按钮]**.

      5. 当消息中添加了第二个按钮时，您现在可以选择使用下拉框更改按钮布局。


   2. **高级格式化**

      ![高级格式切换](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      启用此切换将在编辑器中提供其他自定义选项。

      1. 媒体大小
      1. 字体
      1. Pt大小
      1. 字体颜色
      1. 对齐方式

      ![高级格式选项](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **“设置”选项卡**

      通过切换到此选项卡并在 **[!UICONTROL 预览]** 部分，您可以更改 **应用程序预览**.
      <br>\
      ![“设置”选项卡](/help/summit/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. 此 **[!UICONTROL 布局]** 部分为您提供了将图像用作背景或纯色的选项。

      2. 此 **[!UICONTROL 消息]** 部分提供了可以为消息启用的自定义交互：
         1. 自定义手势
         2. UI接管
         3. 自定义UI接管
         4. 自定义大小
         5. 自定义位置
         6. 自定义动画
         7. 消息转角
   <br>
4. 当您完成内容创作并对消息感到满意时，请单击 **[!UICONTROL 审查以激活] 按钮**.

   >[!SUCCESS]
   >
   > 您现在已完成移动设备应用程序内消息的创作。 您现在应该加入促销活动 **[!UICONTROL 审查以激活]** 页面。
   >
   >![查看和激活](/help/summit/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > 您将在此处看到消息的完整摘要。
   >
   > *请记下您用作触发规则的自定义值。 此值将用于触发您的应用程序内消息。 可在摘要页面的高亮区域找到使用的值。*

   >[!NOTE]
   >应用程序内消息的当前触发器为默认设置 **发生应用程序启动事件**，这表示应用程序启动时会触发应用程序内消息。 您可以在 **[!UICONTROL “计划”部分]**.

5. 如果您已完成审阅营销活动，请按激活按钮发布营销活动。
   <br>
   ![激活](/help/summit/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> 您现在应该会看到营销活动仪表板。 通过滚动或使用搜索功能找到您的营销策划。 当您的营销活动将状态更改为 **[!UICONTROL 实时]** （~1分钟），您的营销活动现已发布。
>
> ![已发布的营销活动](/help/summit/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## 练习2.4触发移动设备应用程序内消息

要刷新有效负载并下载新发布的营销活动，请执行以下操作：

1. 在移动设备上，完全关闭Fréscopa应用程序。
2. 重新打开Fréscopa应用程序。
3. 现在，导航到应用程序上的练习选项卡。

   ![练习按钮](/help/summit/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. 在文本字段中，键入您在Campaign中定义的自定义触发器值。 然后按提交。


   ![修改](/help/summit/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>通过单击提交，您可以手动触发触发器，此时您创建的应用程序内通知会弹出：
>
>![应用程序内消息](/help/summit/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *如果在触发消息时遇到问题，请检查以下各项：*
> 
> * *在移动设备应用程序上的事件名称字段中，确保键入的触发器规则值与Campaign中的相应值完全相同。*
> * *确保大小写正确，并且没有前导或结尾空格。*
> * *如果通过单击返回营销活动仪表板上的营销活动，以返回营销活动审核页面，则可以查找您使用的触发规则值。*

您刚刚创作并发布了您的首条Journey Optimizer应用程序内消息！


## 附加练习：在设备上复制活动和预览

此 **复制营销活动** 和 **在设备上预览** 这些功能均为现成可用功能，可让您在激活营销活动之前，直接在设备上测试和查看应用程序内消息。 在本练习中，您将学习如何使用此功能并预览您在练习3.1中创建的消息。

1. 通过单击“营销活动”仪表板页面中的营销活动名称以打开您刚刚创建的营销活动。 这会将您带回 **[!UICONTROL 审核营销活动]** 页面。
1. 按 **[!UICONTROL “复制”按钮]**. 这将打开一个新提示，为您正在复制的新营销活动命名。 添加您容易记住或使用默认名称的新名称，其中 **[!DNL _copy]** 默认添加。

   ![复制营销活动](/help/summit/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. 点击复制按钮后，将会创建您的重复营销活动，并且您会返回到营销活动仪表板。
1. 复制营销活动后，打开您的新营销活动。

1. 您可以在以下位置访问在设备上预览功能： **[!UICONTROL 营销活动审核]** 页面或 **[!UICONTROL 营销活动作者]** 步骤。

   ![“在设备上预览”按钮](/help/summit/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. 接下来，单击 **[!UICONTROL “开始”按钮]** 从“连接到设备”屏幕。

   ![“开始”按钮](/help/summit/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. 输入已配置为启动Fréscopa应用程序的基本URL： `dxdemo://`

   ![预览url](/help/summit/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. 按照屏幕上的说明操作：
   1. 使用移动设备扫描二维码，此时会打开Fréscopa应用程序，并显示一个允许您输入所显示图钉的屏幕。
   2. 在设备的Assurance屏幕上，输入AJO中显示的pin，然后单击右下角的Connect （连接）按钮，输入pin后即会显示。


   ![输入pin](/help/summit/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. 此弹出窗口显示在计算机屏幕上

   ![弹出窗口](/help/summit/l820-lab-workbook/assets/3-3-pop-up.png)

1. 单击“Done（完成）”按钮。 这将关闭对话框，您的手机现在已连接到设备上的“预览”功能。


>[!SUCCESS]
>
> 您的应用程序内消息会显示在您的设备上。
>
> *连接后，每次都应显示您的应用程序内消息，单击 **[!UICONTROL 在设备上预览] 按钮**.

## 其他资源

**操作方法视频：**

* [创建应用程序内营销活动](/help/channels/create-an-in-app-campaign.md)
* [创建应用程序内消息](/help/channels/author-in-app-messages.md)

**产品文档：**

* [应用程序内渠道入门](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/get-started-in-app)
* [创建移动应用程序内消息](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/create-in-app)
* [设计应用程序内内容](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/design-in-app)
* [检查并发送应用程序内通知](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/send-in-app)
