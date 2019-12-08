---
description: 決定是否開始新瀏覽。
keywords: Analytics Implementation
title: getVisitStart
topic: Developer and implementation
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

