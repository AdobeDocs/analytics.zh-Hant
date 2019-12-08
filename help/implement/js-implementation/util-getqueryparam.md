---
description: 若在現行頁面 URL 或提供的字串中找到指定的查詢字串參數值，則加以傳回。
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.getQueryParam
topic: Developer and implementation
uuid: 1fecd148-3e52-46f2-a73f-003563f7a62c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.getQueryParam

若在現行頁面 URL 或提供的字串中找到指定的查詢字串參數值，則加以傳回。

由於重要資料 (例如促銷活動追蹤程式碼、內部搜尋關鍵字等)都可在頁面上的查詢字串中使用，因此   getQueryParam 有助於將資料擷取至 Analytics 變數中。

此公用程式會取代  [getQueryParam](/help/implement/js-implementation/plugins/getqueryparam.md) 外掛程式。

**語法:**

```
s.Util.getQueryParam(key, [url], [delim])
```

> [!NOTE]公用程式的語法與外掛程式的語法不同。

**參數:**

| 參數 | 說明 |
|---|---|
| key | (必要) 您要取得之查詢字串參數的名稱。此參數會區分大小寫。 |
| url | (選用) 預設 URL 為 `s.pageURL` 或 `window.location`。為此參數指定值後，會將從中擷取查詢參數的 URL 覆寫為指定的 URL。 |
| delim | (選用) URL 中的參數分隔字元。預設的分隔字元為 "&amp;"。這可讓您指定替代的查詢字串分隔字元，例如 ";"。 |

**傳回:**

若未提供任何索引鍵、或若無 URL 選項存在，或若無法在 URL 中找到索引鍵，則函數會傳回空字串 ""。若在 URL 找到片段分隔字元 #，則不會將分段分隔字元之後的所有內容視為內容。如果索引鍵存在且指派給某個值，則值已 URL 解碼及傳回。

**範例:**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

