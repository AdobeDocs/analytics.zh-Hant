---
description: 中止標幟可在 doPlugins 內部設定，以導致目前追蹤呼叫不傳送。
keywords: Analytics Implementation
title: s.abort 標幟
topic: Developer and implementation
uuid: 0c6ec8c7-d136-4851-8cb6-6cb1b7f6f0dc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# s.abort 標幟

中止標幟可在 doPlugins 內部設定，以導致目前追蹤呼叫不傳送。

中止標幟皆會隨每個追蹤呼叫重設，因此若後續的追蹤呼叫也需要被中止，就必須在 doPlugins 中再次設定此標幟。

```js
s.doPlugins = function(s) { 
     s.campaign = s.getQueryParam("cid"); 
     if ((!s.campaign) && (!s.events)) { 
          s.abort = true; 
     } 
};
```

這讓您可以集中邏輯，用於識別不想追蹤的活動，例如自訂連結或顯示廣告中的外部連結。
