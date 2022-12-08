---
title: 创建夏季收藏集公告 — 挑战
description: 向现有客户的区段发送夏季收藏集公告，以推广新的Luma夏季收藏集。
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: cfd438e198fdf62859569eed0c6ac22087ddbc75
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 2%

---

# 创建夏季收藏集公告 — 挑战

![AJO夏季收藏品发布横幅](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| 挑战 | 创建夏季收藏集公告 |
|---|---|
| 角色 | 历程管理器 |
| 所需技能 | <ul><li>[创建区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [导入和编辑 HTML 电子邮件内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[用例 - 读取区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| 要下载的资产 | [季节性收藏集电子邮件文件](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## 故事

虚构的运动服装公司Luma正在宣传其最新的服装和装备系列，并推动现有客户的销售。 Luma将推出新的夏季收藏集，并希望专门针对不同的客户区段。

## 您的挑战

Luma营销团队要求您在Journey Optimizer中实施夏季收藏集营销活动。 您面临的挑战是：

* 创建一个区段，用于定义哪些用户档案有资格接收促销活动。
* 构建历程.

### 步骤1:定义区段 — 活动客户

>[!BEGINTABS]

>[!TAB 任务]

#### 在中创建区段 [!DNL Journey Optimizer]

* 在中创建区段 [!DNL Journey Optimizer] 调用 *活动客户*.
* 该区段必须仅包含活跃的Luma客户。
* 活跃客户是指在Luma的忠诚度计划（铜、银、金或铂）中具有等级的客户。


>[!TAB 成功标准]

在区段生成器中，您可以看到估计的符合条件的用户档案数。 如果您使用培训沙盒数据，则在129 K中有大约753个符合条件的用户档案。

>[!NOTE]
>由于需要回填现有用户档案，因此现有用户档案最多可能需要24小时才能显示区段成员资格。

**已向区段添加符合条件的用户档案：**

您可以通过导航到区段详细信息视图上所列用户档案中的某个用户档案，来检查已添加到区段的用户档案是否符合条件。

在用户档案页面上，检查 [!UICONTROL 属性] 选项卡，确认其符合条件：层应该是银、金、铂或钻石。

![配置文件属性](assets/C1-S1-profile-attributes.png)

您还可以检查 [!UICONTROL 区段成员资格] 选项卡：您的区段应会列出。

![区段成员资格](assets/C1-S1-profile-segment-membership.png)

>[!TAB 检查您的工作]

区段字段： [!UICONTROL 属性] > [!UICONTROL XDM个人资料] > [!UICONTROL 忠诚度] > [!UICONTROL 层]

您的区段应如下所示：

![区段 — 活动客户](/help/challenges/assets/C1-S1.png)

代码应当如下所示：

```javascript
stringCompare("equals", loyalty.tier, ["diamond", "gold", "platinum", "silver"], false)
```

>[!ENDTABS]


### 步骤2:创建历程 — 夏季收藏集公告

>[!BEGINTABS]

>[!TAB 任务]

#### 发送夏季收藏集公告

一家机构为您提供了四个HTML文件，其中包含电子邮件的设计：

* `SeasonalCollectionEmail.html`
* Luma Men&#39;s Collection电子邮件
* Luma Women&#39;s Collection电子邮件
* Luma — 收藏集电子邮件优惠20%

1. [下载季节性收藏集电子邮件文件](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

2. 创建名为 *Luma — 夏季收藏品发布* 根据以下准则：

   1. 发送 *Luma — 新的夏季系列发布* 电子邮件至 *活动客户* 10%的受众作为控制组
      * 消息标题 *Luma — 夏季收藏品发布*
      * 主题行 *（收件人的名字），新的Luma夏季系列在此！*
      * 使用提供的HTML文件 `SeasonalCollectionEmail.html` 邮件正文。
   2. 等待两天，然后发送一封包含更多目标内容的后续电子邮件：
      * 男性客户应接收 **鹿马门藏** 电子邮件。
         * 消息标题： *鹿马门藏*
         * 主题行： *（收件人的名字），探索“男新运动装”！*
         * 电子邮件正文： `MensCollectionEmail.html` 邮件正文。
      * 女性客户应 **鲁玛女子藏品** 电子邮件。
         * 消息标题： *鲁玛女子藏品*
         * 主题行： *（收件人的名字），浏览Luma的Women Collection!*
         * 电子邮件正文： `WomensCollectionEmail.html`
      * 其他客户应会收到 **Luma — 收藏20%** 电子邮件。
         * 消息标题： *Luma — 收藏20%*
         * 主题行： *（收件人的名字），享受20%的销售优惠！*
         * 电子邮件正文： `20OOffCollectionEmail.html`
   3. 在发送上述定向电子邮件后，等待两天以打开电子邮件
   4. 如果目标电子邮件未在2天内打开，请发送 **Luma - 20个%off集合电子邮件** 作为最终的重定位尝试


>[!TAB 成功标准]

#### 预览电子邮件

**电子邮件#1 - Luma — 夏季收藏公告**

预览电子邮件：

1. 添加测试用户档案：路易丝·佩蒂：
   1. 身份命名空间： *Luma CRM ID*
   2. 标识值： *d1f132f9f9502bba047a6ec86c4b61f9*

结果:
* 主题行应为：露易丝，新的卢玛系列来了！
* 电子邮件正文应与您在预览中看到的内容匹配： [新的季节性收集公告](/help/challenges/assets/email-assets/SeasonalCollectionEmail.html)


**电子邮件#2 - Luma Men&#39;s Collection**

向您自己发送验证：

1. 添加测试用户档案：斯坦利·斯托克：
   1. 身份命名空间： *Luma CRM ID*
   1. 标识值： `4f34057d9d9e792c28ba18ecae378e98`
1. 选择测试用户档案：斯坦利·斯托克。
1. 给自己发个证据。

结果:\
您应会收到一封电子邮件。 主题行应该写成 *斯坦利，探索男子新运动装备！* 且电子邮件正文应与您在预览中看到的内容相匹配： [鹿马门藏](/help/challenges/assets/email-assets/MensCollectionEmail.html)

>[!NOTE]
>你可能需要几分钟才能收到证据。

**电子邮件#3 - Luma Women&#39;s Collection**

使用测试用户档案预览电子邮件 *露易丝·佩蒂。*

* 主题行应为： *露易丝，探索卢玛的女装系列！*
* 电子邮件正文应与您在预览中看到的内容匹配： [鲁玛女子藏品](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**电子邮件#4 - Luma 20%收藏**

使用测试用户档案预览电子邮件 *露易丝·佩蒂。*

* 主题行应为： *露易丝，享受20%的销售优惠！*
* 电子邮件正文应与您在预览中看到的内容匹配： [Luma收藏20%优惠](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)


#### 测试您的历程

>[!IMPORTANT]
>
>在将历程设置为测试模式之前：
>
>1. 确保 [!UICONTROL 读取区段活动] 将命名空间设置为 **Luma CRM id(lumaCrmId)**
>1. 对于每封电子邮件，覆盖电子邮件的默认电子邮件参数，以便将其发送到您的电子邮件地址：
   >    * 通过单击眼睛符号显示隐藏值。
   >    * 在电子邮件参数中，单击T符号（启用参数覆盖）。

      >
      >      ![覆盖电子邮件参数](/help/challenges/assets/c3-override-email-paramters.jpg)
   > 
   >    * 单击 [!UICONTROL 地址] 字段
   >    * 在下一个屏幕中，将您的电子邮件地址添加到括号中： `"yourname@yourdomain"` 在表达式编辑器中，单击确定。

>


测试历程并将电子邮件发送到您自己的帐户：

1. 将历程置于测试模式。
1. 一次选择单个用户档案。
1. 等待时间：将计时器设置为120秒（在字段中键入计时器）。
1. 触发用户档案进入
1. 您可以使用以下任一方法测试每个分支 *Luma CRM Id* 作为配置文件标识符：
   * 女：Leora Dietsche，身份值：`a8f14eab3b483c2b96171b575ecd90b1`
   * 男：斯坦利·斯托克，身份价值： `4f34057d9d9e792c28ba18ecae378e98`
   * 未指定性别：路易丝·佩蒂，身份价值： `d1f132f9f9502bba047a6ec86c4b61f9`

1. 触发用户档案进入后，您应会收到第一封电子邮件。 标题应根据您选择的用户档案进行个性化。
1. 历程应继续进入相应的分支，您应会收到相关电子邮件(例如，如果您选择 *珍娜*，您应会收到 *鲁玛女子藏品* 电子邮件)。
1. 打开第二封电子邮件，历程应该结束。
1. 您可以重复步骤4。 - 7. ，以检查分支是否正常工作。
1. 要测试超时，请将等待时间设置为30秒，然后再次触发该条目。
1. 请勿打开您收到的电子邮件(请勿预览电子邮件(!)) 让等待时间过去。

您应收到以下电子邮件：

* Luma — 新的季节性收藏公告
* 根据您使用的测试用户档案，您应会收到以下电子邮件之一：
   * 莱奥拉：鲁玛女子藏品
   * 斯坦利：鹿马门藏
   * 露易丝：Luma — 优惠20%
* 如果您未打开第二封电子邮件：Luma — 优惠20%

>[!TAB 检查您的工作]

您的历程应如下所示：

![历程](/help/challenges/assets/c3-j1-journey.png)

**条件 — 控制组：**

![控制组](/help/challenges/assets/c3-j1-condition-control-group.png)

**条件 — 性别：**\

![条件 — 性别](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
