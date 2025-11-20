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
source-git-commit: c0d4d95932a9f529442ac3471ee4070398e1bfa5
workflow-type: tm+mt
source-wordcount: '2463'
ht-degree: 17%

---


# 配置和启动

在Adobe Journey Optimizer和Adobe Experience Platform中配置移动渠道，与移动应用程序集成，并确保为执行营销活动做好准备。

> **注释**\
> 如果您不熟悉Journey Optimizer并Experience Platform，请参加以下课程来熟悉核心概念：
> - [配置和管理Adobe Journey Optimizer](https://experienceleague.adobe.com/zh-hans/courses/ajo-configure-and-administrate-ajo-environment)
>*在本课程中，您将学习如何配置和管理Journey Optimizer环境，包括用户角色、权限、沙盒和电子邮件渠道，以确保高效和安全的操作。*
> - [Adobe Journey Optimizer中智能历程激活的工程师数据](https://experienceleague.adobe.com/zh-hans/courses/ajo-engineer-data-for-intelligent-journey-activation)
>*在本课程中，您将学习如何使用Experience Platform为Journey Optimizer设置和管理实时客户配置文件数据。 了解数据建模、身份映射和数据摄取，以便为个性化的客户历程创建统一的配置文件。*


## Adobe Journey Optimizer中的移动功能

了解Adobe Journey Optimizer为开发人员、营销人员和产品团队提供的移动功能，包括推送消息、应用程序内消息传递和内容个性化。

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## 移动SDK和应用程序配置

Journey Optimizer中的移动实现以应用程序中的&#x200B;**Adobe Experience Platform Mobile SDK**&#x200B;集成开始。 SDK对于数据收集以及与Adobe Experience Platform (AEP)及其应用程序(例如Adobe Journey Optimizer (AJO))的交互至关重要。

移动SDK：

- 收集应用程序事件（屏幕视图、点击、购买、生命周期事件等）并将它们发送到&#x200B;**Adobe Experience PlatformEdge Network**。
- 管理&#x200B;**身份**&#x200B;和&#x200B;**同意**，以便Journey Optimizer可以安全地构建和使用客户配置文件。
- 注册和更新&#x200B;**推送令牌**，并将&#x200B;**推送和应用程序内跟踪事件**&#x200B;发送回Adobe Experience Platform。
- 与&#x200B;**Journey Optimizer移动扩展**（推送、应用程序内、内容卡、决策功能）集成，以便消息可以端到端地传递、渲染和测量。

如果您的应用程序中未集成移动SDK，Journey Optimizer将无法可靠地：

- 传递和跟踪移动推送和应用内消息。
- 呈现和跟踪内容卡片。
- 使用应用程序内的实时行为来触发旅程并个性化体验。


### 先决条件

确保您具有：

- 为您的组织配置的Adobe Journey Optimizer (AJO)。
- 具有数据收集和Journey Optimizer权限的Adobe Experience Platform访问权限。
- 在AJO中拥有渠道和配置设置的管理员权限。
- 访问移动应用程序的源代码(iOS、Android或跨平台框架)。
- 您的应用程序已启用所需的操作系统级别功能（例如，推送权限、通知服务扩展、后台模式）。


### Journey Optimizer所需的Mobile SDK组件

要使用Journey Optimizer移动渠道（推送、应用程序内、内容卡、基于代码的体验），必须在移动应用程序中安装和配置一组&#x200B;**核心**&#x200B;和&#x200B;**特定于渠道**&#x200B;的扩展：

>[!BEGINTABS]

>[!TAB 核心]

#### 核心扩展（所有移动用例均需要）

| 用途 | 扩展示例(iOS/Android) | 注释 |
|----------------------|-----------------------------------------------|-------|
| 活动中心和服务 | 移动核心/AEP核心、AEP服务 | 为所有其他扩展奠定基础。 提供事件中心、网络、存储和共享状态。 |
| Edge Network | Adobe Experience Platform Edge Network | 将应用程序事件发送到Adobe Experience PlatformEdge Network。 |
| 身份标识 | Edge Network身份 | 管理用于配置文件和分段的ECID和其他身份。 |
| 同意 | 同意Edge Network | 收集并强制执行用户同意首选项。 |
| Assurance | Adobe Experience Platform Assurance | 用于端到端地验证和调试SDK和通道配置。 |

>[!TAB 特定于频道]

#### 适用于Journey Optimizer的渠道特定扩展

| 通道/功能 | 其他密钥扩展（在核心之上） | 他们支持的功能 |
|------------------------|---------------------------------------------------------------------|------------------|
| 推送通知 | Journey Optimizer移动扩展（推送） | 注册和更新推送令牌，发送推送跟踪事件，连接到AJO推送配置。 |
| 应用程序内消息 | Journey Optimizer移动扩展（应用程序内）、消息传送UI组件 | 在上下文中获取和显示应用程序内消息，发送印象和交互事件。 |
| 内容卡 | 支持内容卡的消息传送SDK | 获取、呈现和跟踪内容卡片，以实现准确的Journey Optimizer报告。 |
| 基于代码的体验 | Journey Optimizer/decisioning扩展或Edge服务器API | 获取应用程序中特定“表面”的决策；您的应用程序控制内容的呈现方式。 |

>[!ENDTABS]

#### 移动标记属性和配置

可在AEP数据收集（标记）中的&#x200B;**[移动标记属性](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)**&#x200B;中配置这些扩展。 此属性控制：

- 安装了哪些移动SDK扩展。
- 您的应用程序中的哪些事件会触发对Edge Network的调用。
- 数据如何映射到XDM并转发到Adobe解决方案(Journey Optimizer、Analytics等)。

您可以手动创建和配置此移动属性，或使用&#x200B;**[引导式渠道设置](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)**&#x200B;自动为iOS或Android创建所需的标签属性、数据流和渠道配置。

> **提示**\
> 对于新实现，**[引导式渠道设置](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)**&#x200B;是推荐的起始点。 它可以降低错误配置数据流或缺少扩展的风险，并引导您通过Assurance完成SDK验证。

#### 开始使用Mobile SDK：

<!-- CARDS
* https://experienceleague.adobe.com/zh-hans/docs/platform-learn/data-collection/mobile-sdk/overview
    {description = Learn how Adobe Experience Platform Mobile SDK powers end-to-end engagement in your mobile applications.}
* https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/overview
* https://experienceleague.adobe.com/zh-hans/docs/mobile
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/platform-learn/data-collection/mobile-sdk/overview" title="Adobe Experience Platform Mobile SDK概述" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/28948?format=jpeg&nocache=1763594622398" alt="Adobe Experience Platform Mobile SDK概述"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" title="Adobe Experience Platform Mobile SDK概述">Adobe Experience Platform Mobile SDK概述</a>
                    </p>
                    <p class="is-size-6">了解Adobe Experience Platform Mobile SDK如何为您的移动应用程序中的端到端参与提供支持。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">观看</span>
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
                    <p class="is-size-6">了解如何实施Adobe Experience Cloud移动应用程序。 本教程将指导您通过Swift或Android应用程序示例实施Experience Cloud应用程序。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">了解详情</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK Documentation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/mobile" title="Adobe Experience Platform Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://cdn.experienceleague.adobe.com/thumb/exl-cards/documentation.png" alt="Adobe Experience Platform Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/mobile" target="_blank" rel="referrer" title="Adobe Experience Platform Mobile SDK">Adobe Experience Platform Mobile SDK文档</a>
                    </p>
                    <p class="is-size-6">搜索有关 Experience Platform Mobile SDK 的自助文章和教程。 在直播和点播视频活动中，向专家学习策略和最佳实践。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/mobile" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">了解详情</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

有关详细信息，另请参阅[Adobe Experience Platform Mobile SDK文档](https://experienceleague.adobe.com/zh-hans/docs/mobile)

#### 开发人员参考信息：

- [移动SDK开发人员门户（主页）](https://developer.adobe.com/client-sdks/home/)
- [当前SDK版本](https://developer.adobe.com/client-sdks/home/current-sdk-versions/)
- [移动属性（标记）入门](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)
- [获取SDK（安装在您的应用程序中）](https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/)
- [使用移动SDK跟踪事件](https://developer.adobe.com/client-sdks/home/getting-started/track-events/)
- [使用保证进行验证](https://developer.adobe.com/client-sdks/home/base/assurance/)

#### 移动SDK就绪性核对表

> - [ 已安装]核心SDK（核心、边缘、身份、同意、保证）。
> - [ 为您要使用的渠道（推送、应用程序内、内容卡、基于代码）添加了]个Journey Optimizer移动扩展。
> - [ ]数据流已正确配置为事件和配置文件数据集。
> - [ ]身份和同意已实施并通过保证进行验证。
> - [ ]端到端地注册和跟踪已验证的推送令牌。
> - [ ]应用程序内和/或内容卡显示已在设备上验证。
> - [ ]引导式渠道设置用于新实现，或手动与记录的步骤相一致的配置。



## Adobe Journey Optimizer渠道配置

### In-App、Push和WhatsApp

使用引导式渠道设置功能配置&#x200B;**移动渠道**。 了解如何配置&#x200B;**WhatsApp渠道**：

<!-- CARDS
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup
 {description = Learn how to quickly set up and validate web and mobile channels across Experience Platform, Journey Optimizer, and Data Collection, and configure a push notification for a sample iOS marketing app.}
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Guided channel setup">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" title="引导式渠道设置" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3433053/?format=jpeg&nocache=1763594622823" alt="引导式渠道设置"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" title="引导式渠道设置">引导式渠道设置</a>
                    </p>
                    <p class="is-size-6">了解如何快速设置和验证跨Experience Platform、Journey Optimizer和数据集合的Web和移动渠道，以及如何为示例iOS营销应用程序配置推送通知。</p>
                </div>
                <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">观看</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="设置 WhatsApp 频道" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470268/?format=jpeg&nocache=1763594622814" alt="设置 WhatsApp 频道"
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

使用标准提供程序（Twilio、Synch或Infobip）或使用自定义SMS提供程序配置&#x200B;**SMS/MMS/RCS通道**：

<!-- CARDS
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="配置短信 API 凭据和渠道平面" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3413355?format=jpeg&nocache=1763594624036" alt="配置短信 API 凭据和渠道平面"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1763594624067" alt="配置自定义短信服务提供商"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="配置自定义短信服务提供商">配置自定义 SMS 提供商</a>
                    </p>
                    <p class="is-size-6">了解如何在Journey Optimizer中配置自定义SMS提供商、设置API凭据和Webhook、管理选择加入/选择退出关键字和启动个性化营销活动。</p>
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3428872/?format=jpeg&nocache=1763594624083" alt="配置彩信 API 凭据和渠道表面"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464755/?format=jpeg&nocache=1763594624043" alt="在 Journey Optimizer 中设置 RCS"
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

## 博客帖子

- [在移动设备上使用基于CDN的客户端个性化(ODD)，以实现更快的个性化。](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626)
- 适用于Adobe Experience Cloud的[Mobile Activation](https://experienceleaguecommunities.adobe.com/t5/adobe-target-blogs/mobile-activation-for-adobe-experience-cloud/ba-p/541595)

## 确保遵守隐私法律和平台准则。

<!-- CARDS
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables{cta = Watch}
* https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
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
                        <a href="https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Adobe Journey Optimizer 中的隐私功能">Adobe Journey Optimizer中的隐私功能</a>
                    </p>
                    <p class="is-size-6">了解如何处理隐私请求、审核用户操作、管理同意、应用治理规则以及如何利用高级安全选项（如客户管理的密钥）。</p>
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29708/?format=jpeg&nocache=1763594624934" alt="数据治理框架概述"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29709?format=jpeg&nocache=1763594624932" alt="使用标签对数据进行分类"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32977/?format=jpeg&nocache=1763594624933" alt="创建数据使用策略"
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

## 常见的实施错误以及如何避免这些错误

大多数移动问题都源自&#x200B;**SDK或数据收集配置**，而不是源自Journey Optimizer旅程或营销活动本身。 使用下表确定问题所在，然后展开相应的部分了解详细信息。

### 一览中的陷阱

| # | 问题/症状 | 常见陷阱 | 一目了然的修复 |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | 引导式通道设置失败；无流量或流量低 | [SDK版本或扩展不一致](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | 更新SDK/扩展版本；在Assurance中验证 |
| 2 | 跟踪批处理失败；AEP中存在错误 | [数据流或数据集配置错误](#2-misconfigured-datastreams-or-datasets) | 将事件映射到事件数据集，将配置文件映射到配置文件数据集 |
| 3 | 历程无法触发；奇怪的个性化 | [缺少身份或同意/不一致](#3-missing-or-inconsistent-identity-and-consent) | 实施Edge标识和同意；在Assurance中验证 |
| 4 | 无推送投放或在报表中打开 | [推送令牌注册或跟踪中断](#4-push-token-registration-and-tracking-not-wired-correctly) | 通过SDK修复令牌注册和交互跟踪 |
| 5 | 尽管开展了有效的营销活动，但没有应用程序内印象 | [未显示应用程序内消息或内容卡](#5-in-app-messages-or-content-cards-not-displaying) | 检查消息扩展、触发器和保证决策响应 |

### 每个陷阱的详细指导

打开与您的症状匹配的陷阱，查看要检查的内容以及如何修复它。

<details id="1-sdk-versions-and-extensions-not-aligned-with-channel-requirements">
<summary><strong>1。 SDK版本和扩展不符合渠道要求</strong></summary>

**您将注意到的内容**

- 推送或应用程序内活动无法访问设备。
- 引导式渠道设置或渠道验证失败。
- “保证”显示缺少的Journey Optimizer、Edge或Identity扩展。

**检查内容**

- 您是否使用了引导式渠道设置所需的最低&#x200B;**移动核心**&#x200B;和&#x200B;**Journey Optimizer**&#x200B;扩展版本？
- 在&#x200B;**保证**&#x200B;中，在扩展和事件下：
   - 您是否看到加载了预期的扩展名？
   - 事件是否会被发送至Edge Network并确认？

**如何修复**

- 升级到支持的移动SDK和Journey Optimizer扩展版本。
- 重建应用程序，重新连接到Assurance ，然后重新运行Guided Channel Setup。

请参阅： [设置移动和Web](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config)

</details>


<details id="2-misconfigured-datastreams-or-datasets">
<summary><strong>2. 配置错误的数据流或数据集</strong></summary>

**您将注意到的内容**

- 平台数据集中的事件或推送跟踪批处理失败。
- 数据引入错误（例如，“事件不支持更新”）。
- 推送报表或应用程序内报表显示很少跟踪或没有跟踪。

**检查内容**

- 是否有人更改了为Journey Optimizer跟踪创建的&#x200B;**系统架构或数据集**？
- 在您的&#x200B;**数据流**&#x200B;中：
   - 体验事件是否映射到&#x200B;**事件数据集**？
   - 配置文件属性是否映射到&#x200B;**配置文件数据集**？

**如何修复**

- 请勿编辑由AJO创建的系统数据集/架构。
- 更正数据流映射(事件→事件数据集、配置文件→配置文件数据集)。
- 建议使用“引导式通道设置”或记录的数据流步骤，而不是临时更改。

请参阅：Adobe Journey Optimizer中的[推送通知流程](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="3-missing-or-inconsistent-identity-and-consent">
<summary><strong>3. 缺少标识和同意</strong>或标识和同意不一致</summary>

**您将注意到的内容**

- 历程不会按预期触发应用程序用户。
- Personalization与其他渠道中的用户行为不匹配。
- 事件以Experience Platform形式出现，但配置文件看起来很分散。

**检查内容**

- 是否实现了&#x200B;**Edge Network标识**&#x200B;并发送稳定的主ID（例如，登录ID）？
- 是否已实现&#x200B;**Edge Network同意**，并在首选项更改时更新？
- 在&#x200B;**保证**&#x200B;中：
   - 出站事件是否包含同意值？
   - 它们是否包含一致的ECID和您的主ID？

**如何修复**

- 在应用程序中实现或更正Edge Network **的**&#x200B;标识。
- 为Edge Network **实现**&#x200B;同意，并将其连接到您应用程序的同意UI。
- 在Assurance中重新测试，直到标识和同意出现在所有相关事件中。

请参阅：[为Platform Mobile SDK实施实施同意](https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/app-implementation/consent)

</details>


<details id="4-push-token-registration-and-tracking-not-wired-correctly">
<summary><strong>4。 推送令牌注册和跟踪未正确布线</strong></summary>

**您将注意到的内容**

- 即使运行营销活动或历程，用户也永远不会收到推送通知。
- 推送报表不显示打开、关闭或交互。

**检查内容**

- 应用程序是否使用Journey Optimizer扩展注册推送令牌：
   - 首次安装时？
   - 在每次应用程序更新之后？
   - 每当操作系统刷新令牌时？
- 当用户打开或关闭通知时，您会在Assurance中看到跟踪事件吗？

**如何修复**

- 添加或更正符合以下条件的代码：
   - 每当创建或刷新令牌时，都将通过Journey Optimizer移动扩展注册令牌。
   - 通过移动SDK发送推送交互事件（打开、关闭、自定义操作）。
- 使用Assurance确认注册和跟踪事件是否按预期触发。

请参阅： [Adobe Journey Optimizer中的推送通知流](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="5-in-app-messages-or-content-cards-not-displaying">
<summary><strong>5。 应用程序内消息或内容卡不显示</strong></summary>

**您将注意到的内容**

- 即使有活跃的活动或旅程，应用程序内的消息或内容卡也不会出现。
- 报告显示0次观看。

**检查内容**

- 是否已在应用程序中安装并注册了&#x200B;**Journey Optimizer移动消息/应用程序内扩展**&#x200B;和&#x200B;**消息SDK**？
- 在您的&#x200B;**标签**&#x200B;配置中：
   - 是否有对正确的事件（例如，屏幕视图或自定义事件）触发请求的规则？
- 在&#x200B;**保证**&#x200B;中：
   - 当这些事件触发时，您会看到应用程序内或内容卡决策请求发出吗？
   - 你看到来自Edge Network的回复吗？

**如何修复**

- 安装和注册所需的消息扩展。
- 添加或更正在目标事件（屏幕、自定义事件）上触发决策的规则。
- 对于内容卡，请确保您：
   - 通过消息传递SDK API获取卡。
   - 在UI中渲染它们。
   - 通过SDK跟踪交互。

请参阅：
- [创建并发送应用程序内消息](https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp)
- [配置移动SDK中的内容卡支持](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp)

</details>


## 一行就绪性检查清单

在将应用程序交付给营销人员之前，请在&#x200B;**[保证](https://developer.adobe.com/client-sdks/home/base/assurance/)**&#x200B;中确认：

- 加载核心SDK + Journey Optimizer扩展，
- 事件在正确的数据流和数据集上流动，
- 所有关键事件上均存在身份和同意信息，
- 将跟踪推送令牌和交互，并且
- 至少显示了一个测试应用程序内消息或内容卡，并将其记录为