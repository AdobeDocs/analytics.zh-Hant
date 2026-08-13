---
title: trackExternalLinks
description: 啟用或停用退出連結的自動連結追蹤。
feature: Appmeasurement Implementation
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/sFN18vtu4C0voXXXDo3LT-4uY4yyz8-ygwnZxIuABXM'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 340
ht-degree: 59%

---

# trackExternalLinks

Adobe 提供追蹤對外連結的功能，使用者不需要手動設定每個退出連結的 [`tl()`](../functions/tl-method.md) 方法。 如果您想要使用退出連結的自動連結追蹤功能，請啟用此變數。

啟用後，AppMeasurement 會將任何點按的連結 URL 與 [`linkInternalFilters`](linkinternalfilters.md) 和 [`linkExternalFilters`](linkexternalfilters.md) 中的值比較。 如果有相符項目，退出連結追蹤呼叫就會自動引發。

## 使用Web SDK擴充功能來啟用或停用點選收集

設定Web SDK時，請使用[!UICONTROL 啟用按一下資料彙集]核取方塊。 此核取方塊會處理退出和下載連結。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 移至[!UICONTROL 擴充功能]標籤，然後按一下[!UICONTROL Adobe Experience Platform Web SDK]底下的&#x200B;**[!UICONTROL 設定]**&#x200B;按鈕。
1. 在[!UICONTROL 資料彙集]下，按一下&#x200B;**[!UICONTROL 啟用「按一下資料彙集]**」核取方塊。

## 啟用或停用手動實作Web SDK的點選收集

使用[`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled)設定SDK。 欄位是布林值，可判斷是否自動收集與連結點選相關聯的資料。 其預設值為 `true`。 如果您要停用自動連結追蹤，請將此值設為`false`。 此設定會處理下載和退出連結的自動連結追蹤。

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## 使用Adobe Analytics擴充功能追蹤對外連結

「追蹤對外連結」是在設定 Adobe Analytics 擴充功能時，於「[!UICONTROL 連結追蹤]」摺疊式功能表下方的勾選方塊。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往「[!UICONTROL 擴充功能]」索引標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「連結追蹤」]摺疊式功能表，如此可顯示[!UICONTROL 「追蹤對外連結」]勾選方塊。

按一下勾選方塊以啟用自動退出連結追蹤。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.trackExternalLinks

`s.trackExternalLinks` 是指示啟用或停用自動退出連結追蹤的布林值。 如果您不想追蹤對外連結，或想要手動呼叫 `tl()` 方法來追蹤退出連結，請將此變數設為 `false`。

```js
s.trackExternalLinks = true;
```
