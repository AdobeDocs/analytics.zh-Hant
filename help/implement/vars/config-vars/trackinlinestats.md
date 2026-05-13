---
title: trackInlineStats
description: （已淘汰）在您的實施中啟用或停用ClickMap 。
keywords: 停用clickmap
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
TQID: https://experienceleague.adobe.com/K6rwl-ZECfoMLfC0Z25PPq2jV1FBo0cTsl1YfDeNpBQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 29%

---

# trackInlineStats

>[!IMPORTANT]
>
>此變數已淘汰，不再使用。

ClickMap是Adobe Analytics已淘汰的功能，可收集訪客點按位置及點按內容的資料。 此功能已由[Activity Map](/help/analyze/activity-map/overview.md)取代。

啟用後，AppMeasurement 會收集連結的相關資訊，並在下一個影像要求中傳送該資料。 每次點按的資訊會儲存在標示為`s_sq`的Cookie中。

## 使用Adobe Analytics擴充功能啟用ClickMap

[!UICONTROL 啟用ClickMap]是在設定Adobe Analytics擴充功能時，於[!UICONTROL 連結追蹤]設定追蹤器下方的核取方塊。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往「[!UICONTROL 擴充功能]」索引標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 連結追蹤]摺疊式功能表，如此可顯示[!UICONTROL 啟用ClickMap]核取方塊。

>[!NOTE]
>
>此核取方塊與[!UICONTROL 「使用Activity Map]」核取方塊不同，該核取方塊位於[!UICONTROL 資料庫管理]摺疊式功能表下。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.trackInlineStats

`s.trackInlineStats`是布林值，可啟用或停用ClickMap追蹤。 由於功能已淘汰，Adobe不建議設定此變數。 其預設值為 `false`。

```js
s.trackInlineStats = false;
```
