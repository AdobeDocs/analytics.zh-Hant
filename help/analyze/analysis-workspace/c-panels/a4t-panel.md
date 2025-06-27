---
description: 瞭解如何使用Analytics for Target面板來分析您在Analysis Workspace中的Adobe Target活動和體驗。
title: Analytics For Target面板
feature: Panels
role: User, Admin
exl-id: 36bca104-37b8-43c6-b8d0-b607a9a333cc
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 97%

---

# Analytics for Target 面板 {#analyze-for-target-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_a4t_button"
>title="Analytics for Target"
>abstract="在 Analysis Workspace 中分析 Target 的活動和體驗。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_a4t_panel"
>title="Analytics for Target 面板"
>abstract="在 Analysis Workspace 中分析 Target 的活動和體驗。<br/><br>**參數&#x200B;**<br/>**Target 活動**：經過分析的 Target 活動。<br/>**控制體驗**：所選取 Target 活動的控制體驗。<br/>**標準化量度**：訪客、造訪次數或曝光次數。此量度 (也稱為計數方法) 會成為提升度計算的分母。也會影響在套用可信度計算前彙總資料的方式。<br/>**成功量度**：最多可使用 3 個標準 (非計算) 成功量度來分析 Target 活動。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文記錄_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 中的 Analytics for Target 面板。_<br/>_請參閱 [Experimentation 面板](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/panels/a4t-panel)，了解 ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)_&#x200B;**CustomerJourneyAnalytics**&#x200B;中，如何比較不同的使用者體驗、行銷或訊息傳遞變化版本_。_

>[!ENDSHADEBOX]

Analytics for Target 面板可讓您在 Analysis Workspace 中分析 Adobe Target 活動和體驗。此面板最多可以讓您查看 3 個成功量度的提升度和信賴度。若要存取 Analytics for Target 面板，請導覽至啟用 Analytics for Target 元件的報告套裝。然後，選取最左側的面板圖示，並將 Analytics for Target 面板拖曳至您的 Analysis Workspace 專案中。


>[!BEGINSHADEBOX]

請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analytics for Target 面板](https://video.tv.adobe.com/v/37247?quality=12&learn=on){target="_blank"} 的示範影片。

>[!ENDSHADEBOX]

## 使用

若要使用 **[!UICONTROL Analytics for Target]** 面板：

1. 建立 **[!UICONTROL Analytics for Target]** 面板。有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。

### 面板輸入 {#panel-nput}

您可以使用下列輸入設定來設定 Analytics for Target 面板：

![A4T 面板輸入](assets/a4t-panel-input.png)

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 目標活動]** | 從目標活動清單中選取。請注意：清單會填入最近 6 個月內至少點擊過 1 次的活動。如果您在清單中未看到某個活動，表示其存留期可能已超過 6 個月。您仍可從左側邊欄新增該活動，其回顧期間最長為 18 個月。 |
| **[!UICONTROL 控制體驗]** | 選取控制體驗。 |
| **[!UICONTROL 標準化量度]** | 選取訪客、造訪數或曝光數。在大多數的分析使用案例中，均建議使用[!UICONTROL 訪客]。此量度 (也稱為計數方法) 會成為提升度計算的分母。也會影響在套用可信度計算前彙總資料的方式。 |
| **[!UICONTROL 成功量度]** | 從下拉式清單中選取最多 3 個標準 (非計算) 成功事件，或從元件邊欄的量度中拖放量度。每個量度在呈現的面板中都會有專屬的表格和視覺效果。 |

請選取「**[!UICONTROL 「建置]**」以建置面板。

### 面板輸出 {#panel-output}

Analytics for Target 面板會傳回一組豐富的資料和視覺效果，協助您更清楚了解 Adobe Target 活動和體驗的執行方式。面板頂端會提供一個摘要行，為您提示您所選取的面板設定。針對您選取的每個成功量度，[自由格式表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)和[折線圖](/help/analyze/analysis-workspace/visualizations/line.md)顯示轉換率趨勢的視覺效果如下所示：

![已呈現](assets/a4t-panel-output.png)

每個自由表格都會顯示下列量度欄：

