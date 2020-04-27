---
description: 執行報表後，您可以自訂報表，以根據您的需求檢視和分析資料。您可以篩選報告資料、變更以圖形呈現資料的方式、變更日期精細度等等。
title: 自訂報表概觀
topic: Reports and analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 自訂報表概觀

執行報表後，您可以自訂報表，以根據您的需求檢視和分析資料。您可以篩選報告資料、變更以圖形呈現資料的方式、變更日期精細度等等。

## 建立自訂報告 {#task_BA6EACA3039C40AEA5605E1D8C76E646}

說明如何將報告的目前設定儲存成可供所有使用者檢視之新自訂報告的步驟。

<!-- 

t_reports_custom.xml

 -->

只有管理員可以建立自訂報告。建立自訂報告後，會將該報告新增至它所依據之報告旁邊的主報告功能表中。

**要建立自訂報告**

1. 執行報告並視需要進行。
1. 按一下 **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Name the report, then click **[!UICONTROL Save.]**

   確保名稱沒有和現有報告名稱重複。

>[!MORELIKETHIS]
>
>* [功能表自訂](https://marketing.adobe.com/resources/help/zh_TW/reference/customize_menus.html)


## 選擇日期或日期範圍 {#task_9BEF7D4D839A4748B76E8500D1406C34}

說明如何為報告資料選擇時段的步驟。

<!-- 

t_reports_select_date.xml

 -->

您可以選擇特定日、週、月或年。您也可以執行比較報告。

當您使用擁有不同日期範圍的小報告開啟控制面板，並在「日曆」中選擇新的日期範圍時，變更會套用至控制面板中的所有小報告。

**要選擇日期範圍**

1. 執行報告。
1. 按一下右上角的日曆圖示。
1. 選擇日期。

   您可以：

   * 檢視天、月或年時段 (最多 3 個)。
   * 將游標拖過若干日期以選擇範圍。
   * 手動輸入日期。
   * 按一下月份名稱以選取月份。
   * 按一 **[!UICONTROL Select Preset]** 下以選取預設日期。
   * 比較日期。

1. 按一下 **[!UICONTROL Run Report]**.

## 比較日期 {#task_95155C3700774B709F5FB81AE96B0824}

說明如何使用日曆來執行排名報告間之日期比較的步驟。

<!-- 

t_reports_comparing_dates.xml

 -->

您無法比較趨勢報告之間的日期。

>[!NOTE]如果要在控制面板中比較重要度量的日期，您可使用兩個個別的請求，將資料提取到 [Report Builder](https://marketing.adobe.com/resources/help/zh_TW/arb/)。您可以在 Excel 中使用自訂公式來分析兩者之間的差異。

若要比較「Report &amp; Analytics」中排名報表之間的日期：

1. 執行報告。
1. 按一下右上角的日曆。
1. 按一下 **[!UICONTROL Compare Dates]**.
1. 選擇要使用的日期。
1. 按一下 **[!UICONTROL Run Report]**.

## 將百分比顯示為圖表 {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

說明如何指定是否要將報告表格中的百分比顯示為圖表的步驟。

<!-- 

t_reports_graph_percent.xml

 -->

該視覺化同樣適用於控制面板報告。

1. Run a report that supports percentages, such as a [!UICONTROL Pages Report].
1. 按一下 **[!UICONTROL Percent Shown As: Graph]**.

## 標準化報告資料 {#task_8005B55E59BD479DA67BC618FF8BC94A}

說明如何標準化報告資料的步驟。

<!-- 

t_reports_normalize.xml

 -->

執行完帶有比較日期或 A/B 比較的報告後，您可以標準化資料以顯示報告間的變更比例。備用資料集經調整可彌補所選日期中的差異，或不同流量的差異。

**要標準化報告資料**

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

說明如何將兩個報告套裝的報告顯示在同一個報告中的步驟。

<!-- 

t_reports_compare_suites.xml

 -->

除了圖形化顯示之外，報告表格也提供百分比比較。以下報告可執行比較：

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

說明如何以每小時、每日、每週、每月、每季或每年為基礎檢視報告總計的步驟。

<!-- 

t_reports_granularity.xml

 -->

報告的時段會決定可用的精細度選項。For example, you can select only **[!UICONTROL Hourly]** if you have a one or two day time frame selected. You can select only **[!UICONTROL Yearly]** granularity if you have more than one year selected.

**要指定報告精細度**

1. 產生趨勢報表，例如 **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Click the **[!UICONTROL View by]** link, then click a granularity.

## 執行星期幾報告 {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

說明如何針對一週中的特定日執行報告 (例如在指定日期範圍內的每個星期一) 的步驟。

<!-- 

t_reports_day_of_week.xml

 -->

此功能僅適用於以「週」或「天」日期範圍篩選的趨勢報告。

1. 在指定日期範圍執行趨勢報告。
1. 按一下 **[!UICONTROL Day of Week]** 連結，然後按一下一天。

## 「在 Workspace 嘗試」按鈕{#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Clicking the **[!UICONTROL Try In Workspace]** button at the top of a report will load the same report in Analysis Workspace.

<!-- 

try_in_workspace.xml

 -->

現在，大部分「Report &amp; Analytics」中的報告已包含一個「在 Workspace 嘗試」按鈕，可讓您在 Analysis Workspace 中重新產生目前的檢視，以便做進一步自訂。

目前，此按鈕僅限擁有 Analysis Workspace 完整權限的使用者名稱可以使用。

如需自訂報告所有方式的詳細資訊，請參閱 [Analysis Workspace](https://marketing.adobe.com/resources/help/zh_TW/analytics/analysis-workspace/) 指南。
