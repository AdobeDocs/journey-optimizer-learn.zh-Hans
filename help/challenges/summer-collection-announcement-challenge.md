---
title: 创建夏季收藏集公告 — 挑战
description: 向现有客户的区段发送夏季收藏品公告，以推广新的Luma夏季收藏品。
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 2%

---

# 创建夏季收藏集公告 — 挑战

![AJO夏季收藏品发布横幅](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| 挑战 | 创建夏季收藏集公告 |
|---|---|
| 角色 | 历程管理器 |
| 所需技能 | <ul><li>[创建区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [导入和编辑 HTML 电子邮件内容](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[用例 - 读取区段](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| 要下载的资产 | [季节性收藏集电子邮件文件](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

>[!NOTE]
> 这些练习是根据Luma样本数据开发的。 我们建议设置一个使用示例数据配置的培训沙盒。 请访问教程 [将示例数据导入Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/import-sample-data.html?lang=zh-Hans) 以了解详细说明。

## 故事

虚构的运动服装公司Luma正寻求推广其最新的服装和装备系列，并推动现有客户的销售。 Luma将推出新的夏季系列，并希望专门针对不同的客户群。

## 您的挑战

Luma营销团队要求您在Journey Optimizer中实施夏季收藏集营销活动。

您面临的挑战是在Journey Optimizer创建旅程。 具体而言，您必须创建所需的区段、创建四条消息并构建历程。

>[!NOTE]
> 如果您在共享的培训沙盒中工作，最佳做法是将您的名称或缩写添加为前缀，以作为您创建的任何元素名称的前缀。

### 步骤1:定义区段 — 活动客户

>[!BEGINTABS]

>[!TAB 任务]

在Journey Optimizer中创建一个名为 **您的名称 — 活动客户**.

* 该区段必须仅包含活跃的Luma客户。
* 活跃客户是指在Luma的忠诚度计划（银、金、铂或钻石）中具有等级的客户。


>[!TAB 成功标准]

在区段生成器中，您可以看到估计的符合条件的用户档案数。 如果您在使用Luma示例数据的培训沙盒中工作，则 [!UICONTROL 估计合格用户] 应该有292个500个用户档案。

**已向区段添加符合条件的用户档案：**

您可以通过导航到区段详细信息视图上所列配置文件中的某个配置文件，来检查已添加到区段的用户档案是否符合条件。

在用户档案页面上，检查 [!UICONTROL 属性] 选项卡，确认其符合条件：层应该是银、金、铂或钻石。

![配置文件属性](assets/C1-S1-profile-attributes.png)

您还可以检查 [!UICONTROL 区段成员资格] 选项卡：您的区段应会列出。

>[!NOTE]
>由于需要回填现有用户档案，因此现有用户档案最多可能需要24小时才能显示区段成员资格。

![区段成员资格](assets/C1-S1-profile-segment-membership.png)

>[!TAB 检查您的工作]

区段字段： [!UICONTROL 属性] > [!UICONTROL XDM个人资料] > [!UICONTROL 忠诚度] > [!UICONTROL 层]

您的区段应如下所示：

![区段 — 活动客户](/help/challenges/assets/C1-S1.png)

检查编辑区段屏幕右下角事件下方的代码。

代码应当如下所示：

```javascript
loyalty.tier.equals("diamond", false) or loyalty.tier.equals("gold", false) or loyalty.tier.equals("platinum", false) or loyalty.tier.equals("silver", false)
```

>[!ENDTABS]


### 步骤2:创建历程 — 夏季收藏公告

>[!BEGINTABS]

>[!TAB 任务]

向现有客户电子邮件区段发送夏季系列公告，以推广新的Luma夏季系列。

一家机构为您提供了四个HTML文件，其中包含电子邮件的设计： [下载季节性收藏集电子邮件文件](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip)

创建名为 `(your name) - Summer collection announcement` 根据以下准则：

1. 向Luma活动客户区段发送Luma — 新的季节性收集公告电子邮件，以控制组形式保留10%的受众
   * 消息标题 `(your name)_Luma New Seasonal Collection Announcement`.
   * 主题行 `(recipient's first name), the new Luma collection is here!`.
   * 使用提供的HTML文件 *SearlyCollectionEmail.html* 邮件正文。
2. 等待两天，然后发送一封包含更多目标内容的后续电子邮件：
   * 男性客户应接收 **Luma Men&#39;s Collection电子邮件**
      * 消息标题： **（您的名字）_Luma男士收藏**
      * 主题行： **（收件人的名字），探索“男新运动装”！**
      * 电子邮件正文： *MensCollectionEmail.html* 邮件正文。
   * 女性客户应 **Luma Women&#39;s Collection电子邮件**
      * 消息标题： **（您的名字）_Luma Women&#39;s Collection**
      * 主题行： **（收件人的名字），浏览Luma的Women Collection!**
      * 电子邮件正文： *WomensCollectionEmail.html*
   * 其他客户应会收到 **Luma — 收藏集电子邮件优惠20%**
      * 消息标题： **（您的名称）_Luma — 收藏20%**
      * 主题行：**（收件人的名字），享受20%的销售优惠！**
      * 电子邮件正文： *20OffCollectionEmail.html*
3. 在发送上述定向电子邮件后，等待两天以打开电子邮件
4. 如果目标电子邮件未在2天内打开，请发送 **Luma - 20个%off集合电子邮件** 作为最终的重定位尝试


>[!TAB 成功标准]

#### 预览电子邮件

**电子邮件#1-新季节性收集公告**

使用身份命名空间预览电子邮件： *电子邮件* 和标识值： *Jenna_Palmer9530@emailsim.io*

* 主题行应为：珍娜，新的卢玛系列来了！
* 电子邮件正文应与您在预览中看到的内容匹配： [新的季节性收集公告](/help/challenges/assets/email-assets/SeasonalCollectionEmail.html)


**电子邮件#2 - Luma Men&#39;s Collection**

向自己发送证据

* 输入您的电子邮件地址
* 选择测试用户档案：Chris_Scott1244@emailsim.io

您应会收到一封电子邮件。 主题栏应该写成“克里斯，探索男人的新运动装备！” 且电子邮件正文应与您在预览中看到的内容相匹配： [鹿马门藏](/help/challenges/assets/email-assets/MensCollectionEmail.html)

**电子邮件#3 - Luma Women&#39;s Collection**

使用身份命名空间预览电子邮件： *电子邮件* 和标识值： *Jenna_Palmer9530@emailsim.io*

* 主题行应为： *珍娜，探索卢玛的女装系列！*
* 电子邮件正文应与您在预览中看到的内容匹配： [鲁玛女子藏品](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**电子邮件#4 - Luma 20%收藏**

使用身份命名空间预览电子邮件： *电子邮件* 和标识值： *Benny_Steer4909@emailsim.io*

* 主题行应为： *本尼，享受20%的销售优惠！*
* 电子邮件正文应与您在预览中看到的内容匹配： [Luma收藏20%优惠](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)

**别忘了发布电子邮件！**

#### 测试您的历程

>[!IMPORTANT]
>
>在将历程设置为测试模式之前：
>
>1. 确保读取区段活动的命名空间已设置为“电子邮件”
>1. 对于每封电子邮件，覆盖电子邮件的默认电子邮件参数，以便将其发送到您的电子邮件地址：
>1. 通过单击眼睛符号显示隐藏值。
>1. 在Email参数中，单击T符号（启用参数覆盖）

   >
   >      ![覆盖电子邮件参数](/help/challenges/assets/c3-override-email-paramters.jpg)
> 
>1. 单击Address字段
>1. 在下一个屏幕上，将您的电子邮件地址添加到括号中： *yourname@yourdomain* 在表达式编辑器中，单击确定。

>


测试历程并将电子邮件发送到您自己的帐户：

1. 将历程置于测试模式
2. 一次选择单个配置文件
3. 等待时间：将计时器设置为120秒（在字段中键入计时器）。
4. 触发用户档案进入
5. 您可以使用以下电子邮件地址之一作为用户档案标识符来测试每个分支：
   * 女：珍娜·帕尔默：Jenna_Palmer9530@emailsim.io
   * 男：克里斯·斯科特：Chris_Scott1244@emailsim.io
   * 未指定性别：本尼·斯蒂尔：Benny_Steer4909@emailsim.io

6. 触发用户档案进入后，您应会收到第一封电子邮件，标题应根据您选择的用户档案进行个性化。
7. 历程应继续进入相应的分支，您应收到相关电子邮件（例如，如果您选择了Jenna，则应收到“Luma Women&#39;s Collection”电子邮件）。
8. 打开第二封电子邮件，历程应该结束
9. 您可以重复步骤4。 - 7. ，以检查您的所有分支是否都正常运行。
10. 要测试超时，请将等待时间设置为30秒，然后再次触发该条目。
11. 请勿打开您收到的电子邮件(请勿预览电子邮件(!)) 让等待时间过去。

您应收到以下电子邮件：

* Luma — 新的季节性收藏公告
* 根据您使用的测试用户档案，您应会收到以下电子邮件之一：
   * 珍娜：鲁玛女子藏品
   * 克里斯：鹿马门藏
   * 本尼：Luma — 优惠20%
* 如果您未打开第二封电子邮件：Luma — 优惠20%

>[!TAB 检查您的工作]

您的历程应如下所示：

![历程](/help/challenges/assets/c3-j1-journey.png)

**条件 — 控制组：**

![控制组](/help/challenges/assets/c3-j1-condition-control-group.png)

**条件 — 性别：**\

![条件 — 性别](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
