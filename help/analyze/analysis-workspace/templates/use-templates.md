---
description: 概述如何在Analysis Workspace中使用範本。
title: 使用範本
feature: Analysis Workspace
role: User, Admin
hide: true
hidefromtoc: true
exl-id: 9e5d1b35-e2b3-4fa5-af12-67bb913675bc
source-git-commit: 547983e17edabcc1efc6354b5a2d2df7f521a354
workflow-type: tm+mt
source-wordcount: '9832'
ht-degree: 70%

---

# 使用範本

Analysis Workspace中的範本（或公司範本）可快速深入分析最常見的報表案例。 以下是您可以使用範本回答的一些問題範例：

* 多少訪客瀏覽您的網站
* 多少訪客是獨特訪客 (僅計算一次)
* 他們如何來到站點 (例如跟隨連結到達站點，或直接到達)
* 搜尋站點內容時所用的關鍵字
* 在指定網頁或整個站點上逗留的時間
* 訪客點按的連結，以及離開網站的時間
* 產生收入或轉換事件的最有效行銷管道
* 訪客花費在觀看視訊的時間
* 他們用來造訪網站的瀏覽器和裝置

下列資訊說明如何從Analysis Workspace的[!UICONTROL 範本]索引標籤存取及使用範本。

## 存取並執行範本

1. 在 Analysis Workspace 中，選取「[!UICONTROL **工作區**]」標籤。

   <!--update screenshot -->

   ![「報告」標籤](assets/view-prebuilt-templates.png)

1. 在&#x200B;[!UICONTROL **範本**]&#x200B;區段中，選取下列其中一個標籤：

   * **[!UICONTROL Adobe範本]**：顯示Adobe提供的所有範本。

   * **[!UICONTROL _login_company_name _範本]**：顯示已為您的組織建立的所有公司範本。

     公司範本只能由管理員建立。 如需有關如何建立公司範本的詳細資訊，請參閱[建立和管理範本](/help/analyze/analysis-workspace/reports/create-company-reports.md)。

1. 使用下列任一選項來變更您檢視可用範本的方式：

   * 選取欄檢視![欄檢檢視示](assets/column-view-icon.png)或卡片檢視![卡片檢檢視示](assets/card-view-icon.png)圖示，選擇是在欄檢視或卡片檢視中檢視範本。

   * 使用卡片檢視![卡片檢檢視示](assets/card-view-icon.png)時，請從下列排序順序中選擇： **[!UICONTROL 最近使用]**、**[!UICONTROL 最受歡迎]**、**[!UICONTROL 字母順序]**、**[!UICONTROL 類別]**。

