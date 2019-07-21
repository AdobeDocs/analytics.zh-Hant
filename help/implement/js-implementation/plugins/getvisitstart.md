---
description: 決定是否開始新瀏覽。
keywords: Analytics 實施
seo-description: 決定是否開始新瀏覽。
seo-title: getVisitStart
solution: Analytics
title: getVisitStart
topic: 開發人員和實施
uuid: 7dd3e51f-2f73-4452-a9 fb-cac513 cd28 eb
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getVisitStart

決定是否開始新瀏覽。

**設定變數**

無

**參數**

c = (字串) 追蹤的 Cookie 名稱。

**傳回**

瀏覽的第一頁為 (整數) 1，其他為 0。

**範例呼叫**

```
s.eVar50 = s.getVisitStart("s_visit");
```

