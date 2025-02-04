---
title: 自由表格
description: 自由表格是 Analysis Workspace 中資料分析的基礎
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
source-git-commit: bb3e8b030af78f0d7758b4cff41d66f20695e11e
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 25%

---

# 自由表格 {#freeform-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="自由表格"
>abstract="建立一個空白的自由格式表格視覺效果，您可以使用維度、區段、量度和日期範圍進一步建置。您可以使用自由格式表格作為其他視覺效果的基礎。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文會在_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中記錄自由格式表格視覺效果。_<br/>_檢視此文章的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版本的[自由格式表格](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/freeform-table)。_

>[!ENDSHADEBOX]


在Analysis Workspace中，![表格](/help/assets/icons/Table.svg) **[!UICONTROL 自由表格]**&#x200B;視覺效果是互動式資料分析的基礎。 您可以將各種[元件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)拖放至行和欄中，建立自訂表格供分析之用。放置每個元件後，表格會立即更新，以便您快速分析及深入探索。

![自由表格，以列與欄顯示元件，包含多個網頁的造訪與線上訂單。](assets/opening-section.png)

若要建立和設定[!UICONTROL 自由格式表格]：

* 新增![表格](/help/assets/icons/Table.svg) **[!UICONTROL 自由表格]**&#x200B;視覺效果。 請參閱[將視覺效果新增至面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

## 自動化表格

若要建立表格，直接將元件拖放至空白專案、面板或自由表格中是最快的方法。系統會以建議的格式為您建立自由表格。 [觀看教學課程](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace)。

![含有造訪元件的新面板已拖放到工作空間。](assets/automated-table.png)

## 自由表格產生器

如果您偏好先將數個元件新增至表格，然後再轉譯資料，您可以選取&#x200B;**[!UICONTROL 啟用表格產生器]**。 啟用產生器後，您可以拖放維度、劃分、量度和篩選器來建立可回答更複雜問題的表格。 選取&#x200B;**[!UICONTROL 組建]**&#x200B;後，資料會更新。

![顯示](assets/table-builder.png)的自由格式表格產生器

## 互動

您可以透過多種方式與自由表格互動及自訂表格：

### 篩選和排序

* 您可以[篩選及排序資料表中的資料](filter-and-sort.md)。

### 「行」

* 您可以使用![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg)，從一或多個資料列快速[建立新的視覺效果](../freeform-analysis-visualizations.md#visualize)。
* 您可以調整專案的[檢視密度](/help/analyze/analysis-workspace/build-workspace-project/view-density.md)，在單一畫面中放入更多列。
* 分頁之前，每個維度列最多可顯示 400 列。選取第一個欄標題中&#x200B;**[!UICONTROL 列]**&#x200B;旁邊的數字，以在頁面上顯示更多列。 在第一欄標題中使用![V形右側](/help/assets/icons/ChevronRight.svg)瀏覽至其他頁面。
* 您可以依其他元件來劃分列。 若要一次劃分許多列，請選取多列，然後將下一個元件拖曳至選取的列上方。 進一步了解[劃分](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。
* 您可以[篩選](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)列，以顯示縮減的項目集。[「列設定」](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)底下提供其他設定。

### 欄

* 元件可堆疊在欄內，以建立篩選量度、跨索引標籤分析等等。
* [欄設定](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)底下可調整每個欄的檢視方式。
* 透過[內容功能表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)有數個動作可供使用。 功能表會根據您選取的表格標題、列或欄提供不同的動作。


## 設定

選取![設定](/help/assets/icons/Setting.svg)以顯示&#x200B;**[!UICONTROL 資料表設定]**。 下列特定視覺效果[設定](../freeform-analysis-visualizations.md#settings)可供使用：

### 資料來源

| 選項 | 說明 |
|---|---|
| **[!UICONTROL 連結的視覺效果]**。 | 列出所有連結的視覺效果。 |
| **[!UICONTROL 顯示資料來源]** | 取消勾選後，Workspace中會隱藏可作為視覺效果資料來源的自由表格。 |

### 設定

| 選項 | 說明 |
|---|---|
| **[!UICONTROL 對齊各欄日期，讓所有開始日期在同一列]** | 對齊或不對齊各欄日期，讓所有開始日期在同一列。 |


## 內容選單

視覺效果標題中有下列[內容功能表](../freeform-analysis-visualizations.md#context-menu)選項：

| 選項 | 說明 |
| --- | --- |
| **[!UICONTROL 插入複製的視覺效果]**n | 將複製的視覺效果貼上（插入）專案內另一個位置或完全不同的專案中。 |
| **[!UICONTROL 將資料複製到剪貼簿]** | 將資料從視覺效果複製到剪貼簿。 |
| **[!UICONTROL 將選取專案複製到剪貼簿]** | 將視覺效果中的選取範圍複製到剪貼簿。 |
| **[!UICONTROL 將專案下載為CSV檔（*維度名稱*）]** | 立即將視覺效果的維度專案（最多50,000個）下載到您的本機裝置。 所選維度最多50,000個維度專案。 |
| **[!UICONTROL 複製視覺效果]** | 複製視覺效果，以便將視覺效果插入專案內另一個位置或完全不同的專案中。 |
| **[!UICONTROL 下載資料CSV]** | 立即將視覺效果顯示的資料下載至本機裝置。 |
| **[!UICONTROL 重複的視覺效果]** | 將視覺效果精確複製。 |
| **[!UICONTROL 編輯描述]** | 新增（或編輯）視覺效果的文字說明。 請參閱[文字](../text.md)。 |
| **[!UICONTROL 取得視覺效果連結]** | 直接複製並共用視覺效果的連結。 共用連結對話方塊會顯示連結。 選取「複製」 ，將連結複製到剪貼簿。 |
| **[!UICONTROL 重新開始]** | 刪除目前視覺效果的設定，以便您從頭開始重新設定。 |



## 影片

>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [自由格式表格產生器概觀](https://video.tv.adobe.com/v/31318?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [自由格式表格篩選器](https://video.tv.adobe.com/v/23232?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [任意形狀表格總計](https://video.tv.adobe.com/v/29273?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


>[!MORELIKETHIS]
>
>[將視覺效果新增至面板](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[視覺效果設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[視覺效果內容功能表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>



