---
title: linkURL
description: 覆寫 AppMeasurement 在連結追蹤呼叫中使用的自動產生連結 URL。
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
TQID: https://experienceleague.adobe.com/O8Bd28njZQDnffeUwCiNGNSNRHk4FU-z48r4pt7Eths
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 34%

---

# linkURL

每當連結追蹤呼叫傳送至Adobe時，AppMeasurement都會偵測所點按的URL。 此URL可協助判斷連結型別，例如下載連結和退出連結。 使用 `linkURL` 變數來覆寫偵測到的 URL。

Analysis Workspace中沒有報告此變數的維度。 它會填入[資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)中的`page_event_var1`欄。 如果您想要追蹤已點按連結的URL，Adobe建議使用自訂變數，例如[Prop](../page-vars/prop.md)。 使用[Activity Map](/help/analyze/activity-map/overview.md)有助於簡化點選連結的資料收集。

## 使用網頁SDK連結URL

連結URL已對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `web.webInteraction.URL`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.linkURL`或`data.__adobe.analytics.pev1`

## 使用Adobe Analytics擴充功能的連結URL

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.linkURL

`s.linkURL`變數是字串，包含點選連結的完整URL。 此變數不會填入報表中任何可用的維度。

```js
s.linkURL = "https://example.com";
```

如果 [tl()](../functions/tl-method.md) 方法的第三個引數未經設定，則會改用 `linkURL` 變數。
