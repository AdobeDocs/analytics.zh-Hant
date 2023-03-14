---
title: linkURL
description: 覆寫 AppMeasurement 在連結追蹤呼叫中使用的自動產生連結 URL。
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 76%

---

# linkURL

每當連結追蹤呼叫傳送至 Adobe 時，資料收集伺服器都會自動偵測 URL。使用 `linkURL` 變數來覆寫偵測到的 URL。

## 使用Web SDK的連結URL

連結URL為 [已對應至Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=zh-Hant) 在XDM欄位下 `web.webInteraction.URL`.

## 使用Adobe Analytics擴充功能連結URL

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.linkURL

`s.linkURL` 變數是字串，包含點按連結時瀏覽器的 URL。此變數不會填入報表中任何可用的維度。

```js
s.linkURL = "https://example.com";
```

如果 [tl()](../functions/tl-method.md) 方法的第三個引數未經設定，則會改用 `linkURL` 變數。
