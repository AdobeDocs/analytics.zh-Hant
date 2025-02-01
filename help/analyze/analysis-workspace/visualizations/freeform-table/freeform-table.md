---
title: 自由表格
description: 自由表格是 Analysis Workspace 中資料分析的基礎
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 61%

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

在 Analysis Workspace 中，自由表格是互動式資料分析的基礎。您可以將各種[元件](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=zh-Hant)拖放至行和欄中，建立自訂表格供分析之用。放置每個元件後，表格會立即更新，以便您快速分析及深入探索。

## 建立簡單的自由表格

您會從空白的自由格式表格開始。

![空白的自由格式表格](assets/freeform-table-1.png)

如果您將&#x200B;**[!UICONTROL **&#x200B;造訪次數&#x200B;**]**&#x200B;量度拖曳至&#x200B;**[!UICONTROL **&#x200B;將量度拖曳至此（或任何其他元件）**]**，自由表格會自動填入您所選日曆期間的每日造訪次數。

![瀏覽自由表格](assets/freeform-table-2.png)

如果您接著卸除&#x200B;**[!UICONTROL **&#x200B;頁面&#x200B;**]**&#x200B;維度來取代&#x200B;**[!UICONTROL **&#x200B;天&#x200B;**]**&#x200B;維度欄，自由表格會自動反映每個頁面的造訪次數。

依頁面自由格式表格的![瀏覽次數](assets/freeform-table-3.png)

例如，您可以將&#x200B;**[!UICONTROL **&#x200B;行銷管道&#x200B;**]**&#x200B;維度拖放至&#x200B;**[!UICONTROL **&#x200B;類別：5 **]**&#x200B;列，以劃分&#x200B;**[!UICONTROL **&#x200B;類別：5 **]**&#x200B;頁面。

依頁面自由表格劃分![瀏覽次數](assets/freeform-table-4.png)


## 自動化表格

如上圖所示，建立表格的最快方式是直接將元件拖放至空白專案、面板或自由表格。 系統會自動以建議的格式為您建立自由表格。[觀看教學課程](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html?lang=zh-Hant)。

![](assets/automated-table.png)

## 自由表格產生器

如果您偏好先將數個元件新增至表格，然後再轉譯資料，則可啟用「自由表格產生器」。啟用產生器後，許多維度、劃分、量度和區段都可直接拖放使用，方便建立表格以供回答更複雜的問題。 資料不會即時更新，但當您按一下&#x200B;**[!UICONTROL 建置]**&#x200B;後，資料就會更新。

![](assets/table-builder.png)

## 表格互動

您可以透過多種方式與自由表格互動及自訂表格：

* **行**
   * 您可以調整專案的[檢視密度](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=zh-Hant)，在單一畫面中放入更多列。
   * 分頁之前，每個維度列最多可顯示 400 列。按一下「列」旁邊的數字，就能在頁面上顯示更多列。使用頁首的頁面箭頭，即可導覽至其他頁面。
   * 列可以依其他元件劃分。若要一次劃分許多列，只需選取多列，然後將下一個元件拖曳至選取的列上即可。進一步了解[劃分](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html?lang=zh-Hant)。
   * 您可以[篩選](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=zh-Hant)列，以顯示縮減的項目集。[「列設定」](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html?lang=zh-Hant)底下提供其他設定。

* **欄**
   * 元件可堆疊在欄內，以建立分段量度、跨標籤分析等等。
   * [欄設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html?lang=zh-Hant)底下可調整每個欄的檢視方式。
   * 您可善用[滑鼠右鍵選單](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html?lang=zh-Hant)執行數個動作。無論是在表格標頭、列或欄上按一下，選單都會提供不同動作。

## 匯出自由表格資料

深入了解 Analysis Workspace 的所有資料[匯出選項](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=zh-Hant)。

* 按一下右鍵 >**[!UICONTROL 「複製資料到剪貼簿」]**，即可匯出顯示的表格資料。如果已選取表格，此選項會顯示&#x200B;**[!UICONTROL 「複製選取項目到剪貼簿」]**。也可以使用 **Ctrl + C** 快捷鍵複製所選取的資料。
* 按一下右鍵 >**[!UICONTROL 「以 CSV 格式下載資料」]**，將顯示的表格資料下載為 CSV 檔案。如果已選取表格，此選項會顯示&#x200B;**[!UICONTROL 「以 CSV 格式下載選取項目」]**。
* 按一下滑鼠右鍵>「**[!UICONTROL 專案>以CSV格式下載專案]**」，最多可為選取的維度匯出50,000個維度專案。

深入了解 Analysis Workspace 的所有資料[匯出選項](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=zh-Hant)。

![](assets/export-options.png)

## 影片

自由格式表格建立器概觀：
>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [自由格式表格產生器概觀](https://video.tv.adobe.com/v/31318?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [自由格式表格篩選器](https://video.tv.adobe.com/v/23232?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [任意形狀表格總計](https://video.tv.adobe.com/v/29273?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]



