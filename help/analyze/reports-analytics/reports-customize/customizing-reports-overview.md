---
description: 執行報表後，您可以自訂報表，以根據您的需求檢視和分析資料。 您可以篩選報表資料、變更以圖形呈現資料的方式、變更日期詳細程度等。
title: 自訂報表概觀
topic: Reports and analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 自訂報表概觀

執行報表後，您可以自訂報表，以根據您的需求檢視和分析資料。 您可以篩選報表資料、變更以圖形呈現資料的方式、變更日期詳細程度等。

## 建立自訂報告 {#task_BA6EACA3039C40AEA5605E1D8C76E646}

說明如何將報表的目前設定儲存為新自訂報表，以供所有使用者檢視的步驟。

<!-- 

t_reports_custom.xml

 -->

只有管理員可以建立自訂報表。 當您建立自訂報表時，它會新增至其所依據之報表旁的主要報表功能表。

**若要建立自訂報表**

1. 執行報告並視需要進行。
1. 按一下 **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Name the report, then click **[!UICONTROL Save.]**

   確保名稱沒有和現有報告名稱重複。

>[!MORELIKETHIS]
>
>* [功能表自訂](https://marketing.adobe.com/resources/help/zh_TW/reference/customize_menus.html)


## 選擇日期或日期範圍 {#task_9BEF7D4D839A4748B76E8500D1406C34}

說明如何使用熱量的步驟，以選擇報表資料的時段。

<!-- 

t_reports_select_date.xml

 -->

您可以選取特定的日、周、月或年。 您也可以執行比較報表。

當您開啟含有不同日期範圍之小報表的控制面板時，可以在日曆中選擇新的日期範圍。 這些變更會套用至控制面板中的所有小報表。

**若要選擇日期範圍**

1. 執行報告。
1. 按一下右上角的日曆圖示。
1. 選擇日期。

   您可以：

   * 檢視日、月或年期（最多3個）。
   * 跨日期拖曳游標以選取範圍。
   * 人工輸入日期。
   * 按一下月份名稱以選取月份。
   * 按一 **[!UICONTROL Select Preset]** 下以選取預設日期。
   * 比較日期。

1. 按一下 **[!UICONTROL Run Report]**.

## 比較日期 {#task_95155C3700774B709F5FB81AE96B0824}

說明如何使用日曆來比較排名報表之間的日期的步驟。

<!-- 

t_reports_comparing_dates.xml

 -->

您無法比較趨勢報表之間的日期。

>[!NOTE]如果要在控制面板中比較重要度量的日期，您可使用兩個個別的請求，將資料提取到 [Report Builder](https://marketing.adobe.com/resources/help/zh_TW/arb/)。您可以在 Excel 中使用自訂公式來分析兩者之間的差異。

若要比較「Report &amp; Analytics」中排名報表之間的日期：

1. 執行報告。
1. 按一下右上角的日曆。
1. 按一下 **[!UICONTROL Compare Dates]**.
1. 選擇要使用的日期。
1. 按一下 **[!UICONTROL Run Report]**.

## 將百分比顯示為圖表 {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

說明如何指定是否將百分比顯示在報表表格中的圖形的步驟。

<!-- 

t_reports_graph_percent.xml

 -->

此視覺化功能也可用於控制面板小報表。

1. Run a report that supports percentages, such as a [!UICONTROL Pages Report].
1. 按一下 **[!UICONTROL Percent Shown As: Graph]**.

## 標準化報告資料 {#task_8005B55E59BD479DA67BC618FF8BC94A}

說明如何標準化報表資料的步驟。

<!-- 

t_reports_normalize.xml

 -->

在執行具有比較日期的報表或A/B比較後，您可以標準化資料以顯示報表之間的變更百分比。 次要資料集會加以調整，以補償所選天數或不同流量的差異。

**要標準化報表資料**

1. 執行支援日期比較的報告。
1. 按一 **[!UICONTROL Compare Dates]**&#x200B;下，然後指定您的日期比較。
1. 按一下 **[!UICONTROL Run Report]**.
1. 按一下 **[!UICONTROL Normalize Data: Yes]**.

## 為報告選擇頁面 {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

說明如何從網站頁面中為報告選擇一個特定頁面的步驟。

<!-- 

t_reports_select_page.xml

 -->

1. 產生報表，例如 [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Page Views]**)。
1. Click the **[!UICONTROL Selected Page]** link.
1. On [!UICONTROL Choose Page], select the pages you want to display.
1.  找到頁面。
1. 按一下 **[!UICONTROL OK.]**

## 比較報告套裝 {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

說明如何在相同報表中顯示兩個報表套裝報表的步驟。

<!-- 

t_reports_compare_suites.xml

 -->

除了圖形顯示外，報表表格還提供百分比比較。 以下報告可執行比較：

* 網站內容
* 行動
* 流量來源
* 促銷活動
* 產品
* 訪客保留率
* 訪客資料
* 自訂轉換
* 自訂流量
* 目標
* 調查

**比較報告套裝**

1. 產生可讓您比較報告的報告。
1. Click the **[!UICONTROL Compare to Site]** link.
1. 找到報告套裝。
1. 按一下 **[!UICONTROL OK.]**

## 指定報告精細度 {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

說明如何以每小時、每日、每週、每月、每季或每年為基礎來檢視報表總計的步驟。

<!-- 

t_reports_granularity.xml

 -->

報表的時段會決定哪些詳細程度選項可用。 例如，您只能在選取 **[!UICONTROL Hourly]** 一或兩天時間範圍時選取。 如果您已選取 **[!UICONTROL Yearly]** 超過一年，則只能選取詳細程度。

**若要指定報表詳細程度**

1. 產生趨勢報表，例如 **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Click the **[!UICONTROL View by]** link, then click a granularity.

## 執行星期幾報告 {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

說明如何在一週中的特定日（例如指定日期範圍內的每個星期一）執行報表的步驟。

<!-- 

t_reports_day_of_week.xml

 -->

此功能僅適用於以「周」或「日」日期範圍篩選的趨勢報表。

1. 在指定日期範圍執行趨勢報告。
1. 按一下 **[!UICONTROL Day of Week]** 連結，然後按一下一天。

## 「在 Workspace 嘗試」按鈕{#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

按一 **[!UICONTROL Try In Workspace]** 下報表頂端的按鈕，將會在分析工作區中載入相同的報表。

<!-- 

try_in_workspace.xml

 -->

「報告與分析」中的大部分報表現在都包含「在工作區中試用」按鈕，可讓您在分析工作區中重制目前的檢視，以進一步自訂。

目前，只有在您的使用者名稱具有分析工作區的完整權限時，才可使用此按鈕。

如需自訂報表的所有方式的詳細資訊，請參閱分析工 [作區指南](https://marketing.adobe.com/resources/help/zh_TW/analytics/analysis-workspace/) 。
