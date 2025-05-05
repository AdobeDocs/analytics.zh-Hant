---
description: Analysis Workspace 中的元件包含維度、量度、區段及時間範圍；您可將這些元件拖放至專案上。
title: 元件概觀
feature: Components
role: User, Admin
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: f66cc6252ecd54c143c08be1e0e7e5bf90cc42e9
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 100%

---

# 元件概觀

Analysis Workspace 中的元件包含維度、量度、區段及時間範圍；您可將這些元件拖放至專案上。

若要存取「元件」功能表，請在左側邊欄按一下「**[!UICONTROL 元件]**」圖示。您可以從左側邊欄圖示或使用[熱鍵](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)在[面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hant)、[視覺效果](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=zh-Hant)和元件之間切換。

![](assets/component-overview.png)

您也可以調整專案的[檢視密度設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=zh-Hant)，以一次在左側邊欄中看到更多值，方法是前往「**[!UICONTROL 專案 > 專案資訊與設定 > 檢視密度]**。

## 維度 {#dimensions}

[**維度**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html?lang=zh-Hant)是描述訪客行為的文字屬性，可在您的分析中供檢視、劃分和比較。這些維度可在左側「元件」邊欄 (橘色區段) 中找到，通常可作為表格列套用。

維度的範例包括[!UICONTROL 頁面名稱]、[!UICONTROL 行銷管道]、[!UICONTROL 裝置類型]和[!UICONTROL 產品]。維度是由 Adobe 提供，並透過您的自訂實作 (eVar、Prop、分類等) 擷取。

每個維度也包含&#x200B;**維度項目**&#x200B;在內。維度項目可在左側的「元件」邊欄中找到，只要按一下任何維度名稱旁的右箭頭 (項目為黃色) 即可。

維度項目的範例包括[!UICONTROL 首頁] (在「[!UICONTROL 頁面]」維度內)、[!UICONTROL 付費搜尋] (在「[!UICONTROL 行銷管道]」維度內)、[!UICONTROL Tablet] (在「[!UICONTROL 行動裝置類型]」維度內) 等。

![](assets/dimensions.png)

## 量度 {#metrics}

[**量度**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html?lang=zh-Hant)是訪客行為的量化量度。這些量度可在左側「元件」邊欄 (綠色區段) 中找到，通常可作為表格欄套用。

量度的範例包括[!UICONTROL 頁面檢視次數]、[!UICONTROL 造訪次數]、[!UICONTROL 訂購]、[!UICONTROL 平均逗留時間]和[!UICONTROL 收入/訂購]。維度是由 Adobe 提供，或是透過您的自訂實作 ([!UICONTROL 成功事件]) 擷取，或是使用[計算量度產生器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=zh-Hant)建立。

![](assets/metrics.png)

## 區段 {#segments}

[**細分群體**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=zh-Hant)是套用至分析的客群篩選器。這些區段可在左側「元件」邊欄 (藍色區段) 中找到，通常套用在面板頂端或表格中量度欄的上方。

區段的範例包括[!UICONTROL 行動裝置訪客人數]、[!UICONTROL 電子郵件的造訪次數]和[!UICONTROL 已驗證點擊次數]。區段是由 Adobe 提供，或在[面板下拉區域](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hant)中建立，或使用[區段產生器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=zh-Hant)建立。

![](assets/segments.png)

## 日期範圍 {#date-ranges}

[**日期範圍**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html?lang=zh-Hant)是您進行分析的日期範圍。這些日期範圍可在左側「元件」邊欄 (紫色區段) 中找到，通常可套用在每個面板的行事曆中。

您可以使日期範圍元件相對於面板行事曆。如需其他資訊，請參閱[關於相對面板日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)。

日期範圍的範例包括 2019 年 7 月、[!UICONTROL 最近 4 週]和[!UICONTROL 本月]。日期範圍是由 Adobe 提供，或在[面板行事曆](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hant)中套用，或使用[日期範圍產生器](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=zh-Hant)建立。

![](assets/date-ranges.png)


## 管理元件 {#actions}

您可以直接在左側邊欄中管理元件。