| 量度 | 說明 |
|---|---|
| **[!UICONTROL 標準化量度]** | 輸入面板中選取的標準化量度：不重複訪客、造訪數或活動曝光數。 |
| **[!UICONTROL 成功量度]** | 輸入面板中選取的成功量度。 |
| **[!UICONTROL 轉換率]** | 成功量度/標準化量度。 |
| **[!UICONTROL 提升度]** | 對照控制體驗來比較每一個體驗的轉換率。請注意：提升度是 Target 體驗的&#x200B;*鎖定量度*；您無法加以劃分，或與其他維度搭配使用。 |
| **[!UICONTROL 提升度 (下限)]** | 此值代表 95% 信賴度區間中，變異數體驗對控制的提升度下限。<br>請參閱[統計計算](https://experienceleague.adobe.com/zh-hant/docs/target/using/reports/statistical-methodology/statistical-calculations)和[完整信賴度計算機](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) Excel 檔案，以了解更多資訊。 |
| **[!UICONTROL 提升度 (中)]** | 此值代表 95% 信賴度區間中，變異數體驗對控制的提升度中間值。<br>請參閱[統計計算](https://experienceleague.adobe.com/zh-hant/docs/target/using/reports/statistical-methodology/statistical-calculations)和[完整信賴度計算機](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) Excel 檔案，以了解更多資訊。 |
| **[!UICONTROL 提升度 (上限)]** | 此值代表 95% 信賴度區間中，變異數體驗對控制的提升度上限。<br>請參閱[統計計算](https://experienceleague.adobe.com/zh-hant/docs/target/using/reports/statistical-methodology/statistical-calculations)和[完整信賴度計算機](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) Excel 檔案，以了解更多資訊。 |
| **[!UICONTROL 信賴度]** | Student t 檢定會計算可信度等級，指出結果在重新執行該檢定時重複的可能性。量度已套用 75%/85%/95% 的固定條件式格式範圍。如有需要，可在「欄」設定下自訂此格式。注意：可信度是 Target 體驗的「鎖定量度」；您無法加以劃分，或與其他維度搭配使用。<br>請參閱[統計計算](https://experienceleague.adobe.com/zh-hant/docs/target/using/reports/statistical-methodology/statistical-calculations)和[完整信賴度計算機](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) Excel 檔案，以了解更多資訊。 |

如同 Analysis Workspace 中的任何面板，您可以透過新增其他有助於您分析 Adobe Target 活動的表格和[視覺效果](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations)，以繼續進行分析。您也可以在面板級別或自由格式表中套用區段。請注意，如果將其新增到自由格式表中，則必須將其覆蓋在整個表中，以保留提升度和可信度計算。目前不支援欄級區段。

使用「![編輯](/help/assets/icons/Edit.svg)」以重新設定並重建面板。

## 常見問題 {#FAQ}

| 問題 | 回答 |
|---|---|
| Analytics for Target 支援哪些活動類型？ | [深入了解](https://experienceleague.adobe.com/zh-hant/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup)受支援的活動類型。 |
| 提升度和可信度計算是否支援計算量度？ | 否。 [深入了解](https://experienceleague.adobe.com/zh-hant/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence)提升度和可信度不支援計算量度的原因。不過，計算量度可用於這些量度以外的 Analytics for Target 報告。 |
| 為何 Target 與 Analytics 的不重複訪客會有差異？ | [了解更多](https://experienceleague.adobe.com/zh-hant/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports)有關產品之間不重複訪客差異。 |
| 當我在分析中為特定 Target 活動套用點擊區段時，為何會看到有不相關的體驗傳回？ | Analytics for Target 維度是清單變數，表示有可能同時包含許多活動 (和體驗)。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports) |
| 可信度量度是否可計算極端順序，或對多個產品建議套用 Bonferroni 校正？ | 否。 [深入了解](https://experienceleague.adobe.com/zh-hant/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence) Analytics 計算可信度的方式。 |
| 提升度和可信度量度是否可搭配其他維度或劃分使用？ | 提升度和可信度是「目標體驗」維度的「鎖定量度」，因為它們需有控制項和變數才能計算。因此，無法劃分或搭配其他維度使用。 |
| 何時會重新計算提升度和可信度？ | 每當建置面板、面板日期範圍變更或將區段套用至面板或表格時，就會重新計算提升度和信賴度。您將區段篩選器套用至自由格式表格時，必須將區段套用於所有欄或提升度，否則信賴度將無法正確更新。不支援欄級區段。 |

若需更多 Analytics for Target 報告相關的詳細資訊，請造訪 [Analytics for Target 報告](https://experienceleague.adobe.com/zh-hant/docs/target/using/integrate/a4t/reporting)
