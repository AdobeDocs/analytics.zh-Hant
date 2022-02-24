---
title: trackInlineStats
description: 在您的實施中啟用或停用 Activity Map。
keywords: 停用 Activity Map
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '196'
ht-degree: 100%

---

# trackInlineStats

Activity Map 是 Adobe Analytics 中的功能，可收集有關訪客點按位置及點按內容的資料。您可以在 Analytics 報表中檢視這些資料，或使用瀏覽器擴充功能覆蓋來檢視。如果您想要使用 Activity Map 功能，請啟用此變數。

啟用後，AppMeasurement 會收集連結的相關資訊，並在下一個影像要求中傳送該資料。每次點按的資訊會儲存在標示為 `s_sq` 的 Cookie中。

## 使用 Adobe Experience Platform 中的標記啟用 ClickMap

「[!UICONTROL 啟用 ClickMap]」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL 連結追蹤]」摺疊式功能表下方的勾選方塊。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]摺疊式功能表，如此可顯示[!UICONTROL 「啟用 Clickmap」]勾選方塊。

按一下勾選方塊以啟用 Activity Map 追蹤。

## AppMeasurement 和自訂程式碼編輯器中的 s.trackInlineStats

`s.trackInlineStats` 是布林值，可啟用或停用 Activity Map 追蹤。其預設值為 `false`。如果您要啟用Activity Map 資料收集，請將此值設為 `true`。

```js
s.trackInlineStats = true;
```
