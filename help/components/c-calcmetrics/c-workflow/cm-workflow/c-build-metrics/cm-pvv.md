---
description: 顯示如何建立簡易的「每次瀏覽頁面檢視次數」量度。
title: 建立簡單的「每次造訪頁面檢視次數」量度
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 54%

---

# 建立「每次造訪頁面檢視次數」量度

以下資訊說明如何建立簡單的「每次造訪頁面檢視次數」量度。

若要建立簡單的「每次造訪頁面檢視次數」量度：

1. 開始建立量度，如所述 [建立量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).
1. 將量度命名為「每次瀏覽頁面檢視次數」或類似名稱。
1. 提供使用者易記的&#x200B;**[!UICONTROL 說明]**，以顯示其用途。
1. 選取右側 **[!UICONTROL 格式]**. 在此範例中，選擇 [!UICONTROL **小數**].
1. 決定您要報表顯示幾個小數位數。
1. 在 [!UICONTROL **將上升趨勢顯示為**] 下拉式功能表，選取 [!UICONTROL **良好（綠色）**].
1. 新增「**[!UICONTROL 標記]**」用以組織量度。
1. 針對此量度，請先將「頁面檢視」拖曳至 [!UICONTROL **定義**] 然後將「造訪」拖曳至其下方（等到藍線出現後再放置）。
1. 選取「除」運算元。(除是預設運算元。)
1. 您現在可以在建立期間，於右上角看到該量度的「**[!UICONTROL 預覽]**」。
1. 產品相容性會顯示量度是否與「[目前的資料](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=zh-Hant)」相容，或是只與「完全處理的資料」相容。
1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

   注意「**[!UICONTROL 摘要]**」公式會隨著您變更量度定義而更新。

1. （可選）若要共用、核准、（重新）標籤、重新命名或刪除量度，您可以前往 [計算量度頁面](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md).
