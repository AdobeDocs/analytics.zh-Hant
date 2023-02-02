---
description: 執行報表後，您可以自訂報表，以根據您的需求檢視和分析資料。您可以篩選報表資料、變更以圖形呈現資料的方式、變更日期精細度等等。
title: 自訂報表概觀
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 5a042fac-926e-4560-83bf-11f66ddb8273
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 91%

---

# 自訂報表概觀

{{ra-eol}}

執行報表後，您可以自訂報表，以根據您的需求檢視和分析資料。您可以篩選報表資料、變更以圖形呈現資料的方式、變更日期精細度等等。

## 建立自訂報表 {#task_BA6EACA3039C40AEA5605E1D8C76E646}

您可以將報表的目前設定儲存為可供所有使用者查看的新自訂報表。

<!-- 

t_reports_custom.xml

 -->

只有管理員可以建立自訂報表。建立自訂報表後，會將該報表新增至它所依據之報表旁邊的主報表功能表中。

建立自訂報表:

1. 執行報表並視需要進行。
1. 按一下&#x200B;**[!UICONTROL 「更多]** > **[!UICONTROL 建立自訂報表」]**。
1. 為報表命名，然後按一下&#x200B;**[!UICONTROL 「儲存」]**。

   確認名稱沒有和現有報表名稱重複。

>[!MORELIKETHIS]
>
>* [功能表自訂](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/customize-menus.html?lang=zh-Hant)


## 選擇日期或日期範圍 {#task_9BEF7D4D839A4748B76E8500D1406C34}

您可以選擇報表資料的時段。

<!-- 

t_reports_select_date.xml

 -->

您可以選擇特定日、週、月或年。您也可以執行比較報表。

當您使用擁有不同日期範圍的小報表開啟控制面板，並在「日曆」中選擇新的日期範圍時，變更會套用至控制面板中的所有小報表。

選擇日期範圍:

1. 執行報表。
1. 按一下右上角的日曆圖示。
1. 選擇日期。

   您可以：

   * 檢視天、月或年時段 (最多 3 個)。
   * 將游標拖過若干日期以選擇範圍。
   * 手動輸入日期。
   * 按一下月份名稱以選取月份。
   * 按一下&#x200B;**[!UICONTROL 選擇預設]**，選取預設日期。
   * 比較日期。

1. 按一下&#x200B;**[!UICONTROL 「執行報表」]**。

## 比較日期 {#task_95155C3700774B709F5FB81AE96B0824}

您可以使用日曆來比較兩個排名報表之間的日期。

<!-- 

t_reports_comparing_dates.xml

 -->

您無法比較趨勢報表之間的日期。

>[!NOTE]
>
>如果要在控制面板中比較重要量度的日期，您可使用兩個個別的請求，將資料提取到 [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html)。您可以在 Excel 中使用自訂公式來分析兩者之間的差異。

若要比較「Report &amp; Analytics」中排名報表之間的日期：

1. 執行報表。
1. 按一下右上角的日曆。
1. 按一下&#x200B;**[!UICONTROL 比較日期]**。
1. 選擇要使用的日期。
1. 按一下&#x200B;**[!UICONTROL 「執行報表」]**。

## 將百分比顯示為圖表 {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

您可以指定要將百分比顯示為報表表格還是圖形。

<!-- 

t_reports_graph_percent.xml

 -->

該視覺化同樣適用於控制面板報表。

若要將百分比顯示為報表表格中的圖形：

1. 執行支援百分比的報表，例如[!UICONTROL 頁面報表]。
1. 按一下&#x200B;**[!UICONTROL 百分比顯示為︰圖表]**。

## 標準化報表資料 {#task_8005B55E59BD479DA67BC618FF8BC94A}

<!-- 

t_reports_normalize.xml

 -->

執行完帶有比較日期或 A/B 比較的報表後，您可以標準化資料以顯示報表間的變更比例。備用資料集經調整可彌補所選日期中的差異，或不同流量的差異。

標準化報表資料:

1. 執行支援日期比較的報表。
1. 按一下&#x200B;**[!UICONTROL 「比較日期」]**，然後指定日期比較。
1. 按一下&#x200B;**[!UICONTROL 「執行報表」]**。
1. 按一下&#x200B;**[!UICONTROL 「標準化資料: 是」]**。

## 為報表選擇頁面 {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

若要從您網站的頁面中選取特定頁面以進行報表：

<!-- 

t_reports_select_page.xml

 -->

1. 產生報表，例如[!UICONTROL 頁面檢視報表] (**[!UICONTROL 「報表]** > **[!UICONTROL 網站量度]** > **[!UICONTROL 頁面檢視」]**)。
1. 按一下&#x200B;**[!UICONTROL 「選取頁面」]**&#x200B;連結。
1. 在[!UICONTROL 「選擇頁面」]上，選擇您想顯示的頁面。
1.  找到頁面。
1. 按一下&#x200B;**[!UICONTROL 「確定」]**。

## 比較報告套裝 {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

您可以在同一份報表中顯示來自兩個報表套裝的報表。

<!-- 

t_reports_compare_suites.xml

 -->

除了圖形化顯示之外，報表表格也提供百分比比較。可執行以下報表加以比較：

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

比較報告套裝:

1. 產生可讓您比較報表的報表。
1. 按一下&#x200B;**[!UICONTROL 網站比較]**&#x200B;連結。
1. 找到報告套裝。
1. 按一下&#x200B;**[!UICONTROL 「確定」]**。

## 指定報表精細度 {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

您可以每小時、每日、每週、每月、每季或每年檢視報表總計。

<!-- 

t_reports_granularity.xml

 -->

報表的時段會決定可用的精細度選項。例如，如果您已選定一天或兩天時間範圍，則只能選擇&#x200B;**[!UICONTROL 每小時]**。如果您已選定一年以上，則只能選擇&#x200B;**[!UICONTROL 每年]**&#x200B;精細度。

指定報表精細度:

1.  產生趨勢報表，例如&#x200B;**[!UICONTROL 「網站內容]** > **[!UICONTROL 頁面」]**。
1.  按一下&#x200B;**[!UICONTROL 檢視依據]**&#x200B;連結，然後按一下精細度。

## 執行星期幾報表 {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

您可以在具體某個日子執行報表，例如指定日期範圍內的每週一。

<!-- 

t_reports_day_of_week.xml

 -->

此功能僅適用於以「週」或「天」日期範圍篩選的趨勢報表。

要執行一週中的某天報表:

1. 在指定日期範圍執行趨勢報表。
1. 按一下&#x200B;**[!UICONTROL 一週中的某天]**&#x200B;連結，然後按一下某一天。

## 「在工作區中試用」按鈕 {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

按一下在報表頂端的&#x200B;**[!UICONTROL 「在工作區中試用」]**&#x200B;按鈕會載入與 Analysis Workspace 相同的報表。

<!-- 

try_in_workspace.xml

 -->

現在，大部分「Report &amp; Analytics」中的報表已包含一個「在工作區中試用」按鈕，可讓您在 Analysis Workspace 中重新產生目前的檢視，以便做進一步自訂。

目前，此按鈕僅限擁有 Analysis Workspace 完整權限的使用者名稱可以使用。

如需自訂報表所有方式的詳細資訊，請參閱 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 指南。
