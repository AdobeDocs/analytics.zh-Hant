---
description: 若在現行頁面 URL 或提供的字串中找到指定的查詢字串參數值，則加以傳回。
keywords: Analytics 實施
seo-description: 若在現行頁面 URL 或提供的字串中找到指定的查詢字串參數值，則加以傳回。
seo-title: Util.getQueryParam
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.getQueryParam
topic: 開發人員和實施
uuid: 1expid148-3e52-46f2-a73 f-003563f7 a62 c
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Util.getQueryParam

若在現行頁面 URL 或提供的字串中找到指定的查詢字串參數值，則加以傳回。

由於重要資料 (例如促銷活動追蹤程式碼、內部搜尋關鍵字等)都可在頁面上的查詢字串中使用，因此  getQueryParam 有助於將資料擷取至 Analytics 變數中。

此公用程式會取代 [getQueryParam](../../implement/js-implementation/plugins/getqueryparam.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) 外掛程式。

**語法:**

```
s.Util.getQueryParam(key, [url], [delim])
```

>[!NOTE]
>
>公用程式的語法與外掛程式的語法不同。

**參數:**

| 參數 | 說明 |
|---|---|
| key | (必要) 您要取得之查詢字串參數的名稱。此參數會區分大小寫。 |
| url | (optional) Default url is `s.pageURL` or `window.location`. 為此參數指定值後，會將從中擷取查詢參數的 URL 覆寫為指定的 URL。 |
| delim | (選用) URL 中的參數分隔字元。預設的分隔字元為 "&amp;"。這可讓您指定替代的查詢字串分隔字元，例如 ";"。 |

**傳回:**

如果未提供索引鍵，或未出現任何URL選項，或URL中找不到索引鍵，函數會傳回空白字串。如果URL中發現分割分隔字元#，則不會考量到追蹤片段分隔字元的所有項目。如果索引鍵存在並指派給值，則會將值解碼並傳回。

**範例:**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

