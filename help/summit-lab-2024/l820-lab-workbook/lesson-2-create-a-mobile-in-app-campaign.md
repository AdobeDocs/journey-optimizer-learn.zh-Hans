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
source-git-commit: 55ba1a46c1473d94847e7fccc69ed2a33badb54c
workflow-type: tm+mt
source-wordcount: '1432'
ht-degree: 1%

---

# 第2课 — 创建移动应用程序内促销活动

在本课程中，您将创建并触发移动设备应用程序内消息。

## 学习目标

* 了解如何触发应用程序内消息。
* 了解如何创建移动应用程序内促销活动。
* 触发应用程序内消息。

## 练习2.1 — 登录到Journey Optimizer

1. 打开[Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}
2. 使用以下详细信息登录：
   <br>
   **用户名：** L820+**`<your seat number>`**@adobeeventlab.com
   **密码：**   Adobe2024！
   <br>
您可以在实验室计算机桌面上找到登录的详细信息。 使用Adobe ID和密码。
   ![桌面](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/desk-top.png)

   ![登录屏幕](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. 您可以跳过以下两个屏幕：
   <br>
   ![电话号码](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![Personalization弹出窗口](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>您应该登录到Journey Optimizer并在主页上：
>
>![AJO主页](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## 练习2.2创建移动应用程序内促销活动

在本练习中，您将创建一个应用程序内消息传送促销活动，此活动将在您打开应用程序时触发。

1. 在Journey Optimizer的左侧导航中，选择&#x200B;**[!UICONTROL 促销活动]**。

1. 单击&#x200B;**[!UICONTROL 创建营销活动]**。

   ![创建营销活动](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. 在&#x200B;**[!UICONTROL 创建营销活动]**&#x200B;页面的&#x200B;**[!UICONTROL 操作]**&#x200B;部分中，选中&#x200B;**[!UICONTROL 应用程序内消息]**&#x200B;复选框。

1. 从&#x200B;**[!UICONTROL 发送至]**&#x200B;下拉列表中，选择&#x200B;**[!DNL Mobile]**。

1. 从&#x200B;**[!UICONTROL 应用程序表面]**&#x200B;下拉列表中，选择&#x200B;**[!DNL Frecopa Mobile App]**。

1. 单击&#x200B;**[!UICONTROL 创建]**。

   ![应用表面](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>现在，您应该位于Campaign属性上：
>
> ![营销活动属性](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## 练习2.3配置活动

### 2.3.1 [!UICONTROL 属性部分]

为您的营销活动提供一个名称。 请确保以您的座位号开始命名，以便您能够轻松地再次找到您的促销活动。

例如，如果您的座位数为99： `99 - Welcome Campaign`。

![属性节](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2设置自定义触发器规则

1. 向下滚动到&#x200B;**[!UICONTROL 触发器部分]**，然后单击&#x200B;**[!UICONTROL 编辑触发器]**。

   ![修改](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. 在规则生成器中，单击&#x200B;**[!UICONTROL 应用程序启动项]**，然后从下拉列表中选择&#x200B;*将数据发送到Platform*。
   ![发送到数据平台](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. 通过单击&#x200B;**[!UICONTROL 添加条件]**&#x200B;添加条件。

   ![添加条件按钮](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. 从&#x200B;**[!UICONTROL 选择特征]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL XDM事件类型]**。

   ![XDM事件类型](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. 在以下文本字段中，添加一个您可以记住的&#x200B;*`<custom string value>`*。

1. 要保存该值，请单击&#x200B;**[!UICONTROL 添加**] `<custom string value>`。

   此自定义字符串值稍后将用于触发消息。

   >[!TIP]
   > 将您的名额编号添加到自定义字符串值中会使您拥有唯一性且更易于记忆。
   > 
   > 例如：`99exerciseTrigger`

   ![添加自定义触发器字符串值](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. 单击右上方的&#x200B;**[!UICONTROL 完成]**。

>[!SUCCESS]
>
>现在，您已使用自定义触发器事件定义应用程序内消息。
>
>![定义了自定义触发器的Campaign](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3编辑应用程序内消息的内容

在&#x200B;**[!UICONTROL 操作]**&#x200B;部分中，单击&#x200B;**[!UICONTROL 编辑内容]**。

![编辑内容按钮](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

将显示[!UICONTROL 应用程序内消息]编辑器，您可以在其中配置应用程序内消息内容。

#### 2.3.3.1布局

选择应用于消息的布局。

例如，单击&#x200B;**[!UICONTROL 模式]**&#x200B;可将应用程序内消息设置为模式布局。

![模式按钮](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2创作消息并发布营销活动

1. 在媒体部分中，粘贴以下URL： `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
当您单击退出值字段时，您的图像应会显示。

   预览中显示![个媒体](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-media.png)

2. 在以下&#x200B;**[!UICONTROL 内容]**&#x200B;部分中，添加您自己的自定义文本，以便显示在您对&#x200B;**[!UICONTROL 标头]**&#x200B;和&#x200B;**[!UICONTROL 正文]**&#x200B;的邮件中。

   ![标头和正文](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-content.png)

3. 其他选项：
   1. **按钮：**

      ![按钮部分](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. 在编辑器的此部分中，您可以通过编辑按钮文本字段来自定义CTA按钮的文本。

      2. **[!UICONTROL Interact事件]**&#x200B;字段用于定义当用户按下CTA时传递到SDK的值。

      3. **[!UICONTROL Target]**&#x200B;字段用于定义您希望CTA将用户带往何处。 这包括URL和深层链接。 例如，您可以将此深层链接添加到产品页面，如`dxdemo://exoticVibes`。

      4. 您可以通过按&#x200B;**[!UICONTROL +添加按钮]**&#x200B;来添加其他按钮。

      5. 当消息中添加了第二个按钮时，您现在可以选择使用下拉框更改按钮布局。


   2. **高级格式化**

      ![高级格式切换](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      启用此切换将在编辑器中提供其他自定义选项。

      1. 媒体大小
      1. 字体
      1. Pt大小
      1. 字体颜色
      1. 对齐方式

      ![高级格式化选项](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **设置选项卡**

      通过切换到此选项卡并在&#x200B;**[!UICONTROL 预览]**&#x200B;分区中，您可以更改&#x200B;**应用程序预览**。
      <br>\
      ![设置选项卡](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. **[!UICONTROL 布局]**&#x200B;部分为您提供了将图像用作背景或纯色的选项。

      2. **[!UICONTROL 消息]**&#x200B;部分提供了可以为消息启用的自定义交互：
         1. 自定义手势
         2. UI接管
         3. 自定义UI接管
         4. 自定义大小
         5. 自定义位置
         6. 自定义动画
         7. 消息转角
   <br>
4. 当您完成内容创作并对消息感到满意时，请单击&#x200B;**[!UICONTROL 查看以激活]按钮**。

   >[!SUCCESS]
   >
   > 您现在已完成移动设备应用程序内消息的创作。 您现在应位于促销活动&#x200B;**[!UICONTROL 审核以激活]**&#x200B;页面。
   >
   >![查看并激活](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > 您将在此处看到消息的完整摘要。
   >
   > *请记下您用作触发器规则的自定义值。 此值将用于触发您的应用程序内消息。 可在摘要页面的高亮区域找到使用的值。*

   >[!NOTE]
   >应用程序内消息的当前触发器是默认的&#x200B;**应用程序启动事件**，这意味着应用程序内消息在应用程序启动时触发。 您可以在&#x200B;**[!UICONTROL 计划部分]**&#x200B;中看到此项。

5. 如果您已完成审阅营销活动，请按激活按钮发布营销活动。
   <br>
   ![激活](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> 您现在应该会看到营销活动仪表板。 通过滚动或使用搜索功能找到您的营销策划。 当您的营销活动将状态更改为&#x200B;**[!UICONTROL 实时]** （~1分钟）时，您的营销活动现已发布。
>
> ![已发布的营销活动](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## 练习2.4触发移动设备应用程序内消息

要刷新有效负载并下载新发布的营销活动，请执行以下操作：

1. 在移动设备上，完全关闭Fréscopa应用程序。
2. 重新打开Fréscopa应用程序。
3. 现在，导航到应用程序上的练习选项卡。

   ![练习按钮](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. 在文本字段中，键入您在Campaign中定义的自定义触发器值。 然后按提交。


   ![修改](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>通过单击提交，您可以手动触发触发器，此时您创建的应用程序内通知会弹出：
>
>![应用程序内消息](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *如果在触发消息时遇到问题，请检查以下各项：*
> 
> * *在移动应用程序的“事件名称”字段中，确保键入的触发器规则值与Campaign中的相应值完全相同。*
> * *确保大小写正确，并且没有前导或结尾空格。*
> * *如果通过单击返回促销活动信息板上的促销活动，以返回促销活动审核页面，则可以查找您使用的触发器规则值。*

您刚刚创作并发布了您的首条Journey Optimizer应用程序内消息！


## 附加练习：在设备上复制活动和预览

**复制营销活动**&#x200B;和&#x200B;**在设备上预览**&#x200B;功能是开箱即用的功能，可让您在激活之前，直接在设备上复制营销活动并测试和查看应用程序内消息。 在本练习中，您将学习如何使用此功能并预览您在练习3.1中创建的消息。

1. 通过单击“营销活动”仪表板页面中的营销活动名称以打开您刚刚创建的营销活动。 这将带您返回&#x200B;**[!UICONTROL 审核营销活动]**&#x200B;页面。
1. 按&#x200B;**[!UICONTROL 复制按钮]**。 这将打开一个新提示，为您正在复制的新营销活动命名。 添加您容易记住或使用默认名称（默认添加&#x200B;**[!DNL _copy]**）的新名称。

   ![重复的营销活动](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. 点击复制按钮后，将会创建您的重复营销活动，并且您会返回到营销活动仪表板。
1. 复制营销活动后，打开您的新营销活动。

1. 您可以在&#x200B;**[!UICONTROL Campaign审核]**&#x200B;页面或&#x200B;**[!UICONTROL Campaign作者]**&#x200B;步骤中访问“在设备上预览”功能。

   ![在设备上预览按钮](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. 接下来，从“连接到设备”屏幕单击&#x200B;**[!UICONTROL 开始按钮]**。

   ![开始按钮](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. 输入已配置为启动Fréscopa应用程序的基本URL： `dxdemo://`

   ![预览url](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. 按照屏幕上的说明操作：
   1. 使用移动设备扫描二维码，此时会打开Fréscopa应用程序，并显示一个允许您输入所显示图钉的屏幕。
   2. 在设备的Assurance屏幕上输入AJO中显示的pin，然后单击右下角的“连接”按钮（输入pin后）。


   ![输入pin](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. 此弹出窗口显示在计算机屏幕上

   ![弹出窗口](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-pop-up.png)

1. 单击“Done（完成）”按钮。 这将关闭对话框，您的手机现在已连接到设备上的“预览”功能。


>[!SUCCESS]
>
> 您的应用程序内消息会显示在您的设备上。
>
> *连接后，每次单击&#x200B;**[!UICONTROL 在设备上预览]按钮**&#x200B;时，都会显示您的应用程序内消息。

## 其他资源

**操作方法视频：**

* [创建应用程序内营销活动](/help/channels/create-an-in-app-campaign.md)
* [创建应用程序内消息](/help/channels/author-in-app-messages.md)

**产品文档：**

* [开始使用应用程序内频道](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/in-app/get-started-in-app)
* [创建移动应用程序内消息](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/in-app/create-in-app)
* [设计应用程序内内容](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/in-app/design-in-app)
* [检查并发送应用程序内通知](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/in-app/send-in-app)
