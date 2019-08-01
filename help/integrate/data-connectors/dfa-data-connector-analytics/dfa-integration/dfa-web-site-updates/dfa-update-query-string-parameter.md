---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: 更新您的 DFA 查詢字串參數
solution: Analytics
title: 更新您的 DFA 查詢字串參數
topic: Data connectors
uuid: adf585ac-84ff-44c1-a48 d-b072726 c8494
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# 更新您的 DFA 查詢字串參數{#update-your-dfa-query-string-parameter}

如果您在使用 DFA 整合之前，已持續透過 Adobe Analytics 來追蹤廣告促銷活動，則所有的促銷活動 (電子郵件、搜尋或橫幅) 有可能使用相同的查詢字串參數來識別著陸頁面上的參照促銷活動 ID。

若想瞭解何時應從您 DFA 廣告促銷活動的 DFA 資料中要求閱覽和點進資料，Data connectors 必須識別出訪客在何時點按了 DFA 促銷活動橫幅廣告。為此，您必須將有所區分的查詢字串參數新增至 DFA 廣告促銷活動的著陸頁面 URL，使 Data connectors 能夠區分 DFA 廣告促銷活動頁面，與您在網站上可能會有的其他廣告促銷活動頁面。The `dfa_overrideParam` in the JavaScript plug-in (see [Update Your Web Site's Data Collection Code](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) used for DFA.

>[!CAUTION]
>
>雖然促銷活動變數可用於其他促銷活動，但不要用於DFA促銷活動。如果您將促銷活動變數設定為 DFA 促銷活動著陸頁面，Adobe 會無法將曝光數與點按繫結至 DFA 促銷活動點進。在每次造訪時，Adobe 收集伺服器都會在 DFA 伺服器中檢查是否有先前的點按或閱覽。因此，請僅在一般著陸頁面上納入 DFA 外掛程式代碼 (請參閱[更新網站的資料收集代碼](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3))，以避免可能減緩頁面載入速度的非必要重新導向，對於網際網路連線速度較慢的使用者，更是如此。

