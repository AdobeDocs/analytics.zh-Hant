---
description: 顯示如何建立簡易的「每次瀏覽頁面檢視次數」量度。
title: 建立簡單的「每次造訪頁面檢視次數」量度
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: bf58da2a39e8b9fd298356f23a9bf8f6c394d3de
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 25%

---

# 建立簡單的計算量度

下列資訊說明如何建立簡單的&#x200B;*每次造訪頁面檢視次數*&#x200B;量度。

1. 開始建立量度，如[建立量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)中所述。
1. 命名量度`Page Views per Visits`或類似名稱。
1. 為量度提供使用者易記的&#x200B;**[!UICONTROL 說明]**，以顯示該量度的用途。
1. 選取正確的&#x200B;**[!UICONTROL 格式]**。 在此範例中，請選擇&#x200B;**[!UICONTROL 小數]**。
1. 決定您要報表顯示幾個小數位數。
1. 在&#x200B;**[!UICONTROL 顯示上升趨勢為]**&#x200B;下拉式功能表中，選取▲ **[!UICONTROL 良好（綠色）]**。
1. 新增「**[!UICONTROL 標記]**」用以組織量度。
1. 針對此計算量度，請先將&#x200B;**[!UICONTROL 頁面檢視]**&#x200B;從&#x200B;**[!UICONTROL 維度]**&#x200B;元件拖曳至畫布的&#x200B;**[!UICONTROL 定義]**&#x200B;區段。
1. 然後從&#x200B;**[!UICONTROL Metrics]**&#x200B;元件拖曳&#x200B;**[!UICONTROL 造訪]**，並將量度拖曳至&#x200B;**[!UICONTROL 頁面檢視]**&#x200B;下方（等到藍線出現為止，再拖曳量度）。
1. 選取除![除](/help/assets/icons/Divide.svg)運運算元。 (除是預設運算元。)
1. 當您建置量度時，可以看到量度的&#x200B;**[!UICONTROL 預覽]**。
1. [產品相容性](../../../cm-compatibility.md)會顯示量度是否與「目前的資料」相容，或只與「完全處理的資料」相容。

   ![簡單計算量度](assets/simple-calculated-metric.png)
1. 選取「**[!UICONTROL 儲存]**」。

   注意「**[!UICONTROL 摘要]**」公式會隨著您變更量度定義而更新。

1. （選擇性）若要共用、核准、（重新）標籤、重新命名或刪除量度，您可以前往[計算量度管理員](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)。