1. 在搜尋欄位中，開始輸入您要尋找的範本名稱，然後從範本清單中選取它。 您也可以依據prop、eVar和事件編號來搜尋範本清單。<!-- still true? -->

   或

   選取您要檢視的範本類別，然後從範本清單中選取範本。

   >[!TIP]
   >
   >若要使用方向鍵瀏覽選單，請按正斜線鍵 (/)，然後按向下鍵。按Enter載入選取的範本。

   如需可用的範本清單，請參閱下方的[可用的範本](#available-reports)區段。

## 根據範本建立專案 {#use-reports}

範本可能並不完全符合您的需求，但可讓您關閉。 在這些情況下，您可以使用範本作為起點，然後進行自訂以最符合您的特定目的。

如果您在進行變更後離開範本，系統會提示您儲存或捨棄變更。 將變更儲存到範本會將範本儲存為新專案。

若要自訂範本並將其儲存為專案：

1. 在 Adobe Analytics 中，選取「[!UICONTROL **工作區**]」索引標籤。

1. 選取&#x200B;[!UICONTROL **範本**]&#x200B;索引標籤。

1. 選取您要檢視的範本。 例如，在&#x200B;[!UICONTROL **最受歡迎**]&#x200B;下，選取&#x200B;[!UICONTROL **頁面**]&#x200B;範本。

   ![頁面報告](assets/pages-report.png)

1. Analysis Workspace中顯示的「頁面」範本會顯示兩個[視覺效果](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) （[橫條圖](/help/analyze/analysis-workspace/visualizations/bar.md)和[摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)）以及一個[自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 使用的量度為發生次數。
1. 執行以下任一操作：

   * 檢視範本。
   * 將一或多個區段拖曳到頂部的「區段」放置區。例如，拖曳「[!UICONTROL **Mobile 客戶**]」區段，然後檢視結果。
   * 前往右上方的行事暦，變更日期範圍。
   * 新增維度劃分、拖曳其他量度，且通常會根據您的需求自訂範本。

1. （選擇性）選取&#x200B;[!UICONTROL **專案**] > [!UICONTROL **儲存**]，將範本儲存為專案。

   範本會儲存為新專案，不會修改現有範本。 如需有關儲存專案的詳細資訊，請參閱[儲存專案](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)。

## 可用的範本

若要存取所有可用的預先建立範本：

1. 在Adobe Analytics中，選取&#x200B;[!UICONTROL **Workspace**]&#x200B;標籤，然後選取&#x200B;[!UICONTROL **範本**]&#x200B;標籤。

   預先建立的範本會依類別組織。

   <!--add screenshot-->

1. 選取類別以檢視其中的範本。

   以下各節對應於可用的類別，並提供每個範本的相關資訊。

   * [[！UICONTROL ](#most-popular)

   * [[！UICONTROL ](#engagement)

### 最受歡迎 {#most-popular}

<!--contextual help is in the CJA docs-->

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **訓練教學課程**] | 瞭解常用的Analysis Workspace術語和建立第一個分析的步驟 |
| [!UICONTROL **頁面**] | <!--duplicated in Engagement section--> 找出最受歡迎和最不受歡迎頁面。 <p>**這有助於您**&#x200B;更加了解您的客群，以及他們最感興趣的資訊類型。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如調整頁面中繼資料來提高瀏覽數較少之頁面的可見度，或花時間改善瀏覽數最多之頁面的內容。</p><p>此範本使用[頁面維度](/help/components/dimensions/page.md)和[頁面檢視量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **頁面檢視**] | <!--duplicated in Engagement section--> 檢視頁面總瀏覽數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站上的流量隨時間可能增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前與發起後的網站流量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期流量。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[頁面檢視量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **造訪數**] | <!--duplicated in Engagement section--> 檢視造訪總次數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站上的流量隨時間可能增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前與發起後的網站流量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期流量。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[造訪量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **訪客**] | <!--duplicated in Engagement section--> 檢視不重複訪客總數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站的觸及範圍和客群規模，隨時間或與先前時期相比增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前和發起後的不重複訪客，評估最近發起之行銷活動是否成功吸引新使用者造訪網站。或者您可以比較逐年的假期期間造訪網站的人數。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[不重複訪客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **關鍵量度**] | <!--duplicated in Engagement section--> 檢視以並排方式顯示頁面瀏覽數、造訪次數與不重複訪客量度的報告。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;比較這些重要量度，更全面地了解造訪網站的不重複訪客數量、頁面造訪次數，以及工作階段數量。</p><p>**根據您所瞭解的情況，您可**&#x200B;執行任何數量的工作，例如評估每個人在指定的一週或一個月內造訪網站時檢視的平均頁數，以及在一年中的特定時間或在執行行銷活動之前和之後的變化。 </p><p>此範本使用[天維度](/help/components/dimensions/day.md)、[頁面檢視量度](/help/components/metrics/page-views.md)、[造訪量度](/help/components/metrics/visits.md)以及[不重複訪客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **網站區域**] | 檢視您網站上最受歡迎或績效最好的區段。 <p>**這有助於您**&#x200B;更加了解使用者最常造訪網站的哪些區段。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估您提供的哪些產品或服務最能引起人們興趣。</p> <p>此範本使用[網站區段維度](/help/components/dimensions/site-section.md)和[造訪量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **下一頁和上一頁**] | 檢視人們在造訪特定地點之前或之後最常去的地方。 <p>**這有助於您**&#x200B;了解流量如何從特定頁面移到網站的其他部分，並了解人們到達特定頁面的路徑。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估是否能夠將頁面設計或版面最佳化，引導人們前往更理想的頁面，例如購買或留下評論的頁面。或者評估目前頁面上的資訊，是否可能為從先前頁面到達這裡的人們提供所尋找的方向或動作。或者您可以評估那些並未像先前頁面一樣出現的頁面，其與目前頁面之間的連結是否需要更加顯眼。</p><p>此範本使用[下一個或上一個專案面板](/help/analyze/analysis-workspace/c-panels/next-previous.md)。</p> |
| [!UICONTROL **行銷活動（追蹤代碼）**] | 檢視將流量導向您的網站效果最好的連結。 <p>**這有助於您**&#x200B;更加了解在造訪您的網站時，哪些追蹤程式碼 (以及與其相關的連結) 最常被使用。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對在網站上新增連結的位置調整相關策略。</p><p>此範本使用[追蹤代碼維度](/help/components/dimensions/tracking-code.md)和[造訪量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **產品**] | 按照產品檢視訂單數目。會顯示一段期間內的資料。 <p>**這有助於您**&#x200B;了解哪些產品的需求量最高或最低。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如調整您的行銷策略推銷高績效產品，或是改善或停止績效不佳的產品。您也可以根據資料分析來調整產品庫存。</p><p>此範本使用[產品維度](/help/components/dimensions/product.md)和[訂單量度](/help/components/metrics/orders.md)。</p> |
| [!UICONTROL **上次接觸管道**] | 檢視訪客在參與期間 (預設為 30 天) 符合的最新行銷管道。<p>**這有助於您**&#x200B;了解哪些行銷管道最能有效地吸引人們造訪您的網站並成功轉換為客戶。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如分配更多資源給績效好的管道，或分配較少資源給績效不佳的管道。</p><p>此範本使用[上次接觸管道維度](/help/components/dimensions/last-touch-channel.md)和[不重複訪客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **上次接觸管道詳細資料**] | 檢視訪客在參與期間 (預設為 30 天) 符合的最新行銷管道的詳細資訊。<p>**這不僅有助於您**&#x200B;了解哪些行銷管道最能有效地吸引人們造訪您的網站並成功轉換為客戶，還可以了解這些行銷管道的詳細資訊。例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來瞭解他們使用了哪個搜尋引擎，或搜尋了哪個關鍵字。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如分配更多資源給績效好的管道，或分配較少資源給績效不佳的管道。</p><p>此範本使用[上次接觸管道詳細資料維度](/help/components/dimensions/last-touch-detail.md)和[不重複訪客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **收入**] | 檢視所有訂單中所購買產品的金額。會顯示一段期間內的資料，並與先前的期間進行比較。<p>**這有助於您**&#x200B;了解收入隨時間增加或減少的情況。您可以將這個量度與任何維度結合，以了解哪些維度項目對收入有貢獻。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據先前的趨勢預測未來的收入。您還可以新增另一個維度，例如追蹤程式碼維度，以了解哪些行銷活動所產生的收入最多。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[收入量度](/help/components/metrics/revenue.md)。</p> |
| [!UICONTROL **訂購**] | 檢視購買事件總數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解人們對您的產品和服務之興趣，隨時間而增加或減少的情況。您可以應用區段來了解哪些客戶或地區的訂單最多，以及這些訂單隨時間所呈現的趨勢。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如透過比較行銷活動發起前和發起後的訂單量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期訂單量。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[訂單量度](/help/components/metrics/orders.md)。</p> |
| [!UICONTROL **件數**] | 檢視所有訂單中購買的單位總數。會顯示一段期間內的資料，並與先前的時段進行比較。 <p>**這有助於您**&#x200B;更加了解單位銷售量隨時間增加或減少的情況。您可以套用區段來了解哪些客戶或地區購買的單位最多，以及這些單位銷售量隨時間呈現的趨勢分析。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如比較行銷活動發起前與發起後的單位銷售量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期期間單位銷售量。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[單位量度](/help/components/metrics/units.md)。</p> |

### 參與 {#web-engagement}

<!--contextual help is in the CJA docs-->

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **關鍵量度**] | <!--duplicated in Most popular section--> 檢視以並排方式顯示頁面瀏覽數、造訪次數與不重複訪客量度的報告。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;比較這些重要量度，更全面地了解造訪網站的不重複訪客數量、頁面造訪次數，以及工作階段數量。</p><p>**根據您所瞭解的情況，您可**&#x200B;執行任何數量的工作，例如評估每個人在指定的一週或一個月內造訪網站時檢視的平均頁數，以及在一年中的特定時間或在執行行銷活動之前和之後的變化。 </p><p>此範本使用[天維度](/help/components/dimensions/day.md)、[頁面檢視量度](/help/components/metrics/page-views.md)、[造訪量度](/help/components/metrics/visits.md)以及[不重複訪客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **頁面檢視**] | <!--duplicated in Most popular section-->檢視頁面總瀏覽數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站上的流量隨時間可能增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前與發起後的網站流量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期流量。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[頁面檢視量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **頁面**] | <!--duplicated in Most popular section-->找出最受歡迎和最不受歡迎頁面。 <p>**這有助於您**&#x200B;更加了解您的客群，以及他們最感興趣的資訊類型。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如調整頁面中繼資料來提高瀏覽數較少之頁面的可見度，或花時間改善瀏覽數最多之頁面的內容。</p><p>此範本使用[頁面維度](/help/components/dimensions/page.md)和[頁面檢視量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **造訪數**] | <!--duplicated in Most popular section-->檢視造訪總次數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站上的流量隨時間可能增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前與發起後的網站流量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期流量。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[造訪量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **訪客**] | <!--duplicated in Most popular section-->檢視不重複訪客總數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站的觸及範圍和客群規模，隨時間或與先前時期相比增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前和發起後的不重複訪客，評估最近發起之行銷活動是否成功吸引新使用者造訪網站。或者您可以比較逐年的假期期間造訪網站的人數。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[不重複訪客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **每次造訪逗留時間**] | 檢視訪客每次造訪期間平均在您網站上逗留的時間。會顯示一段期間內的資料，並與先前的時段進行比較。 <p>**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[每次造訪逗留時間（秒）量度](/help/components/metrics/time-spent-per-visit.md)。</p> |
| [!UICONTROL **事件之前時間**] | 檢視使用者在成功事件之前的平均逗留時間。 <p>**這有助於您**&#x200B;更加了解訪客執行其所需動作 (例如進行購買) 所花的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否讓訪客更能夠快速達到成功事件。</p><p>此範本使用[事件之前時間](/help/components/dimensions/time-prior-to-event.md)和[不重複訪客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **網站區域**] | <!--duplicated in Most popular section-->檢視您網站上最受歡迎或績效最好的區段。 <p>**這有助於您**&#x200B;更加了解使用者最常造訪網站的哪些區段。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估您提供的哪些產品或服務最能引起人們興趣。</p> <p>此範本使用[網站區段維度](/help/components/dimensions/site-section.md)和[造訪量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **即時**] | 檢視網站上目前收集的維度和量度。 <p>**這可協助您**&#x200B;更瞭解您網站上的趨勢。</p><p>**根據您所學到的內容，您可能**&#x200B;回應並主動管理您目前行銷內容和行銷活動的績效。</p> <p>此範本使用[即時報表](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)。</p> |
| [!UICONTROL **網頁內容使用量**] | 檢視使用者最常使用以及對使用者有吸引力的網頁內容。<p>**這有助於您**&#x200B;更加了解人們首次登入網站時會前往哪些部分、人們最常造訪網站的哪些區段，以及哪些頁面最有可能導致人們離開網站。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何數量的操作，例如評估網站上的哪些路徑會將人們引導至最重要的頁面，以及哪些頁面更可能將人們引導至遠離網站<!-- not sure about these takeaways... -->。</p> <p>此範本使用[頁面維度](/help/components/dimensions/page.md)和[頁面檢視量度](/help/components/metrics/page-views.md)、[造訪量度](/help/components/metrics/visits.md)、[不重複訪客量度](/help/components/metrics/unique-visitors.md)、[登入率量度](/help/components/metrics/entries.md)、[跳出率量度](/help/components/metrics/bounce-rate.md)、[退出率量度](/help/components/metrics/exits.md)以及[內容速度量度](/help/components/metrics/content-velocity.md)。 它也會針對登入、退出和頂端區段使用[流量視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)。</p> |
| [!UICONTROL **媒體內容使用量**] | 檢視使用者最常使用以及對使用者有吸引力的媒體內容。<p>**這有助於您**&#x200B;更加了解人們首次登入網站時會前往哪些部分、人們最常造訪網站的哪些區段，以及哪些頁面最有可能導致人們離開網站。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何數量的操作，例如評估網站上的哪些路徑會將人們引導至最重要的頁面，以及哪些頁面更可能將人們引導至遠離網站<!-- not sure about these takeaways... -->。</p> <p>此範本使用[頁面維度](/help/components/dimensions/page.md)和[頁面檢視量度](/help/components/metrics/page-views.md)、[造訪量度](/help/components/metrics/visits.md)、[不重複訪客量度](/help/components/metrics/unique-visitors.md)、[登入率量度](/help/components/metrics/entries.md)、[跳出率量度](/help/components/metrics/bounce-rate.md)、[退出率量度](/help/components/metrics/exits.md)以及[內容速度量度](/help/components/metrics/content-velocity.md)。 它也會針對登入、退出和頂端區段使用[流量視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)；顯示最常見頁面檢視的[點陣圖視覺效果](/help/analyze/analysis-workspace/visualizations/scatterplot.md)；依分段時間顯示頁面檢視的[長條圖視覺效果](/help/analyze/analysis-workspace/visualizations/bar.md)；以及顯示網站平均逗留時間的趨勢檢視的[線條視覺效果](/help/analyze/analysis-workspace/visualizations/line.md)。</p> |
| [!UICONTROL **下一頁和上一頁流量**] | 檢視訪客造訪特定地點之前或之後最常前往的地方。<p>**這可協助您**&#x200B;更清楚瞭解使用者第一次進入網站時的目的地、使用者最常造訪的網站區域，以及離開網站前最有可能造訪的頁面。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何數量的操作，例如評估網站上的哪些路徑會將人們引導至最重要的頁面，以及哪些頁面更可能將人們引導至遠離網站<!-- not sure about these takeaways... -->。</p> <p>此範本使用[頁面維度](/help/components/dimensions/page.md)和[頁面檢視量度](/help/components/metrics/page-views.md)、[造訪量度](/help/components/metrics/visits.md)、[不重複訪客量度](/help/components/metrics/unique-visitors.md)、[登入率量度](/help/components/metrics/entries.md)、[跳出率量度](/help/components/metrics/bounce-rate.md)、[退出率量度](/help/components/metrics/exits.md)以及[內容速度量度](/help/components/metrics/content-velocity.md)。 它也會針對登入、退出和頂端區段使用[流量視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)；顯示最常見頁面檢視的[散點圖視覺效果](/help/analyze/analysis-workspace/visualizations/scatterplot.md)；顯示依分段時間劃分的頁面檢視的[長條圖視覺效果](/help/analyze/analysis-workspace/visualizations/bar.md)；以及顯示網站平均逗留時間的趨勢檢視的[線條視覺效果](/help/analyze/analysis-workspace/visualizations/line.md)。</p> |
| [!UICONTROL **流失**] | 檢視在一系列預先定義的連續頁面中，訪客在哪個位置離開和繼續通過。<p>**這可以幫助您**&#x200B;更加了解人們在使用者歷程中的哪些位置流失。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如透過網站上的特定流程 (像是購買或註冊流程) 分析轉換率，或分析網站上事件之間的關聯。(例如，查看您的隱私權原則並繼續購買產品的人所佔的百分比)。您也可以使用此範本，在同一份報表中執行兩個不同區段的並排比較。</p> <p>此範本使用[流失視覺效果](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)。</p> |
| [!UICONTROL **跨裝置分析**] | 檢視訪客在歷程的所有時間點使用了哪些裝置。<p>**這可以幫助您**&#x200B;更加了解有多少人與您的品牌互動、他們使用的裝置類型，以及他們對多種裝置的使用如何影響其體驗。舉例來說，人們在行動裝置上開始工作，且稍後再移至桌上型電腦完成工作的頻率為何？使用者在裝置間移動最常採取的路徑為何？他們在哪裡退出？他們在哪裡獲得成功？以此類推。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如針對行動體驗將使用者歷程的特定部分最佳化。</p> <p>此範本使用[流量視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)、[流失視覺效果](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)、[同類群組分析](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)、[人員量度](/help/components/metrics/people.md)和[不重複裝置量度](/help/components/metrics/unique-devices.md)。</p> |
| [!UICONTROL **網頁留存率**] | 檢視誰是您的忠實使用者，以及他們在您的網站上做什麼。<p>**這可以幫助您**&#x200B;更加了解使用者造訪您網站的平均次數、返回網站的頻率，以及回訪之間的天數。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如分析哪些內容最能有效地吸引人們返回網站。<p>此範本使用[造訪量度](/help/components/metrics/visits.md)和[不重複訪客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **媒體音訊使用量**] | 檢視所有數位裝置上媒體音效消費的趨勢和熱門量度。<p>**這可以幫助您**&#x200B;更加了解訪客如何在您的網站上使用音訊內容。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如分析哪些內容最常被使用。<p>此範本使用[造訪量度](/help/components/metrics/visits.md)和[不重複訪客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **媒體造訪間隔、頻率、忠誠度**] | 檢視所有數位裝置上媒體使用的趨勢和熱門量度。<p>**這可以幫助您**&#x200B;更加了解使用者造訪您網站的平均次數、返回網站的頻率，以及回訪之間的天數。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如分析哪些內容最能有效地吸引人們返回網站。<p>此範本使用[造訪量度](/help/components/metrics/visits.md)和[不重複訪客量度](/help/components/metrics/unique-visitors.md)。</p> |
| **[!UICONTROL 頁面分析]** > [!UICONTROL **頁面摘要**] | 檢視訪客每次造訪期間平均在您網站上逗留的時間。會顯示一段期間內的資料，並與先前的時段進行比較。 <p>**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[每次造訪逗留時間（秒）量度](/help/components/metrics/time-spent-per-visit.md)。</p> |
| **[!UICONTROL 頁面分析]** > [!UICONTROL **重新載入**] | 檢視重新載入期間維度項目出現的次數。訪客重新整理瀏覽器是觸發重新載入的最常見方式。 <p>**這可以幫助您**&#x200B;判別特定頁面上何時可能出現問題，且會提示訪客重新載入頁面。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估哪些頁面有需要解決的問題。</p><p>此範本使用[重新載入量度](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/reloads)。</p> |
| **[!UICONTROL 頁面分析]** > [!UICONTROL **頁面逗留時間**] | 檢視訪客每次造訪期間平均在您網站上逗留的時間。會顯示一段期間內的資料，並與先前的時段進行比較。 <p>**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[每次造訪逗留時間（秒）量度](/help/components/metrics/time-spent-per-visit.md)。</p> |
| **[!UICONTROL 登入與退出]** > [!UICONTROL **登入頁面**] | 檢視訪客在第一次造訪您的網站達指定工作階段時所存取的前幾個頁面。 <p>**這有助於您**&#x200B;更加了解哪些頁面為您的網站帶來最多流量，或進一步了解訪客對於網站的第一印象。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如將人們登入網站的初始體驗最佳化，或確保人們登入您的網站時最先看到的頁面呈現良好的互動氛圍，並且提供前往網站其他區域的必要連結。</p><p>此範本使用工作階段量度。 此範本亦使用條狀圖視覺化圖像和自由格式表格視覺化圖像。</p> |
| **[!UICONTROL 登入與退出]** > [!UICONTROL **原始登入頁面**] | 檢視訪客在期限中首次造訪您網站時的熱門存取頁面。 <p>**這有助於您**&#x200B;更加了解哪些頁面為您的網站帶來最多流量，或進一步了解訪客對於網站的第一印象。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如將人們登入網站的初始體驗最佳化，或確保人們登入您的網站時最先看到的頁面呈現良好的互動氛圍，並且提供前往網站其他區域的必要連結。</p><p>此範本使用工作階段量度。 此範本亦使用條狀圖視覺化圖像和自由格式表格視覺化圖像。</p> |
| **[!UICONTROL 登入與退出]** > [!UICONTROL **單頁造訪次數**] | 檢視包含單一不重複頁面的造訪次數。 <p>**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。</p><p>此範本使用[單頁造訪次數維度](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/single-page-visits)。</p> |
| **[!UICONTROL 登入與退出]** > [!UICONTROL **退出頁面**] | 檢視人們在離開您的網站前最常存取的頁面。<p>**這可以協助您**&#x200B;更瞭解哪些頁面正在將人們帶離網站。 </p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如更新常見的退出頁面，將人們離開網站前的體驗最佳化，或包含鼓勵人們在您網站上逗留的內容或連結。</p><p>此範本使用工作階段量度。 此範本亦使用條狀圖視覺化圖像和自由格式表格視覺化圖像。</p> |
| [!UICONTROL **AEM**] > [!UICONTROL **網站績效**] > [!UICONTROL **AEM網站績效**] | 檢視 Adobe Experience Manager 網站的效能資料。  <p>**這可以幫助您**&#x200B;更加了解 Adobe Experience Manager 的價值實現。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將 Experience Manager 設定最佳化。</p> |
| [!UICONTROL **ITP影響**] | 檢視並分析智慧追蹤預防 (ITP) 對資料收集和報告的影響。 <p>**這可以幫助您**&#x200B;更加了解由於 ITP 施加的 Cookie 限制而導致的潛在資料遺失。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如調整您的分析設定以將 ITP 的影響降至最低。</p> |

### 轉換 {#web-conversion}

<!--contextual help is in the CJA docs-->

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **產品轉換漏斗**] | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **產品** | 檢視帶動關鍵量度的產品，例如最暢銷商品或最常檢視的商品。 <p>**這有助於您**&#x200B;更加了解哪些產品最成功。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如增加成功產品的資金，及減少不太成功產品的資金。</p><p>此範本使用訂單量度和產品維度。 |
| **產品績效** | 檢視哪些產品績效最佳。<p>**這有助於您**&#x200B;更加了解哪些產品最成功。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如增加成功產品的資金，及減少不太成功產品的資金。</p><p>此範本使用產品檢視、購物車新增、訂單、收入和件數等量度。 此範本亦使用產品維度。 |
| **類別** |  |
| **購物車轉換漏斗** | 檢視人們執行關鍵結帳事件的次數，例如新增商品到購物車、檢視購物車、移除購物車中的商品以及結帳。 <p>**這有助於您**&#x200B;更加了解結帳程序漏斗的哪些部分會促成轉換，而哪些部分更容易導致購物車捨棄。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如減少結帳程序中某些步驟的摩擦。</p><p>此範本使用 |
| **購物車** | 檢視將產品加入購物車的人數。<p>**這有助於您**&#x200B;更加了解將產品加入到購物車的人數，而非加入到購物車的產品總數。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如測量產品頁面的成效。</p><p>此範本使用購物車量度。 |
| **購物車檢視** | 檢視人們檢視購物車的次數。 <p>**這有助於您**&#x200B;更加了解結帳體驗以降低購物車捨棄率，或分析不同產品間從加入購物車到結帳之間的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對購物車中保留時間最長且捨棄風險最大的產品提供促銷活動。</p><p>此範本使用購物車檢視量度。 |
| **購物車新增** | 檢視人們將商品加入購物車的次數。 <p>**這有助於您**&#x200B;更加了解在轉換漏斗中哪個部分，客戶對產品產生足夠興趣並將其加入到購物車。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如改善所有客戶的產品推薦內容。透過分析哪些產品經常加入到同一購物車，並根據已加入購物車的商品來建議相關產品，即可改善推薦內容。 |
| **購物車移除** | 檢視人們移除購物車中某件商品的次數。<p>**這有助於您**&#x200B;更加了解轉換漏斗中哪個部分讓客戶對產品不再感到興趣，或者可以幫助您了解結帳程序中哪個部分可能存在問題。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如移除結帳程序中可能存有的任何潛在阻礙，例如複雜的使用者體驗。</p><p>此範本使用購物車移除量度。 |
| **購買轉換漏斗** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **收入** | <!--duplicated in Most popular section-->檢視所有訂單中購買產品的金額。<p>**這可協助您將「收入」量度與任何維度結合，以**&#x200B;更能瞭解哪些維度專案對收入有貢獻。 例如，您可以看到對收入最有貢獻的前幾項行銷活動（使用追蹤代碼維度）。 </p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如調整未達到您預期收入目標的行銷活動。</p><p>此範本使用收入量度。 |
| **訂購** | <!--duplicated in Most popular section-->檢視您的網站上發生的購買事件總數。 <p>**這可協助您**&#x200B;結合訂單量度與任何維度，以更清楚瞭解哪些維度專案對訂單有貢獻。 例如，您可以看到對購買最有貢獻的前幾項行銷活動（使用追蹤代碼維度）。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如調整未達到您預期購買目標的行銷活動。 </p><p>此範本使用訂單量度。 |
| [!UICONTROL **件數**] | 檢視所有訂單中購買的單位總數。會顯示一段期間內的資料，並與先前的時段進行比較。 <p>**這有助於您**&#x200B;更加了解單位銷售量隨時間增加或減少的情況。您可以套用區段來了解哪些客戶或地區購買的單位最多，以及這些單位銷售量隨時間呈現的趨勢分析。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如比較行銷活動發起前與發起後的單位銷售量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期期間單位銷售量。</p><p>此範本使用[天維度](/help/components/dimensions/day.md)和[單位量度](/help/components/metrics/units.md)。</p> |
| [!UICONTROL **Magento：行銷與Commerce**] | 檢視零售商對您商業活動的預先建立深入解析，以幫助您提高銷售量。這是針對 Magento 的使用者，但是任何線上零售商都可以運用。 <p>**這可以幫助您**&#x200B;更加了解您的商業活動如何協助提升銷售數字。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將預算調整至 ROI 最高的活動上。</p> |

### 客群 {#web-audience}

<!--contextual help is in the CJA docs-->

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **人員量度**] | 檢視與您品牌互動的人數。 <p>**這可協助您**&#x200B;更瞭解您網站上的使用趨勢。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如衡量最近行銷活動在產生網站新訪客方面的成效。</p> |
| **訪客設定檔** > **位置概述** | 在地圖視覺效果中檢視訪客位置概觀。<p>**這可協助您**&#x200B;更清楚瞭解造訪您網站的訪客所在位置。 </p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如將行銷資源集中在您最感興趣和機會的地方。</p><!-- This template uses the --> |
| **訪客資料** > **地理國家/地區** | 檢視造訪網站的人們來自哪個國家/地區。<p>**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些國家/地區。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如利用資料來加強這些國家/地區的行銷工作，或者確保您的網站體驗在使用不同主要語言的國家/地區能達到最佳效果。</p><p>此範本使用國家/地區維度。 </p> |
| **訪客設定檔** > **美國地理州** | 檢視造訪網站的人們來自哪個州 (美國國內)。此範本與地理區域範本相似，差別僅在限定於美國。<p>**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自美國的哪些州。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用資料來加強這些州的行銷工作。</p><p>此範本使用美國州維度。 </p> |
| **訪客資料** > **地理區域** | 檢視造訪網站的人們來自哪個地理區域。區域指的是小於國家/地區但大於城市的地理範圍。在某些國家，區域是指一個州、省或府/州。在其他地方，則是指構成國、行政區或大都會區域。 <p>**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些區域。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如使用資料來集中在這些地區的行銷工作，或確保您的網站體驗在主要語言不同的地區是最佳的。 </p><p>此範本使用ID（變數/地理國家）與地區維度。 </p> |
| **訪客資料** > **地理城市** | 檢視造訪網站的人們來自哪個城市。 <p>**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些城市。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如使用這些資料來專注於這些城市的行銷工作。 </p><p>此範本使用城市維度。 </p> |
| **訪客設定檔** > **美國Geo DMA** | 檢視造訪網站的人們來自美國境內哪些指定行銷區域 (DMA)。<p>**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些區域。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用資料加強最成功區域的行銷工作。 </p><!-- This template uses the --> |
| **訪客資料** > **語言** | 檢視訪客查看內容時偏好的最常用語言。 <p>**這有助於您**&#x200B;更加了解訪客最常使用的語言。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最常用的語言加強本地化工作或行銷工作。</p><p>此範本使用語言維度。</p> |
| **訪客設定檔** > **時區** | 檢視存取您網站之訪客所在的熱門時區。 <p>**這可以幫助您**&#x200B;更加了解訪客居住的時區。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將網站維修時間調整為受影響人數最少的時段。</p> |
| **訪客設定檔** > **網域** | 檢視存取您網站之訪客使用的熱門網域。 <p>**這可以幫助您**&#x200B;更加了解您的訪客來自哪些組織。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將最大的客戶群作為目標來進行內容設定。</p> |
| **訪客設定檔** > **最上層網域** | 檢視存取您網站的訪客的頂層網域。 <p>**這可以幫助您**&#x200B;更加了解您的訪客來自哪些組織。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將最大的客戶群作為目標來進行內容設定。</p> |
| **訪客設定檔** > **技術** > **技術概覽** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 </p> |
| **訪客設定檔** > **技術** > **瀏覽器** | 檢視人們存取您的網站時最常使用的瀏覽器名稱與版本。<p>**這有助於您**&#x200B;更加了解訪客最常用的瀏覽器。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用最常用的瀏覽器針對網站新版本進行測試，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p><p>此範本使用瀏覽器維度。 </p> |
| **訪客設定檔** > **技術** > **瀏覽器型別** | 檢視人們存取您的網站時最常使用的瀏覽器之製作組織名稱。這與瀏覽器範本不同，不會將相同瀏覽器的不同版本列為單獨的維度項目。<p>**這可協助您**&#x200B;更瞭解訪客最常使用的瀏覽器</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用最常用的瀏覽器針對網站新版本進行測試，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。 </p><p>此範本使用瀏覽器型別維度。 </p> |
| **訪客設定檔** > **技術** > **瀏覽器寬度** | 檢視訪客用來存取您網站的熱門瀏覽器寬度。<p>**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的瀏覽器寬度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p><p>此範本使用瀏覽器維度。 </p> |
| **訪客設定檔** > **技術** > **瀏覽器高度** | 檢視訪客用來存取您網站的熱門瀏覽器高度。<p>**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的瀏覽器高度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p><p>此範本使用瀏覽器維度。 </p> |
| **訪客設定檔** > **技術** > **作業系統** | 檢視訪客存取您網站時使用的作業系統名稱與版本。<p>**這可以幫助您**&#x200B;更加了解訪客使用的最常見作業系統及其版本。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用熱門作業系統及版本來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p> |
| **訪客設定檔** > **技術** > **作業系統型別** | 檢視訪客存取您網站時使用的作業系統名稱。<p>**這能幫助您**&#x200B;更加了解訪客使用的最常見作業系統。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用熱門作業系統來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p> |
| **訪客設定檔** > **技術** > [!UICONTROL **行動電信業者**] | 檢視人們用來存取您的網站之行動裝置，由哪些電信公司提供行動網路連線。<p>**這有助於您**&#x200B;更加了解您的使用者群最常使用哪些行動電信業者。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同電信業者的網路功能自訂內容傳送方式，以確保流暢的使用者體驗。</p><p>此範本使用行動電信業者維度。</p> |
| **訪客保留率** > **回訪頻率** | 檢視人們用來存取您的網站之行動裝置，由哪些電信公司提供行動網路連線。<p>**這有助於您**&#x200B;更加了解您的使用者群最常使用哪些行動電信業者。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同電信業者的網路功能自訂內容傳送方式，以確保流暢的使用者體驗。</p><p>此範本使用行動電信業者維度。</p> |
| **訪客保留率** > **回訪** | 檢視人們用來存取您的網站之行動裝置，由哪些電信公司提供行動網路連線。<p>**這有助於您**&#x200B;更加了解您的使用者群最常使用哪些行動電信業者。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同電信業者的網路功能自訂內容傳送方式，以確保流暢的使用者體驗。</p><p>此範本使用行動電信業者維度。</p> |
| **訪客保留率** > **造訪次數** | 檢視個別訪客造訪網站的次數。<p>**這可以幫助您**&#x200B;更加了解訪客返回您網站時的參與度。此維度會套用至訪客的期限，無論專案日期範圍為何。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如對常客調整行銷工作。</p><p>此範本使用造訪次數維度。</p> |
| **訪客保留率** > **銷售週期** > **客戶忠誠度** | 檢視您網站上先前購買 0 次、先前購買 1 次、先前購買 2 次或先前購買 3 次以上的訪客數量。 <p>**這可以幫助您**&#x200B;更加了解您的網站如何影響購買行為。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將焦點放在返回購買的訪客，藉此鼓勵新訪客也採取類似的行為。</p><p>此範本使用客戶忠誠度維度。</p> |
| **訪客保留率** > **銷售週期** >首次購買前&#x200B;**天** | 檢視訪客首次瀏覽網站和進行購買之間的間隔天數。舉例來說，如果訪客在首次造訪一天後購買，則所有後續造訪或事件都屬於「1 天」維度項目。<p>**這可以幫助您**&#x200B;更加了解訪客通常會在多久後進行購買。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如更新您的網站以促進訪客更快進行購買。</p><p>此範本使用首次購買間隔天數維度。</p> |
| **訪客保留率** > **銷售週期** > **天（自上次購買後）** | 檢視訪客目前的點擊與他們先前最近一次購買之間所經過的時間。<p>**這可以幫助您**&#x200B;更加了解在您網站上購買商品後的訪客行為。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如更新您的網站以鼓勵後續購買。</p><p>此範本使用上次購買間隔天數維度。</p> |
| **行動裝置** > **行動裝置** | 檢視人們存取您的網站所使用的行動裝置品牌和型號。<p>**這有助於您**&#x200B;更加了解您的使用者群最喜歡使用哪些行動裝置。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最常見的行動裝置將網站呈現最佳化。</p><p>此範本使用行動裝置名稱維度。</p> |
| **行動裝置** > **行動裝置型別** | 檢視人們使用哪些類型的行動裝置存取您的網站，例如手機和平板電腦。<p>**這有助於您**&#x200B;更加了解人們存取您的網站所使用的各種行動裝置。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最常用的行動裝置類型將您的網站最佳化。</p><p>此範本使用行動裝置型別維度。</p> |
| **行動裝置** > **製造商** | 檢視人們存取您的網站所使用的行動裝置由哪些製造商製造，例如 Apple 和 Samsung。<p>**這有助於您**&#x200B;更加了解您的使用者群最喜歡哪些製造商。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同製造商的能力自訂內容傳送方式，以確保流暢的使用者體驗。</p><p>此範本使用行動製造商維度。</p> |
| **行動裝置** > **熒幕大小** | 檢視訪客存取您網站時最常使用的行動裝置螢幕尺寸。<p>**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的行動裝置螢幕尺寸來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p> |
| **行動裝置** > **熒幕高度** | 檢視訪客存取您網站時最常使用的行動裝置螢幕長度。<p>**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的行動裝置螢幕長度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p> |
| **行動裝置** > **熒幕寬度** | 檢視訪客存取您的網站時最常使用的行動裝置螢幕寬度。<p>**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的行動裝置螢幕寬度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p> |
| **行動裝置** > **行動應用程式使用情形** | 檢視應用程式的使用者數量、啟動次數和首次啟動次數，以及平均作業長度。<p>**這可協助您**&#x200B;更清楚瞭解您的應用程式目前的使用量。 </p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如提升應用程式效能，使其能夠根據使用量進行擴展。</p><!-- This template uses the --> |
| **行動裝置** > **行動應用程式歷程** | 檢視行動應用程式的主要使用模式。 <p>**這可協助您**&#x200B;更瞭解人們如何使用您的應用程式。 </p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如改進人們從一個螢幕轉到另一個螢幕的方式，以達到最常見的工作流程目標。 </p><!-- This template uses the --> |
| **行動裝置** > **行動應用程式量度** | 檢視一些最常見的行動應用程式量度。 <p>**這可以幫助您**&#x200B;更加了解行動應用程式的基本效能。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估應用程式的整體健康和效能。</p><!-- This template uses the --> |
| **行動裝置** > **行動應用程式訊息** | 檢視應用程式內傳送訊息和推播傳送訊息的效能資料。<p>**這可以幫助您**&#x200B;更加了解人們如何使用應用程式內傳送訊息的功能，以及推播通知如何有效地為您的應用程式帶來流量。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如提升應用程式內傳送訊息推播通知的體驗。</p><!-- This template uses the --> |
| **行動裝置** > **行動應用程式效能** | 檢視應用程式的執行情況，以及使用者在何處遇到問題。 <p>**這可協助您**&#x200B;更清楚瞭解使用您應用程式的人是否遇到效能緩慢或效能降低的問題。 </p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如修復現有問題，或在問題發生之前提升應用程式效能。</p><!-- This template uses the --> |
| **行動裝置** > **行動應用程式保留率** | 檢視哪些使用者是應用程式最忠實的使用者，以及他們在應用程式中執行哪些操作。 <p>**這可以幫助您**&#x200B;更加了解最忠實的使用者如何使用您的應用程式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最忠實使用者正在使用的功能來改善您的行銷工作。</p><!-- This template uses the --> |

### 贏取 {#web-acquisition}

<!--contextual help is in the CJA docs-->

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **行銷管道**] > [!UICONTROL **行銷管道概觀報表**] | 使用自訂歸因時，此範本會顯示訪客如何到達您的網站。<p>**這有助於您**&#x200B;更加了解哪些行銷管道最有效。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對有效的行銷管道加重投資，並放棄投資效果較差的行銷管道。</p><p>此範本使用ID（變數/行銷管道）維度和收入量度。</p> |
| [!UICONTROL **行銷管道**] > [!UICONTROL **首次接觸行銷管道**] | 檢視訪客在參與期間 (預設為 30 天) 符合的第一個行銷管道。 <p>**這有助於您**&#x200B;更加了解哪些行銷管道將初始流量導向您的網站。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最有成效的領域加強行銷工作。</p><p>此範本使用首次接觸管道維度。</p> |
| [!UICONTROL **行銷管道**] > [!UICONTROL **首次接觸行銷管道詳細資料**] | 檢視訪客在參與期間 (預設為 30 天) 符合之第一個行銷管道的詳細資訊。<p>**這有助於您**&#x200B;更加了解是什麼因素促成與行銷管道相符的點擊。例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來瞭解他們使用了哪個搜尋引擎，或搜尋了哪個關鍵字。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最有成效的領域加強行銷工作。</p><p>此範本使用首次接觸管道詳細資料維度。</p> |
| [!UICONTROL **行銷管道**] > [!UICONTROL **上次接觸行銷管道**] | 檢視訪客在其參與期間（預設為30天）遇到的最新相符行銷管道。<p>**這可協助您**&#x200B;更清楚瞭解哪些行銷管道促進您網站的流量進而產生轉換。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最有成效的領域加強行銷工作。</p><p>此範本使用「上次接觸管道」維度。  </p> |
| [!UICONTROL **行銷管道**] > [!UICONTROL **上次接觸行銷管道詳細資料**] | 檢視訪客在其參與期間（預設為30天）遇到的最新相符行銷管道的詳細資料<p>**這有助於您**&#x200B;更加了解是什麼因素促成與行銷管道相符的點擊。例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來瞭解他們使用了哪個搜尋引擎，或搜尋了哪個關鍵字。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最有成效的領域加強行銷工作。 </p><p>此範本使用「上次接觸管道詳細資料」維度。 </p> |
| [!UICONTROL **行銷活動**] > [!UICONTROL **行銷活動（追蹤代碼）**] | 檢視您網站上的追蹤程式碼名稱。 您可以在網際網路中的不同位置放置具有不同查詢字串引數值的連結。<p>**這可協助您**&#x200B;更瞭解哪些連結最能成功吸引流量進入您的網站。 附加追蹤程式碼查詢字串在電子郵件、廣告、社群媒體貼文及您的組織使用的其他行銷工作中很常見</p><p>**根據您所學到的內容，您可能**&#x200B;會執行許多動作，例如將行銷工作重點放在帶來最多收入的行銷活動中。</p><p>此範本使用追蹤代碼維度。 </p> |
| [!UICONTROL **促銷活動**] > [!UICONTROL **促銷活動轉換漏斗**] | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用  </p> |
| [!UICONTROL **行銷活動**] > [!UICONTROL **行銷活動績效**] | 檢視您的行銷活動績效的詳細資訊。<p>**這有助於您**&#x200B;更加了解與行銷活動相關的各種成功指標，例如收入、產品瀏覽數、訂單等。</p><p>**根據您所學到的內容，您可能**&#x200B;會執行許多動作，例如將行銷工作重點放在帶來最多收入的行銷活動中。 </p><p>此範本使用「收入」量度、「產品檢視」量度、「購物車新增」量度、「訂單」量度和「件數」量度。 此範本亦使用追蹤程式碼維度和反向連結網域維度。 </p> |
| **行動裝置贏取** | 檢視您的網站如何取得行動裝置上的訪客。<p>**這有助於您**&#x200B;更加了解促成贏取客戶的各種因素，例如搜尋關鍵字、反向連結網域等。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最有成效的管道加強行銷工作。</p><p>此範本使用「跳出率」量度和「跳出」量度。 此範本亦使用搜尋引擎維度、搜尋關鍵字維度、登入頁面維度、反向連結網域維度、追蹤程式碼維度和反向連結維度。  </p> |
| **網頁贏取** | 檢視您的網站如何吸引訪客。<p>**這有助於您**&#x200B;更加了解促成贏取客戶的各種因素，例如搜尋關鍵字、反向連結網域等。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最有成效的管道加強行銷工作。</p><p>此範本使用「跳出率」量度和「跳出」量度。 此範本亦使用搜尋引擎維度、搜尋關鍵字維度、登入頁面維度、反向連結網域維度、追蹤程式碼維度和反向連結維度。  </p> |
| **Advertising Analytics：付費搜尋** | 並排檢視您所有的 Google 和 Bing 付費搜尋資料。 <p>**這可以幫助您**&#x200B;更加了解傳送到您網站的流量，以及客戶是否正在轉換。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如預估廣告行銷活動的成本效益。</p> |
| **搜尋關鍵字 — 全部** | 檢視訪客到達您網站所使用的搜尋關鍵字，無論是付費或免費。 <p>**這有助於您**&#x200B;更加了解人們搜尋哪些關鍵字而帶來網站流量。 </p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如找出所使用的關鍵字和能夠帶來網站流量的關鍵字之間有哪些 SEO 差距，並彌補這些差距。</p><p>此範本使用「搜尋關鍵字」維度。 </p> |
| **搜尋付費關鍵字** | 檢視訪客用來到達您網站的搜尋關鍵字 (與付費搜尋偵測相符)。<p>**這有助於您**&#x200B;更加了解人們搜尋哪些關鍵字而帶來網站流量。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如找出所使用的關鍵字和能夠帶來網站流量的關鍵字之間有哪些 SEO 差距，並彌補這些差距。 </p><p>此範本使用搜尋關鍵字 — 付費維度。 </p> |
| **搜尋關鍵字 — 免費** | 檢視訪客用來到達您網站的搜尋關鍵字 (與付費搜尋偵測不符)。<p>**這有助於您**&#x200B;更加了解人們搜尋哪些關鍵字而帶來網站流量。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如找出所使用的關鍵字和能夠帶來網站流量的關鍵字之間有哪些 SEO 差距，並彌補這些差距。</p><p>此範本使用「搜尋關鍵字 — 免費」維度。 </p> |
| **搜尋引擎 — 全部** | 檢視訪客到達您網站所使用的搜尋引擎，無論是付費或免費。 <p>**這有助於您**&#x200B;更加了解人們使用哪些搜尋引擎而帶來網站流量。 </p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對為網站帶來最多流量的搜尋引擎加強 SEO 工作。</p><p>此範本使用搜尋引擎維度。 </p> |
| **搜尋引擎付費** | 檢視訪客用來到達您網站的搜尋引擎 (與付費搜尋偵測相符)。<p>**這有助於您**&#x200B;更加了解人們使用哪些搜尋引擎而帶來網站流量。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對為網站帶來最多流量的搜尋引擎加強 SEO 工作。 </p><p>此範本使用搜尋引擎 — 付費維度。 </p> |
| **搜尋引擎 — 免費** | 檢視訪客用來到達您網站的搜尋關鍵字 (與付費搜尋偵測不符)。<p>**這有助於您**&#x200B;更加了解人們使用哪些搜尋引擎而帶來網站流量。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對為網站帶來最多流量的搜尋引擎加強 SEO 工作。</p><p>此範本使用「搜尋引擎 — 免費」維度。 </p> |
| **所有搜尋頁面排名** | 檢視訪客點擊了搜尋結果中的哪一個頁面來進入您的網站。例如，若您的網站出現在搜尋引擎搜尋結果的第二頁，此變數的維度項目則為「搜尋頁面 2」。<p>**這可以幫助您**&#x200B;更加了解您的頁面在搜尋結果中的排名。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作、改進您的 SEO 策略，以確保您的內容顯示在搜尋結果的第一頁中。 </p> |
| **反向連結網域** | 檢視人們點進哪些網域來到達您的網站。<p>**這有助於您**&#x200B;更加了解哪些協力廠商網站為您的網站帶來最多流量。(外部網站上必須有連結，且訪客必須點選該連結，才會顯示維度項目。)</p><p>**根據您瞭解到的內容，您可能**&#x200B;會執行許多操作，例如建立或調整內容，以更符合來自頂級反向連結網域的訪客的興趣。 </p><p>此範本使用反向連結網域維度。 </p> |
| **原始反向連結網域** | 檢視人們到達您的網站前點進的第一個反向連結網域。(設定後，該訪客 ID 的整個期限內都會包含相同的值。)<p>**這有助於您**&#x200B;更加了解哪些協力廠商網站會帶動原始流量到您的網站。</p><p>**根據您瞭解到的內容，您可能**&#x200B;會執行任意數量的操作，例如建立或調整內容，以更符合來自最佳原始反向連結網域的訪客的興趣。 </p><p>此範本使用原始反向連結網域維度。 </p> |
| **反向連結** | 檢視訪客點進哪一個 URL 來到達您的網站。(外部 URL 上必須有連結，且訪客必須點選該連結，才會顯示維度項目。)  <p>**這有助於您**&#x200B;更加了解哪些特定 URL 為您的網站帶來最多流量。</p><p>**根據您瞭解到的內容，您可能**&#x200B;會執行許多操作，例如建立或調整內容，以更符合來自頂層URL之訪客的興趣。 </p><p>此範本使用反向連結網域維度 </p><p>此範本使用反向連結維度。 </p> |
| **反向連結型別** | 檢視訪客點進哪個通用管道來到達您的網站。Adobe 會維護每個管道的規則。可能的管道包括搜尋引擎、社交網路、其他網站、硬碟或電子郵件。<p>**這有助於您**&#x200B;更加了解哪種類型的反向連結能為您的網站帶來最多流量。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如建立或調整內容，使更加符合來自特定管道的訪客之興趣。</p><p>此範本使用反向連結型別維度。</p> |
