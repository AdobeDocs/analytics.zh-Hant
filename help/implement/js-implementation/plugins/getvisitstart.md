---
description: 決定是否開始新瀏覽。
keywords: Analytics Implementation
solution: Analytics
title: getVisitStart
topic: Developer and implementation
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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

