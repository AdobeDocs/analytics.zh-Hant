---
description: 說明Report Builder如何支援路徑分析和流失報表，以及實作方式與Reports & Analytics有何不同。
title: Report Builder 中的路徑與路徑流失報表
feature: Report Builder
role: User, Admin
exl-id: 211b0e76-2895-401d-a5a5-73e459a486e2
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 83%

---

# Report Builder 中的路徑與路徑流失報表

{{legacy-arb}}

說明Report Builder如何支援路徑分析和流失報表，以及實作和Reports &amp; Analytics （目前生命週期結束）有何不同。

| Reports &amp; Analytics 中的路徑報表名稱 (路徑 > 維度 >) | Report Builder 是否支援？ |
|--- |--- |
| 下一個/上一個維度流量 | 不供作為獨立報表使用。可以數個請求、路徑維度或使用篩選條件重新產生。 |
| 下一個/上一個維度 | 不供作為獨立報表使用。可以路徑維度或使用篩選條件重新產生。 |
| 流失 | 以獨立報表的形式支援並提供 (「路徑 > 維度 > 維度流失」)。 |
| 完整路徑 | 不支援。 |
| PathFinder | 不供作為獨立報表使用。可使用篩選條件重新產生作為路徑報表。 |
| 路徑長度 | 僅支援「頁面」維度。 |
| 頁面分析 > 維度摘要 | 不供作為獨立報表使用。可以數個請求、路徑維度或使用篩選條件重新產生。 |
| 頁面分析 > 重新載入 | 不供作為獨立報表使用。可以維度報表使用「重新載入」度量重新產生。 |
| 頁面分析 > 維度深度 | 僅支援「頁面」維度。 |
| 頁面分析>維度逗留時間 | 不支援。 |
| 登入與退出 > 登入頁面 | 不供作為獨立報表使用。可使用預先定義的「登入網站」篩選條件重新產生作為路徑報表。 |
| 登入與退出 > 原始登入頁面 | 僅支援「頁面」維度。 |
| 登入與退出 > 單頁存取次數 | 不供作為獨立報表使用。可使用預先定義的篩選條件重新產生作為路徑報表。 |
| 登入與退出 > 退出維度 | 不供作為獨立報表使用。可使用預先定義的「退出網站」篩選條件重新產生作為路徑報表。 |