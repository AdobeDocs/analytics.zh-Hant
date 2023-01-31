---
title: collectHighEntropyUserAgentHints
description: 使用 collectHighEntropyUserAgentHints 變數來確定 Adobe 是否會要求 Chromium 瀏覽器 (例如 Google Chrome 和 Microsoft Edge) 的高平均資訊量提示。
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
source-git-commit: 5318079d6ad972e66494cd7b7f3bd64359b11012
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 82%

---

# collectHighEntropyUserAgentHints

Adobe Analytics 使用高平均資訊量用戶端提示來協助識別裝置和瀏覽器。此選項自2.23.0版AppMeasurement.js開始可用。 請在[本概述和常見問題](/help/technotes/client-hints.md)以及 [Google 部落格](https://web.dev/user-agent-client-hints/)閱讀更多有關用戶端提示的資訊。

## 使用 Web SDK 收集高平均資訊量提示

高平均資訊量用戶端提示是 Web SDK 中內容類別的一部分。如需更多資訊，請參閱[設定平台 Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant)。

## 使用 Adobe Analytics 擴充功能收集高平均資訊量提示

**[!UICONTROL 收集高平均資訊量使用者代理提示]**&#x200B;是在設定 Adobe Analytics 擴充功能時，「一般」摺疊式功能表下的一個核取方塊。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/#/@adobepm/data-collection)。

1. 按一下所需的 [!UICONTROL 標記屬性。]。

1. 前往 [!UICONTROL 擴充功能] 索引標籤，然後按一下 Adobe Analytics 下方的 [!UICONTROL 設定]。

1. 展開 [!UICONTROL 一般] 摺疊式功能表，其中顯示 [!UICONTROL 收集高平均資訊量使用者代理提示] 核取方塊。這項設定預設為未勾選。

## AppMeasurement 中的 collectHighEntropyUserAgentHints

此 `s.collectHighEntropyUserAgentHints` 變數可判斷AppMeasurement是否要求Chromium瀏覽器的高熵提示(例如Google Chrome或Microsoft Edge)。 Adobe Analytics 使用這些提示來協助識別裝置和瀏覽器。

若設為 `true`，則會從瀏覽器請求所有高熵提示。

```js
s.collectHighEntropyUserAgentHints = true;
```
