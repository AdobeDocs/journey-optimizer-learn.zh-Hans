---
title: 配置并启动
description: 在Adobe Journey Optimizer (AJO)和Adobe Experience Platform (AEP)中配置移动渠道，将其与移动应用程序集成，并确保为执行营销活动做好准备。
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: true
index: false
last-substantial-update: 2025-08-22T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: eed29b23e46480725b6ed786911758283b25ad16
workflow-type: tm+mt
source-wordcount: '2106'
ht-degree: 18%

---


# 配置并启动

对于&#x200B;**管理员**&#x200B;和&#x200B;**移动应用程序开发人员**，本节将介绍如何在Adobe Journey Optimizer中配置和启动移动和Web渠道。 它涵盖先决条件、权限和平台支持，然后指导您完成创建特定于应用程序的配置。

>[!IMPORTANT]
>
> 如果您不熟悉Journey Optimizer和Experience Platform，请参加以下课程，以熟悉Journey Optimizer中的核心概念数据管理：[Adobe Journey Optimizer中的智能历程激活的工程师数据](https://experienceleague.adobe.com/zh-hans/courses/ajo-engineer-data-for-intelligent-journey-activation){target="_blank"}
>


## Adobe Journey Optimizer中的移动功能

了解Adobe Journey Optimizer为开发人员、营销人员和产品团队提供的移动功能，包括推送消息、应用程序内消息传送和内容个性化。

>[!VIDEO](https://video.tv.adobe.com/v/344613?captions=chi_hans&quality=12&learn=on){transcript=true}


## 渠道配置

### 移动推送和应用程序内

Journey Optimizer中的移动设备实施从应用程序中的&#x200B;**Adobe Experience Platform Mobile SDK**&#x200B;集成开始。 SDK对于数据收集以及与Adobe Experience Platform (AEP)及其应用程序(如Adobe Journey Optimizer (AJO))的交互至关重要。

#### 什么是Mobile SDK：

移动设备SDK：

- 收集应用程序事件（屏幕查看、点按、购买、生命周期事件等）并将它们发送到&#x200B;**Adobe Experience Platform Edge Network**。
- 管理&#x200B;**身份**&#x200B;和&#x200B;**同意**，以便Journey Optimizer可以安全地构建和使用客户配置文件。
- 注册和更新&#x200B;**推送令牌**，并将&#x200B;**推送和应用程序内跟踪事件**&#x200B;发送回Adobe Experience Platform。
- 与&#x200B;**[Journey Optimizer移动扩展](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer)**&#x200B;集成，以便能够端到端地传递、渲染和测量消息。

如果应用程序中没有集成的Mobile SDK，Journey Optimizer将无法可靠地：

- 投放和跟踪移动推送和应用程序内消息。
- 呈现和跟踪内容卡片。
- 使用应用程序内实时行为来触发历程并个性化体验。

#### 新实施的引导式渠道设置

对于新的移动设备应用程序内和推送实施，建议从引导式渠道设置开始。 它降低了数据流配置错误或缺少扩展的风险，并指导您完成使用Assurance的SDK验证。

>[!PREREQUISITES]
>
>确保您拥有：
>
> - 为您的组织配置了&#x200B;**Adobe Journey Optimizer** (AJO)。
> - 通过[数据收集和Journey Optimizer权限](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config#:~:text=Required%20permissions)访问Adobe Experience Platform。
> - AJO中的管理员权限，用于渠道和配置设置。
> - 访问移动设备应用程序的源代码(iOS、Android或跨平台框架)。
> - 您的应用程序启用了所需的操作系统级别功能（例如，推送权限、通知服务扩展、后台模式）。
> - 如果您使用的是现有配置选项，请确保您使用的是[当前的Adobe Experience Platform Mobile SDK版本](https://developer.adobe.com/client-sdks/home/current-sdk-versions/){target="_blank"}


>[!VIDEO](https://video.tv.adobe.com/v/3449632/?captions=chi_hans&learn=on)

有关详细信息，请参阅[引导式渠道设置入门](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config.html?lang=zh-Hans){target="_blank"}


#### 手动配置推送渠道

以下指南将指导您完成有效手动配置和使用推送通知所需的一切，从了解数据流并与Firebase和Apple推送通知服务(APN)等服务集成，到设置移动应用程序和测试通知。

<!-- CARDS
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-gs
{title = Push notification data flow and components}
{description = Learn how to setup and understand key services and workflows involved with push notifications in Journey Optimizer.}
{image = https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/media_1f6e99fa57e318230d92f5dde619c450690b5d27a.png?width=2000&format=webply&optimize=medium}
{target = _blank}

* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-configuration
{image = https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/media_1134ddf9b0f7d39bb365d4884a1d603fd4aa5bbdf.png?width=2000&format=webply&optimize=medium}
{target = _blank}
* https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/overview 
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notification data flow and components">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-gs" title="推送通知数据流和组件" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/media_1f6e99fa57e318230d92f5dde619c450690b5d27a.png?width=400&format=webply&optimize=medium" alt="推送通知数据流和组件"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" title="推送通知数据流和组件">推送通知数据流和组件</a>
                    </p>
                    <p class="is-size-6">了解如何在Journey Optimizer中设置并了解与推送通知相关的主要服务和工作流。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">了解详情</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notification configuration">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-configuration" title="推送通知配置" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/media_1134ddf9b0f7d39bb365d4884a1d603fd4aa5bbdf.png?width=400&format=webply&optimize=medium" alt="推送通知配置"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" title="推送通知配置">推送通知配置</a>
                    </p>
                    <p class="is-size-6">了解如何使用Journey Optimizer配置您的环境以发送推送通知</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">了解详情</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/overview" title="在移动应用程序中实施Adobe Experience Cloud教程" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="在移动应用程序中实施Adobe Experience Cloud教程"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="在移动应用程序中实施Adobe Experience Cloud教程">“在移动应用程序中实施 Adobe Experience Cloud”教程</a>
                    </p>
                    <p class="is-size-6">了解如何实施Adobe Experience Cloud移动应用程序。 本教程将指导您在一个Swift或Android示例应用程序中实施Experience Cloud应用程序。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">了解详情</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### 其他资源


<!-- CARDS
* https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk
{target = _blank}
* https://developer.adobe.com/client-sdks/home/base/assurance
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Get the Adobe Experience Platform Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" title="获取Adobe Experience Platform Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="获取Adobe Experience Platform Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" title="获取Adobe Experience Platform Mobile SDK">获取Adobe Experience Platform Mobile SDK</a>
                    </p>
                    <p class="is-size-6">本指南将介绍如何在应用程序中安装Adobe Experience Platform Mobile SDK。</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">了解详情</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Assurance overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/base/assurance" title="Adobe Experience Platform Assurance概述" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Adobe Experience Platform Assurance概述"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" title="Adobe Experience Platform Assurance概述">Adobe Experience Platform Assurance概述</a>
                    </p>
                    <p class="is-size-6">Adobe Experience Platform Assurance移动扩展概述。</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">了解详情</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### 移动SDK准备清单

在将应用程序交付给营销人员之前，请在&#x200B;**[Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/){target="_blank"}**&#x200B;中确认：

>[!SUCCESS]
> 
> [ ]核心SDK + Journey Optimizer扩展已加载，\
> [ ]事件正在正确的数据流和数据集中流动，\
> [ ]所有关键事件上均存在身份和同意，\
> [ ]个推送令牌和交互已跟踪，并且\
> [ ]至少显示了一个测试应用程序内消息或内容卡并将其记录为展示。


### 内容卡

<!-- CARDS
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp
{title = Configure content cards support in Mobile SDK}
{description = Learn how to integrate content cards in your mobile application using Messaging SDK.}
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure content cards support in Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" title="在 Mobile SDK 中配置内容卡支持" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp./media_17623afb1c5e280b7fb6861b4003d0ef8f8bea24d.jpg?width=400&format=jpg&optimize=medium" alt="在 Mobile SDK 中配置内容卡支持"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" title="在 Mobile SDK 中配置内容卡支持">在Mobile SDK中配置内容卡支持</a>
                    </p>
                    <p class="is-size-6">了解如何使用消息传送SDK在移动应用程序中集成内容卡。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">了解详情</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### WhatsApp

了解如何配置&#x200B;**WhatsApp渠道**：

<!-- CARDS
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="设置 WhatsApp 频道" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470278/?captions=chi_hans&format=jpeg&nocache=1765241811878" alt="设置 WhatsApp 频道"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" title="设置 WhatsApp 频道">设置 WhatsApp 频道</a>
                    </p>
                    <p class="is-size-6">本教程将指导您在 Adobe Journey Optimizer 中设置 WhatsApp 渠道以启用实时业务消息。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">观看</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### 短信/彩信/RCS

使用标准提供商（Twilio、Synch或Infobip）或使用自定义短信提供商配置&#x200B;**短信/彩信/RCS渠道**：

<!-- CARDS
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
{target = _blank}
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
{target = _blank}
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
{target = _blank}
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="配置短信 API 凭据和渠道平面" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3418543?captions=chi_hans&format=jpeg&nocache=1765241812951" alt="配置短信 API 凭据和渠道平面"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="配置短信 API 凭据和渠道平面">配置SMS API凭据和渠道界面</a>
                    </p>
                    <p class="is-size-6">了解如何将 Journey Optimizer 连接到短信服务提供商，以及如何创建短信渠道平面。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">观看</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure a custom SMS provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" title="配置自定义短信服务提供商" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1765241812924" alt="配置自定义短信服务提供商"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="配置自定义短信服务提供商">配置自定义 SMS 提供商</a>
                    </p>
                    <p class="is-size-6">了解如何在Journey Optimizer中配置自定义短信提供程序、设置API凭据和Webhook、管理选择加入/选择退出关键字以及启动个性化营销活动。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">观看</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure MMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="配置彩信 API 凭据和渠道表面" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3438056/?captions=chi_hans&format=jpeg&nocache=1765241812943" alt="配置彩信 API 凭据和渠道表面"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" title="配置彩信 API 凭据和渠道表面">配置 MMS API 凭据和渠道表面</a>
                    </p>
                    <p class="is-size-6">了解如何将 Journey Optimizer 连接到彩信服务提供商，以及如何创建彩信渠道表面。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">观看</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up RCS in Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" title="在 Journey Optimizer 中设置 RCS" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464765/?captions=chi_hans&format=jpeg&nocache=1765241812927" alt="在 Journey Optimizer 中设置 RCS"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" title="在 Journey Optimizer 中设置 RCS">在 Journey Optimizer 中设置 RCS</a>
                    </p>
                    <p class="is-size-6">了解如何使用自定义短信服务提供商在 Adobe Journey Optimizer 中配置和发送品牌化交互式 RCS 消息。本教程将指导您设置 API 凭据、Webhook 和渠道配置，然后构建历程以提供丰富的个性化消息体验，所有这些都是在原生消息应用程序内完成。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">观看</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## 确保遵守隐私法律和平台准则。

<!-- CARDS
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
{target = _blank}
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
{target = _blank}
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables
{cta = Watch}
{target = _blank}
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Privacy Features in Adobe Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/privacy/privacy-landing-page" title="Adobe Journey Optimizer 中的隐私功能" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../mobile-learning-hub/assets/privacy.webp" alt="Adobe Journey Optimizer 中的隐私功能"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        Adobe Journey Optimizer中的<a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Adobe Journey Optimizer 中的隐私功能">隐私功能</a>
                    </p>
                    <p class="is-size-6">了解如何处理隐私请求、审核用户操作、管理同意、应用治理规则以及利用客户管理的密钥等高级安全选项。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">了解详情</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Data Governance Framework Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" title="数据治理框架概述" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32134/?captions=chi_hans&format=jpeg&nocache=1765241813815" alt="数据治理框架概述"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" title="数据治理框架概述">数据治理框架概述</a>
                    </p>
                    <p class="is-size-6">了解 Adobe Experience Platform 中的治理功能。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">观看</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Classify data using labels">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" title="使用标签对数据进行分类" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3422787?captions=chi_hans&format=jpeg&nocache=1765241813814" alt="使用标签对数据进行分类"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" title="使用标签对数据进行分类">使用标签对数据进行分类</a>
                    </p>
                    <p class="is-size-6">了解如何将标签应用于您的架构和数据集。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">观看</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create Data Usage Policies">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" title="创建数据使用策略" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/37121/?captions=chi_hans&format=jpeg&nocache=1765241813810" alt="创建数据使用策略"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" title="创建数据使用策略">创建数据使用策略</a>
                    </p>
                    <p class="is-size-6">了解如何创建和管理数据使用策略。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">观看</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->


## 常见的实施陷阱以及避免方法

大多数移动问题源于&#x200B;**SDK或数据收集配置**，而不源于Journey Optimizer历程或营销活动本身。 使用下表确定出现了什么问题，然后展开相应的部分以了解详细信息。

### Pitfalls概览

| # | 问题/症状 | 常见陷阱 | 修复概览 |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | 引导式通道设置失败；无流量或流量低 | [SDK版本或扩展不一致](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | 更新SDK/扩展版本；在Assurance中验证 |
| 2 | 跟踪批次失败；AEP中有错误 | [数据流或数据集配置错误](#2-misconfigured-datastreams-or-datasets) | 将事件映射到事件数据集，将配置文件映射到配置文件数据集 |
| 3 | 历程无法触发；奇怪的个性化 | [缺少身份或同意/不一致](#3-missing-or-inconsistent-identity-and-consent) | 实施Edge标识和同意；在Assurance中验证 |
| 4 | 无推送投放或在报表中打开 | [推送令牌注册或跟踪中断](#4-push-token-registration-and-tracking-not-wired-correctly) | 通过SDK修复令牌注册和交互跟踪 |
| 5 | 尽管存在活动的营销活动，但没有应用程序内展示次数 | [未显示应用程序内消息或内容卡](#5-in-app-messages-or-content-cards-not-displaying) | 检查消息扩展、触发器和Assurance决策响应 |

### 每个隐患的详细指导

打开与您的症状匹配的隐患，查看要检查什么以及如何修复它。

+++ &#x200B;1. SDK版本和扩展与渠道要求不一致
**您将注意到的内容**

- 推送或应用程序内活动无法访问设备。
- 引导式渠道设置或渠道验证失败。
- Assurance显示缺少的Journey Optimizer、Edge或身份扩展。

**检查内容**

- 您是否使用引导式渠道设置所需的最低&#x200B;**Mobile Core**&#x200B;和&#x200B;**Journey Optimizer**&#x200B;扩展版本？
- 在&#x200B;**Assurance**&#x200B;中，在扩展和事件下：
   - 您是否看到预期的扩展已加载？
   - 是否要将事件发送到Edge Network并进行确认？

**如何修复**

- 升级到支持的Mobile SDK和Journey Optimizer扩展版本。
- 重建应用程序，重新连接到Assurance，然后重新运行引导式渠道设置。

请参阅：[设置移动和Web](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config){target="_blank"}

+++

+++ 2.数据流或数据集配置错误
**您将注意到的内容**

- 事件或推送跟踪批次在Platform数据集中失败。
- 数据摄取错误（例如，“事件不支持更新”）。
- 推送报表或应用程序内报表显示很少跟踪或没有跟踪。

**检查内容**

- 是否有人更改了为Journey Optimizer跟踪创建的&#x200B;**系统架构或数据集**？
- 在您的&#x200B;**数据流**&#x200B;中：
   - 体验事件是否映射到&#x200B;**事件数据集**？
   - 配置文件属性是否映射到&#x200B;**配置文件数据集**？

**如何修复**

- 请勿编辑由AJO创建的系统数据集/架构。
- 更正数据流映射(事件→事件数据集、用户档案→用户档案数据集)。
- 首选引导式渠道设置或记录的数据流步骤，而不是临时更改。

请参阅：Adobe Journey Optimizer中的[推送通知流程](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

+++

+++ 3.缺少身份和同意或身份和同意不一致
**您将注意到的内容**

- 历程不会按预期触发应用程序用户。
- Personalization与其他渠道中的用户行为不匹配。
- 事件显示在Experience Platform中，但用户档案看起来很分散。

**检查内容**

- 是否已为Edge Network **实施**&#x200B;身份并发送稳定的主ID（例如，登录ID）？
- 首选项更改时，Edge Network **的**&#x200B;同意是否已实现并更新？
- 在&#x200B;**Assurance**&#x200B;中：
   - 出站事件是否包含同意值？
   - 它们是否始终包含ECID和您的主ID？

**如何修复**

- 在应用程序中实施或更正Edge Network **的**&#x200B;标识。
- 为Edge Network **实施**&#x200B;同意，并将其连接到您应用程序的同意UI。
- 在Assurance中重新测试，直到标识和同意出现在所有相关事件中。

请参阅：[为Platform Mobile SDK实施实施同意](https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/app-implementation/consent){target="_blank"}

+++

+++ 4.推送令牌注册和跟踪连接不正确
**您将注意到的内容**

- 即使运行营销活动或历程，用户也永远不会收到推送通知。
- 推送报表不显示打开、关闭或交互。

**检查内容**

- 应用程序是否使用Journey Optimizer扩展注册推送令牌：
   - 首次安装时？
   - 每次应用程序更新后？
   - 每当操作系统刷新令牌时？
- 当用户打开或关闭通知时，您是否在Assurance中看到跟踪事件？

**如何修复**

- 添加或更正以下代码：
   - 在创建或刷新令牌时，通过Journey Optimizer Mobile扩展注册令牌。
   - 通过Mobile SDK发送推送交互事件（打开、取消、自定义操作）。
- 使用Assurance确认注册和跟踪事件是否按预期触发。

请参阅：Adobe Journey Optimizer中的[推送通知流程](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

+++

+++ 5.应用程序内消息或内容卡未显示
**您将注意到的内容**

- 无论活动是营销活动还是历程，应用程序内消息或内容卡都不会显示。
- 报表显示0次展示。

**检查内容**

- **Journey Optimizer移动消息传送/应用程序内扩展**&#x200B;和&#x200B;**消息传送SDK**&#x200B;是否已安装并在应用程序中注册？
- 在您的&#x200B;**标记**&#x200B;配置中：
   - 您是否有规则来触发对正确事件（例如，屏幕查看或自定义事件）的请求？
- 在&#x200B;**Assurance**&#x200B;中：
   - 当这些事件触发时，您是否看到应用程序内或内容卡决策请求发出？
   - 您看到来自Edge Network的响应吗？

**如何修复**

- 安装并注册所需的消息传递扩展。
- 添加或更正触发目标事件（屏幕、自定义事件）决策的规则。
- 对于内容卡片，请确保您：
   - 通过消息传送SDK API获取卡。
   - 在您的UI中呈现它们。
   - 通过SDK跟踪交互。

请参阅：
- [创建并发送应用程序内消息](https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp){target="_blank"}
- [在Mobile SDK中配置内容卡支持](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp){target="_blank"}

+++

## 其他资源

- [在移动设备上使用基于CDN的客户端个性化(ODD)以实现更快的个性化（博客）](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626){target="_blank"}
- [下一级别移动应用程序参与度和增长（高峰会议）的密钥](https://business.adobe.com/cn/summit/2025/sessions/the-secret-to-nextlevel-mobile-app-engagement-s603.html)
