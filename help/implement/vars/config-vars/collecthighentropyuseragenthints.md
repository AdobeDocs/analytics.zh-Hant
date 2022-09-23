---
title: collectHighEntropyUserAgentHints
description: 使用collectHighEntropyUserAgentHints變數來判斷Adobe是否會從Chromium瀏覽器(例如Google Chrome和Microsoft Edge)要求高熵提示。
source-git-commit: 03d12625a0089672fa0a27f8f720065c5ca16a62
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 3%

---


# collectHighEntropyUserAgentHints

Adobe Analytics使用高熵用戶端提示來改善裝置和瀏覽器識別。 閱讀更多有關客戶端提示的資訊，請參閱 [此概述與常見問題集](/help/technotes/client-hints.md) 和 [Google部落格](https://web.dev/user-agent-client-hints/).

## 使用Web SDK收集高熵提示

高熵客戶端提示是Web SDK中上下文類別的一部分。 請參閱 [配置平台Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) 以取得更多詳細資訊。

## 使用Adobe Analytics擴充功能收集高熵提示

「收集高熵使用者代理提示」是在設定Adobe Analytics擴充功能時，於「一般」設定追蹤器下方的核取方塊。

1. 登入 [Adobe Experience Platform資料收集](https://experience.adobe.com/#/@adobepm/data-collection) 使用您的AdobeID憑證。

1. 按一下所需 [!UICONTROL 標籤屬性].

1. 前往 [!UICONTROL 擴充功能] ，然後按一下 [!UICONTROL 設定] 在Adobe Analytics底下。

1. 展開 [!UICONTROL 一般] 折疊式功能表，可顯示 [!UICONTROL 收集高熵用戶代理提示] 框。 這項設定預設為未勾選。

## AppMeasurement中的collectHighEntropyUserAgentHints

此 `s.collectHighEntropyUserAgentHints` 變數可判斷AppMeasurement是否要求來自Chromium瀏覽器(例如Google Chrome和Microsoft Edge)的高熵提示。 Adobe Analytics會使用這些提示來改善裝置和瀏覽器識別。

如果設為TRUE，將從瀏覽器請求所有高熵提示。

`s.collectHighEntropyUserAgentHints = TRUE`

`s.collectHighEntropyUserAgentHints = FALSE`