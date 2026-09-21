---
source-git-commit: 084d4d9457db32e30855cd6466439b1de96f2b68
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 3%
---
# 实时活动

## 这是什么

**实时活动**&#x200B;允许您提供实时、持续的更新，以便在活动进行时随时告知客户，例如正在准备订单、正在运输的投放或正在旅途中的行程。 它不会为每次更新发送新通知，而是会创建一个实时活动，然后随着活动的演变而更新并结束，从而保持客户的锁屏界面或通知阴影与正在发生的情况同步。

Adobe Journey Optimizer支持两种主要移动平台上的实时活动：

* **[iOS Live活动](/help/channels/ios-live-activities.md)** — iPhone锁屏界面和Dynamic Island上的实时丰富更新。
* **[Android Live更新](/help/channels/android-live-updates.md)** — Android通知栏中的实时、持久更新。

要配置Mobile SDK并使用API启动、更新和结束客户历程中的实时体验，请参阅[配置实时活动](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/live-activity/configure-live-activity/mobile-live-configuration-sdk){target="_blank"}。

## 用例

当您需要执行以下操作时，请选择实时活动作为首选渠道：

| # | 好处 | 原因 | 示例用例 |
|---|---------|-----|-------------------|
| 1 | 进行中的进度概览 | 更新直接显示在锁屏界面或Dynamic Island/通知阴影上，用户无需打开应用程序 | <ul><li>食品配送跟踪</li><li>叫车服务状态</li><li>实时运动得分</li></ul> |
| 2 | 减少通知疲劳 | 单个活动会就地更新，而不是触发重复的推送通知 | <ul><li>订单准备和交付阶段</li><li>航班登机和登机口更新</li></ul> |
| 3 | 时间关键型、短期环境 | 非常适合具有明确开始和结束日期的活动 | <ul><li>路边取车倒计时</li><li>锻炼或计时器会话</li></ul> |
| 4 | 本机、可浏览的UI | 使用操作系统原生表面（动态岛、锁屏、通知阴影）以获得高可见度、低摩擦的体验 | <ul><li>包跟踪</li><li>队列或等待时间更新</li></ul> |

## 当&#x200B;*不*&#x200B;使用实时活动时

* 对于没有明确结尾的长期运行或开放状态 — 在基础进程完成后结束活动。
* 对于促销或营销内容 — 请改用推送通知、应用程序内消息或内容卡。
* 当更新节奏很高时，频繁的更新可能会被OS限制或让用户感到噪音。
* 如果您的应用程序不支持iOS Live活动或Android Live更新所需的最低操作系统版本。
