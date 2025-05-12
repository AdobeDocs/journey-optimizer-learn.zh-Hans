---
title: 创建网页以测试解决方案
description: 用于测试使用决策提供的个性化优惠的网页。
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 72a67137-303d-4dfe-9b70-322c81e5fb27
source-git-commit: 9a35160921988103182815efd3551151c09b9bb4
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# 创建网页以测试解决方案

此网页用于测试通过Adobe Journey Optimizer Decisioning提供的个性化优惠。 它提供了一个受控环境，可以在其中触发sendEvent调用并呈现返回的选件内容，从而帮助验证端到端个性化设置并确保决策按预期工作。

以下脚本负责使用Adobe Journey Optimizer在网页上获取和显示个性化优惠。

1. 解码HTML实体：

   有一个辅助函数，可安全地将选件内容中的任何特殊字符转换为可读的HTML。

1. 运行个性化：

   调用后，它会向Adobe的Web SDK发送请求(`sendEvent`)，以获取页面上特定区域（`#ajo-offer`元素）的个性化内容。

   如果返回选件，则会解码HTML并将其插入到页面中。

   如果未返回任何内容，则会记录警告。

1. 等待SDK：

   由于Adobe SDK (alloy)以异步方式加载，因此脚本会等到完全加载后再发出请求。

   它每200毫秒检查一次合金，最多20次，以避免错误。

1. 页面加载时：

   当页面完成加载时，脚本通过调用`waitForAlloy()`启动进程。



```javascript
< script >
    function decodeHtmlEntities(html) {
        const txt = document.createElement("textarea");
        txt.innerHTML = html;
        return txt.value;
    }


function runPersonalization() {
    console.log("🚀 Sending personalization request to AJO...");
    alloy("sendEvent", {
        renderDecisions: true,
        personalization: {
            surfaces: ["#ajo-offer"]
        }
    }).then(result => {
        console.log("🔍 Web SDK decision response:", result);

        const decision = result.propositions?.[0];
        const html = decision?.items?.[0]?.data?.content;

        const container = document.getElementById("ajo-offer");
        if (html && container) {
            const decodedHtml = decodeHtmlEntities(html);
            console.log("✅ Offer HTML content (decoded):", decodedHtml);
            container.innerHTML = decodedHtml;
        } else {
            console.warn("⚠️ No personalized offer returned.");
        }


    }).catch(error => {
        console.error("❌ sendEvent failed:", error);
    });
}

function waitForAlloy(callback, retries = 20) {
    if (typeof alloy === "function") {
        callback();
    } else if (retries > 0) {
        console.log("⌛ Waiting for Alloy...");
        setTimeout(() => waitForAlloy(callback, retries - 1), 200);
    } else {
        console.error("❌ alloy is not loaded after waiting.");
    }
}

// Trigger initial personalization on page load
document.addEventListener("DOMContentLoaded", function() {
    waitForAlloy(() => runPersonalization());
}); <
/script>
```

[可从此处下载示例HTML页面和相关资源](assets/web-page-assets.zip)
