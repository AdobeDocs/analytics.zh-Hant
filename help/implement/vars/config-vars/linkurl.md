---
title: linkURL
description: 覆寫 AppMeasurement 在連結追蹤呼叫中使用的自動產生連結 URL。
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 65%

---

# linkURL

每當連結追蹤呼叫傳送至 Adobe 時，資料收集伺服器都會自動偵測 URL。使用 `linkURL` 變數來覆寫偵測到的 URL。

Analysis Workspace中沒有報告此變數的維度。 它會填入[資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)中的`page_event_var1`欄。

## 使用網頁SDK連結URL

連結URL已對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `web.webInteraction.URL`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.linkURL`或`data.__adobe.analytics.pev1`

## 使用Adobe Analytics擴充功能的連結URL

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.linkURL

`s.linkURL` 變數是字串，包含點按連結時瀏覽器的 URL。此變數不會填入報表中任何可用的維度。

```js
s.linkURL = "https://example.com";
```

如果 [tl()](../functions/tl-method.md) 方法的第三個引數未經設定，則會改用 `linkURL` 變數。
