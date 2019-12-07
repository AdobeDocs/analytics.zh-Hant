---
description: 未在報表中記錄及顯示路徑分析資訊的可能原因清單。
keywords: Analytics Implementation
title: 未記錄路徑分析的原因
topic: Developer and implementation
uuid: 9985b7f7-75ea-4c94-97a3-520f92630989
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 未記錄路徑分析的原因

未在報表中記錄及顯示路徑分析資訊的可能原因清單。

* 未在該報表套裝中為該 prop 啟用路徑分析。這項啟用須對報表套裝個別執行。
* 資料未傳入正確的 prop。
* 路徑分析已啟用，且資料位於 prop 中，但未顯示在報表中。雖然 [!UICONTROL sprop] 資料可在 10 分鐘內顯示，但在訪客的工作階段結束前，路徑分析資料將不會顯示。工作階段會在未活動達 30 分鐘後結束。Analytics 接著需要再花 10 分鐘來處理路徑資料，以將其呈現在報表中。

若您已檢查前述所有事項，但資料仍未顯示，請洽詢客戶服務以進行進一步的除錯。
