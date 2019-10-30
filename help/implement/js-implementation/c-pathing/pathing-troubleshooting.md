---
description: 未在報表中記錄及顯示路徑分析資訊的可能原因清單。
keywords: Analytics 實作
seo-description: 未在報表中記錄及顯示路徑分析資訊的可能原因清單。
seo-title: 未記錄路徑分析的原因
solution: Analytics
title: 未記錄路徑分析的原因
topic: 開發人員和實作
uuid: 9985b7f7-75ea-4c94-97a3-520f92630989
translation-type: ht
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 未記錄路徑分析的原因

未在報表中記錄及顯示路徑分析資訊的可能原因清單。

* 未在該報表套裝中為該 prop 啟用路徑分析。這項啟用須對報表套裝個別執行。
* 資料未傳入正確的 prop。
* 路徑分析已啟用，且資料位於 prop 中，但未顯示在報表中。雖然 [!UICONTROL sprop] 資料可在 10 分鐘內顯示，但在訪客的工作階段結束前，路徑分析資料將不會顯示。工作階段會在未活動達 30 分鐘後結束。Analytics 接著需要再花 10 分鐘來處理路徑資料，以將其呈現在報表中。

若您已檢查前述所有事項，但資料仍未顯示，請洽詢客戶服務以進行進一步的除錯。