1. 在元件上按一下右鍵。

   或

   選取元件，然後選取元件清單頂端的&#x200B;**操作** (3 個點) 圖示。

   >[!TIP]
   >
   >   按住 Shift 或按住 Command (Mac 版) 或 Ctrl (Windows 版)，即可選取多個元件。


   ![](assets/component-actions.png)

   | 元件動作 | 說明 |
   |--- |--- |
   | [!UICONTROL **標記**] | 以套用標記的方式組織或管理元件。然後，您可以按一下篩選或輸入 #，依左側欄中的標籤進行搜尋。標籤也會當作元件管理員中的篩選器。 |
   | [!UICONTROL **我的最愛**] | 將元件新增至我的最愛清單。如同標籤，您可以依左側邊欄的「我的最愛」搜尋，並在元件管理員中這些條件篩選。 |
   | [!UICONTROL **核准**] | 將元件標示為「已核准」，向您的使用者表示此元件已獲得組織核准。如同標籤，您可以依左側邊欄的「已核准」搜尋，並在元件管理員中這些條件篩選。 |
   | [!UICONTROL **共用**] | 與組織中的使用者共用元件。此選項僅適用於自訂元件，例如區段或計算量度。 |
   | [!UICONTROL **刪除**] | 刪除您不再需要的元件。此選項僅適用於自訂元件，例如區段或計算量度。 |

自訂元件也可透過其各自的元件管理員來管理。例如[區段管理員](/help/components/segmentation/segmentation-workflow/seg-manage.md)。

## 搜尋、篩選元件清單並進行排序

您可以在 Analysis Workspace 的左側邊欄中搜尋、篩選元件清單並進行排序，以快速找到特定元件。

### 搜尋元件清單

1. 在左側邊欄中選取&#x200B;**元件**&#x200B;圖示![元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 在搜尋欄位中開始輸入要用於專案中的元件的名稱。

   元件的類型可依據顏色和圖示加以識別。**維度**![維度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)是橙色的，**區段**![區段圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)是藍色的，**日期範圍**![日期範圍圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)是紫色的，而&#x200B;**量度**![量度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)是綠色的。Adobe 圖示代表計算量度範本或區段範本，計算機圖示![計算機圖示](assets/calculated-metric-icon-created.png)則代表由貴組織中的 Analytics 管理員所建立的計算量度。

3. 當元件出現在下拉式清單中時請將其選取。

### 篩選元件清單

1. 在左側邊欄中選取&#x200B;**元件**&#x200B;圖示![元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 選取&#x200B;**篩選**&#x200B;圖示![資料字典篩選器圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)。

   或

   在搜尋欄位中輸入井字號 (#)。

3. 選取以下任一篩選器選項以篩選元件清單：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **已核准**] | 僅顯示標記為由管理員核准的元件。 |
   | [!UICONTROL **我的最愛**] | 僅顯示「我的最愛」清單中的元件。有關將元件新增到「我的最愛」清單的資訊，請參閱[元件概觀](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)。 |
   | [!UICONTROL **維度**] | 僅顯示維度的元件。 |
   | [!UICONTROL **量度**] | 僅顯示量度的元件。 |
   | [!UICONTROL **區段**] | 僅顯示區段的元件。<!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **日期範圍**] | 僅顯示日期範圍的元件。 |
   | [!UICONTROL **全部顯示**] | 顯示所有元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **未經核准**] | 僅顯示尚未由管理員標記為「已核准」的元件。作為管理員，這有助於確定需要您檢閱和核准的元件。此選項僅提供給管理員使用。 |

4. (可選) 若要進一步整理清單，您可以依據[對元件清單進行排序](#sort-the-component-list)中的說明將元件清單排序。

### 將元件清單排序

1. (可選) 依據[篩選元件清單](#filter-the-component-list)中的說明，對元件清單套用任何篩選器。

2. 在左側邊欄中選取&#x200B;**元件**&#x200B;圖示![元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

3. 選取&#x200B;**排序** 圖示![排序元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然後選取以下任一篩選器選項，將元件清單排序：

   {{components-sort-options}}
