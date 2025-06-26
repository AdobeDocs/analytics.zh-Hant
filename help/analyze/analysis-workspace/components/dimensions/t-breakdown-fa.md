---
description: 在 Analysis Workspace 中劃分維度和維度項目。
keywords: Analysis Workspace
title: 劃分維度
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: ed4d7bb2b3ba290da575ce18fa6ba62d6b2e9751
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 59%

---

# 在工作區中劃分維度

您可以根據特定需求，以無限方式劃分資料；使用相關量度、維度、區段、時間表及其他分析劃分值來建立查詢。

1. 在[自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)中，從一或多個選取資料列的內容功能表中，選取&#x200B;**[!UICONTROL 劃分]** ![V形右側](/help/assets/icons/ChevronRight.svg)。

   ![顯示從選取專案建立警示的步驟結果。](assets/breakdown.png)

1. 從子功能表中選取&#x200B;**[!UICONTROL 維度]**、**[!UICONTROL 量度]**、**[!UICONTROL 區段]**&#x200B;或&#x200B;**[!UICONTROL 日期範圍]**，然後選取專案。 或只是在&#x200B;**[!UICONTROL *搜尋&#x200B;*]**欄位中搜尋元件。

您可以跨所選時段，依維度項目或客群細分群體來劃分量度。您也可以更深入鑽研至更詳細的層級。

>[!NOTE]
>
>表格中顯示的劃分數目上限為 200。匯出劃分時，此限制會提高。

## 依位置劃分

依預設，劃分會固定至靜態列專案。 例如，想像您根據行銷管道劃分前 3 個頁面維度項目 (「首頁」、「搜尋結果」、「結帳」)。接著，您離開專案，兩週後再回來。再次開啟專案時，前 3 個頁面已變更，現在「首頁」、「搜尋結果」和「結帳」是前 4 到 6 個頁面。您的「行銷管道」劃分預設仍會顯示在「首頁」、「搜尋結果」和「結帳」下方，即使它們現在位於第4到6列。

相反地，**依位置**&#x200B;劃分，一律劃分前3個專案，無論前3個專案是什麼。 請參考範例，當您重啟專案時，行銷管道劃分將與表格中的前 3 頁面相連結。而非「首頁」、「搜尋結果」和「結帳」，它們現在位於第4-6列。 請參閱[資料列設定](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)設定此設定的方式。



## 將歸因模型套用到資料劃分

表格中的任何劃分也可套用任何歸因模型。此歸因模型可與父欄相同或不同。舉例來說，您可以在「行銷管道」維度中分析線性訂單，但將「U 形訂單」套用至管道中的特定追蹤代碼。若要編輯套用到劃分的歸因模型，請將滑鼠移到劃分模型上，然後選取&#x200B;**[!UICONTROL 編輯]**。

![顯示劃分設定的訂單歸因比較](assets/breakdown-attribution.png)

這是將歸因模型套用至劃分或編輯劃分時的預期行為：

* 如果在沒有其他歸因時套用歸因，該歸因將套用於整個欄樹。

* 如果在套用了歸因後新增劃分，則將對新增的給定劃分使用預設值 (如果該維度具有預設值)。否則將使用父欄的劃分。某些維度具有預設配置。例如，「時間」維度和「反向連結」使用「同一次接觸」。「產品」維度使用「上次接觸」。其他維度沒有預設值，將使用父欄配置。

* 如果欄樹中已有歸因，則變更歸因只會影響正在編輯的歸因。

>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace中的Dimension](https://video.tv.adobe.com/v/23971?quality=12&learn=on){target="_blank"}。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [Dimension劃分](https://video.tv.adobe.com/v/23969?quality=12&learn=on){target="_blank"}。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [新增維度和量度](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"}。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [在自由格式表格中使用維度](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"}。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [依位置劃分的Dimension](https://video.tv.adobe.com/v/24033){target="_blank"}。


>[!ENDSHADEBOX]



<!--
# Break down dimensions

Break down dimensions and dimension items in Analysis Workspace.

Break down your data in unlimited ways for your specific needs; build queries using relevant metrics, dimensions, segments, time lines, and other analysis breakdown values.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table.
1. In the data table, right-click a line item and select **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Step Result](assets/fa_data_table_actions.png)

   You can break down metrics by dimension items or audience segments across selected time periods. You can also drill down further to a more granular level.

   >[!NOTE]
   >
   >The number of breakdowns to show in the table is limited to 200. This limit will increase for exporting breakdowns.

## Apply attribution models to breakdowns

Any breakdown within a table can also have any attribution model applied to it. This attribution model can be the same or different from the parent column. For example, you can analyze linear Orders on your Marketing Channels dimension but apply U-Shaped Orders to the specific tracking codes within a Channel. To edit the attribution model applied to a breakdown, hover over the breakdown model and click **[!UICONTROL Edit]**:

![Breakdown settings](assets/breakdown_settings.png)

This is the expected behavior when applying attribution models to breakdowns or editing them:

* If you apply an attribution when no other attributions exist, then the attribution applies to the entire column tree.

* If you add a breakdown after an attribution has been applied, it will use the default for the given breakdown that was added, if that dimension has a default. Otherwise it will use the breakdown from the parent column. Some dimensions have a default allocation.  For example, [!UICONTROL Time] dimensions and [!UICONTROL Referrer] use [!UICONTROL Same Touch]. The [!UICONTROL Product] dimension uses [!UICONTROL Last Touch]. Other dimensions don't have a default, and will use the parent column allocation.

* If there are already attributions in the column tree, changing the attribution only impacts the one you are editing.

## Videos


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding dimensions and metrics to your project in Analysis Workspace](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Working with dimensions in a Freeform Table](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [dimension breakdowns by position](https://video.tv.adobe.com/v/24033?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


-->