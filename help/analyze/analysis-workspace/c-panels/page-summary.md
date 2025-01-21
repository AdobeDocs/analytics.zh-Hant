---
description: 頁面摘要面板會顯示您所選頁面的摘要資訊。
title: 頁面摘要面板
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 2aaa8c0d13755b40ec701ca6342ab773103a0422
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 12%

---

# 頁面摘要面板 {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="頁面摘要"
>abstract="快速檢閱部分高階量度，以及特定頁面的來回移動。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="頁面摘要面板"
>abstract="快速檢閱部分高階量度，以及特定頁面的來回移動。<br/><br/>**引數&#x200B;**<br/>**新增頁面維度專案**：開啟元件邊欄，找出頁面維度，然後按一下胡蘿蔔來展開維度，以檢視維度專案。 然後，將您想要瞭解的特定頁面拖放至產生器。 拖放維度專案後，報表會自動填入頁面的重要資訊。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文會在_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中記錄頁面摘要面板。_<br/>_在_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中沒有對應的面板。_

>[!ENDSHADEBOX]

**[!UICONTROL 頁面摘要]**&#x200B;面板可讓您探索有關特定頁面的關鍵統計資料。

## 使用

若要使用&#x200B;**[!UICONTROL 頁面摘要]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 頁面摘要]**&#x200B;面板。 有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。



您可以從[!UICONTROL 報表]內或[!UICONTROL Workspace]記憶體取面板。

| 存取點 | 說明 |
| --- | --- |
| [!UICONTROL 報表] | <ul><li>該面板已放入專案中。</li><li>左側邊欄會摺疊。</li><li>僅支援頁面維度。</li><li>已套用預設設定，在此例中為[!UICONTROL 頁面]維度的最常造訪的頁面。 您可以修改此設定。</li></ul> |
| Workspace | 建立新專案，並在左側欄中選取「面板」圖示。 將[!UICONTROL 頁面摘要]面板拖曳至自由表格上方。 請注意，頁面[!UICONTROL Dimension專案]欄位留空。 從下拉式清單中選取維度專案。 |

### 面板輸入 {#panel-input}

您可以使用這些輸入設定來設定[!UICONTROL 頁面摘要]面板：

![頁面輸入摘要](assets/page-summary-input.png)

| 輸入 | 說明 |
| --- | --- |
| **[!UICONTROL 頁面]** | 選取您要探索其關鍵統計資料的頁面的頁面維度。 |

{style="table-layout:auto"}


選取&#x200B;**[!UICONTROL 建置]**&#x200B;以建置面板。

### 面板輸出 {#panel-output}

[!UICONTROL 頁面摘要]面板會傳回一組豐富的量度資料和視覺效果，協助您更清楚瞭解特定頁面的統計資料。

![頁面摘要面板](assets/page-summary-output.png)

| 視覺效果 | 說明 |
| --- | --- |
| **[!UICONTROL 頁面檢視次數] — 目前月份（到目前為止）** | 顯示這個頁面當月頁面檢視次數的[摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)視覺效果。 |
| **[!UICONTROL 頁面檢視次數] - 4週前** | [摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)視覺效果會顯示過去一個月此頁面的頁面檢視次數。 |
| **[!UICONTROL 頁面檢視次數] - 52週前** | [摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)視覺效果會顯示去年此頁面的頁面檢視次數。 |
| **[!UICONTROL 趨勢]** | 本月、4週前和52週前的頁面檢視趨勢[線條](/help/analyze/analysis-workspace/visualizations/line.md)視覺效果。 |
| **[!UICONTROL 所有頁面檢視的百分比]** | 瀏覽此頁面之所有頁面檢視次數的百分比摘要數字。 |
| **[!UICONTROL 頁面逗留時間]** | [橫條圖](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md)視覺效果可顯示在此頁面逗留的時間。 |
| **[!UICONTROL 單頁造訪次數]** | [摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)會顯示此頁面是唯一造訪的頁面檢視次數。 |
| **[!UICONTROL 重新載入]** | 一個[摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，顯示重新載入期間維度專案出現的次數。 訪客重新整理瀏覽器是觸發重新載入的最常見方式。 |
| **[!UICONTROL 登入點]** | [摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，顯示指定的維度專案在造訪中被擷取為第一個值的次數。 |
| **[!UICONTROL 退出點]** | [摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)，顯示指定的維度專案在造訪中被擷取為最後一個值的次數。 |
| **[!UICONTROL 流程]** | 以選取的頁面為焦點的[流量](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)視覺效果。 您可以像在任何[流量](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)視覺效果中一樣深入鑽研資料。 |

{style="table-layout:auto"}

使用![編輯](/help/assets/icons/Edit.svg)來重新設定及重建面板。
