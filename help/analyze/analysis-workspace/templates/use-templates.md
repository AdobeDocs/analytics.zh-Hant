---
description: 如何在 Analysis Workspace 中使用預設範本的概觀。
title: 使用範本
feature: Analysis Workspace
role: User, Admin
exl-id: 9e5d1b35-e2b3-4fa5-af12-67bb913675bc
source-git-commit: 75ade12b36e2dc98a1ad521c746d97094c7bf9cd
workflow-type: tm+mt
source-wordcount: '18667'
ht-degree: 99%

---

# 使用範本

Analysis Workspace 中的範本 (或公司範本) 提供最常見的報告情境之快速深入分析。以下範本是您可以使用範本回答的問題：

* 多少訪客瀏覽您的網站
* 多少訪客是獨特訪客 (僅計算一次)
* 他們如何來到站點 (例如跟隨連結到達站點，或直接到達)
* 搜尋站點內容時所用的關鍵字
* 在指定網頁或整個站點上逗留的時間
* 訪客點按的連結，以及離開網站的時間
* 產生收入或轉換事件的最有效行銷管道
* 訪客花費在觀看視訊的時間
* 他們用來造訪網站的瀏覽器和裝置

以下資訊說明如何從 Analysis Workspace 的「[!UICONTROL 範本]」索引標籤中存取和使用範本。

## 存取並執行範本

1. 在 Analysis Workspace 中，選取「[!UICONTROL **Workspace**]」索引標籤。

   <!--update screenshot -->

   ![「報告」索引標籤](assets/view-prebuilt-templates-full.png)

1. 在「[!UICONTROL **範本**]」區段中，選取下列其中一個索引標籤：

   * **[!UICONTROL Adobe 範本]**：顯示 Adobe 提供的所有範本。

   * **[!UICONTROL _login_company_name _範本]**：顯示為您組織建立的所有公司範本。

     只有管&#x200B;&#x200B;理員可以建立公司範本。若要了解如何建立公司範本更多資訊，請參閱「[建立和管理範本](/help/analyze/analysis-workspace/templates/create-templates.md)」。

1. 使用以下任一個選項來變更檢視可用範本的方式：

   * 透過選取欄視圖 ![ViewColumn](/help/assets/icons/ViewColumn.svg) 或卡片視圖 ![Card](/help/assets/icons/Card.svg) 圖示，選擇是否在欄視圖或卡片視圖中檢視範本。

   * 使用卡片視圖的![卡片](/help/assets/icons/Card.svg)時，請從以下排序順序中選擇：**[!UICONTROL 最近使用]**、**[!UICONTROL 最受歡迎]**、**[!UICONTROL 英文字母]**、**[!UICONTROL 類別]**。

1. 在搜尋欄位中，開始輸入要尋找範本的名稱，然後從範本清單中選取。您也可以依據 prop、eVar 和事件編號來搜尋範本。<!-- still true? -->

   或

   請選取要查看的範本類別，然後從範本清單中選取範本。

   >[!TIP]
   >
   >若要使用方向鍵瀏覽選單，請按正斜線鍵 (/)，然後按向下鍵。請按 Enter 鍵以載入選取範本。

   有關可用範本的清單，請參閱下方的[可用範本](#available-reports)區段。

## 根據範本建立專案 {#use-reports}

範本也許不完全符合您的需求，但是可以接近您的需求。在這些情況下，您可以使用此範本作為專案的起點，然後對範本進行自訂以最適合您的特定目的。

如果您在進行變更後要離開範本，系統會提示您儲存或捨棄變更。儲存範本的變更會將範本另存為新專案。

若要自訂範本並將其儲存為專案：

1. 在 Adobe Analytics 中，選取「[!UICONTROL **Workspace**]」索引標籤。

1. 請選取「[!UICONTROL **範本**]」索引標籤。

1. 請選取想要查看的範本。例如，在「[!UICONTROL **最受歡迎**]」下，選取「[!UICONTROL **頁面**]」範本。

   ![頁面報告](assets/pages-report.png)

1. 「頁面」範本 (如 Analysis Workspace 中所顯示) 會顯示兩種[視覺效果](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([長條圖](/help/analyze/analysis-workspace/visualizations/bar.md)和[摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)) 以及一個[自由格式表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)。已使用的量度為發生次數。
1. 執行以下任一操作：

   * 檢視範本。
   * 將一或多個區段拖曳到頂部的「區段」放置區。例如，拖曳「[!UICONTROL **Mobile 客戶**]」區段，然後檢視結果。
   * 前往右上方的行事暦，變更日期範圍。
   * 新增維度劃分、在其他量度中拖曳，且通常會根據您的需求自訂範本。

1. (可選) 請選取「[!UICONTROL **專案**]」>「[!UICONTROL **儲存**]」，將範本另存為專案。

   此範本會另存為新專案，而不會修改現有的範本。有關儲存專案的詳細資訊，請參閱「[儲存專案](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)」。

## 可用的範本

若要存取所有可用的預先建立範本：

1. 在 Adobe Analytics 中，選取「[!UICONTROL **Workspace**]」索引標籤，然後選取「[!UICONTROL **範本**]」索引標籤。

   預先建立範本會按類別整理排列。

   <!--add screenshot-->

1. 請選取一個類別來檢視其中的範本。

   以下區段對應於適用類別，並提供有關每個範本的資訊。

   * **[[!UICONTROL 最受歡迎]](#most-popular)**

   * **[[!UICONTROL 參與度]](#engagement)**

### 最受歡迎 {#most-popular}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--unitsOvertimeReport"
>title="檢視所有訂單中購買的單位總數。會顯示一段期間內的資料，並與先前的時段進行比較。"
>abstract="**這有助於您**&#x200B;更加了解單位銷售量隨時間增加或減少的情況。您可以套用區段來了解哪些客戶或地區購買的單位最多，以及這些單位銷售量隨時間呈現的趨勢分析。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如比較行銷活動發起前與發起後的單位銷售量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期期間單位銷售量。<br/>此範本使用「日」維度和「單位」量度。"

<!-- markdownlint-enable MD034 -->

<!--both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--training"
>title="培訓教學課程範本"
>abstract="了解常見的 Analysis Workspace 術語，及建置首次分析所需的步驟。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pagesRankedReport"
>title="找出最受歡迎和最不受歡迎頁面。"
>abstract="**這有助於您**&#x200B;更加了解您的對象，以及他們最感興趣的資訊類型。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如調整頁面中繼資料來提高瀏覽數較少之頁面的可見度，或花時間改善瀏覽數最多之頁面的內容。<br/>此範本使用頁面維度和頁面瀏覽數量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pageViewsOvertimeReport"
>title="檢視頁面總瀏覽數。會顯示一段期間內的資料，並與先前的期間進行比較。 "
>abstract="**這有助於您**&#x200B;更加了解網站上的流量隨時間可能增加或減少的情況。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前與發起後的網站流量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期流量。<br/>此範本使用日維度和頁面瀏覽數量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitsOvertimeReport"
>title="檢視造訪總次數。會顯示一段期間內的資料，並與先前的期間進行比較。"
>abstract="**這有助於您**&#x200B;更加了解網站上的流量隨時間可能增加或減少的情況。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前與發起後的網站流量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期流量。<br/>此範本使用日維度和造訪次數量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitorsOvertimeReport"
>title="檢視不重複訪客總數。會顯示一段期間內的資料，並與先前的期間進行比較。 "
>abstract="**這有助於您**&#x200B;更加了解網站的觸及範圍和對象規模，隨時間或與先前時期相比增加或減少的情況。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前和發起後的不重複訪客，評估最近發起之行銷活動是否成功吸引新使用者造訪網站。或者您可以比較逐年的假期期間造訪網站的人數。<br/>此範本使用日維度和不重複訪客量度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--keyMetricsReport"
>title="檢視以並排方式顯示頁面瀏覽數、造訪次數與不重複訪客量度的報告。會顯示一段期間內的資料，並與先前的期間進行比較。"
>abstract="**這有助於您**&#x200B;比較這些重要量度，更全面地了解造訪網站的不重複訪客數量、頁面造訪次數，以及工作階段數量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估每個人在特定一週或一個月內於造訪網站時檢視的頁面平均數量，以及在一年中的特定時期或行銷活動展開前與展開後的變化情況。<br/>此範本使用日維度、頁面瀏覽數量度、造訪次數量度，和不重複訪客量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--siteSectionRankedReport"
>title="檢視您網站上最受歡迎或績效最好的區段。"
>abstract="**這有助於您**&#x200B;更加了解使用者最常造訪網站的哪些區段。<br>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估您提供的哪些產品或服務最能引起人們興趣。<br/>此範本使用網站區段維度和造訪次數量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--next-page-report"
>title="檢視人們在造訪特定頁面之後最常去的地方。"
>abstract="**這有助於您** 更了解使用者造訪特定頁面後的行為。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估是否能夠將頁面設計或版面最佳化，引導人們前往更理想的頁面，例如購買或留下評論的頁面。<br/>此範本使用「頁面」維度和「事件」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--previous-page-report"
>title="檢視人們在造訪特定頁面之前最常去的地方。"
>abstract="**這有助於您**&#x200B;更了解哪些頁面會將最多流量引導至特定頁面。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估未顯示為先前頁面的頁面，與目前頁面之間的連結是否需要更醒目。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignRankedReport"
>title="檢視將流量導向您的網站效果最好的連結。"
>abstract="**這有助於您**&#x200B;更加了解在造訪您的網站時，哪些追蹤程式碼 (以及與其相關的連結) 最常被使用。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對在網站上新增連結的位置調整相關策略。<br/>此範本使用追蹤程式碼維度和造訪次數量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productsRankedReport"
>title="按照產品檢視訂單數目。會顯示一段期間內的資料。"
>abstract="**這有助於您**&#x200B;了解哪些產品的需求量最高或最低。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如調整您的行銷策略推銷高績效產品，或是改善或停止績效不佳的產品。您也可以根據資料分析來調整產品庫存。<br/>此範本使用產品維度和訂單量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelRankedReport"
>title="檢視訪客在參與期間 (預設為 30 天) 符合的最新行銷管道。"
>abstract="**這有助於您**&#x200B;了解哪些行銷管道最能有效地吸引人們造訪您的網站並成功轉換為客戶。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如分配更多資源給績效好的管道，或分配較少資源給績效不佳的管道。<br/>此範本使用上次接觸管道維度和不重複訪客量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelDetailRankedReport"
>title="檢視訪客在參與期間 (預設為 30 天) 符合的最新行銷管道的詳細資訊。"
>abstract="**這不僅有助於您**&#x200B;了解哪些行銷管道最能有效地吸引人們造訪您的網站並成功轉換為客戶，還可以了解這些行銷管道的詳細資訊。例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來了解他們使用哪個搜尋引擎，或已搜尋哪個關鍵字。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如分配更多資源給績效好的管道，或分配較少資源給績效不佳的管道。<br/>此範本使用上次接觸管道詳細資料維度和不重複訪客量度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--revenueOvertimeReport"
>title="檢視所有訂單中購買的全部產品金額。會顯示一段期間內的資料，並與先前的期間進行比較。"
>abstract="**這有助於您**&#x200B;了解收入隨時間增加或減少的情況。您可以將這個量度與任何維度結合，以了解哪些維度項目對收入有貢獻。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據先前的趨勢預測未來的收入。您還可以新增另一個維度，例如追蹤程式碼維度，以了解哪些行銷活動所產生的收入最多。<br/>此範本使用日維度和收入量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--ordersOvertimeReport"
>title="檢視購買事件總數。會顯示一段期間內的資料，並與先前的期間進行比較。"
>abstract="**這有助於您**&#x200B;更加了解人們對您的產品和服務之興趣，隨時間而增加或減少的情況。您可以應用區段來了解哪些客戶或地區的訂單最多，以及這些訂單隨時間所呈現的趨勢。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如透過比較行銷活動發起前和發起後的訂單量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期訂單量。<br/>此範本使用日維度和訂單量度。"

<!-- markdownlint-enable MD034 -->

可使用以下範本：

| 範本名稱 | 為什麼使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **培訓教學課程**] | 了解常見的 Analysis Workspace 術語，以及建置首次分析的所需步驟 |
| [!UICONTROL **頁面**] | <!--duplicated in Engagement section--> 找出最受歡迎和最不受歡迎頁面。 <p>**這有助於您**&#x200B;更加了解您的對象，以及他們最感興趣的資訊類型。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如調整頁面中繼資料來提高檢視次數較少之頁面的可見度，或花時間改善檢視次數最多之頁面的內容。</p><p>此範本使用[「頁面維度」](/help/components/dimensions/page.md)和[「頁面檢視次數」量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **頁面檢視**] | <!--duplicated in Engagement section--> 檢視頁面總瀏覽數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站上的流量隨時間可能增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前與發起後的網站流量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期流量。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「頁面檢視次數」量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **造訪數**] | <!--duplicated in Engagement section--> 檢視造訪總次數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站上的流量隨時間可能增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前與發起後的網站流量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期流量。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「造訪數」量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **訪客**] | <!--duplicated in Engagement section--> 檢視不重複訪客總數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站的觸及範圍和對象規模，隨時間或與先前時期相比增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前和發起後的不重複訪客，評估最近發起之行銷活動是否成功吸引新使用者造訪網站。或者您可以比較逐年的假期期間造訪網站的人數。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **關鍵量度**] | <!--duplicated in Engagement section--> 檢視以並排方式顯示頁面瀏覽數、造訪次數與不重複訪客量度的報告。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;比較這些重要量度，更全面地了解造訪網站的不重複訪客數量、頁面造訪次數，以及工作階段數量。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如評估每個人在特定一週或一個月內於造訪網站時檢視的頁面平均數量，以及在一年中的特定時期或行銷活動執行前和執行後的變化情況。 </p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)、[「頁面檢視次數」量度](/help/components/metrics/page-views.md)、[「造訪數」量度](/help/components/metrics/visits.md)，以及[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **網站區段**] | 檢視您網站上最受歡迎或績效最好的區段。 <p>**這有助於您**&#x200B;更加了解使用者最常造訪網站的哪些區段。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估您提供的哪些產品或服務最能引起人們興趣。</p> <p>此範本使用[「網站區段」維度](/help/components/dimensions/site-section.md)和[「造訪數」量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **追蹤程式碼**] | 檢視將流量導向您的網站效果最好的連結。 <p>**這有助於您**&#x200B;更加了解在造訪您的網站時，哪些追蹤程式碼 (以及與其相關的連結) 最常被使用。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對在網站上新增連結的位置調整相關策略。</p><p>此範本使用[「追蹤程式碼」維度](/help/components/dimensions/tracking-code.md)和[「造訪數」量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **下一頁**] | 檢視人們在造訪特定頁面之後最常去的地方。 <p>**這有助於您** 更了解使用者造訪特定頁面後的行為。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估是否能夠將頁面設計或版面最佳化，引導人們前往更理想的頁面，例如購買或留下評論的頁面。</p> <p>此範本使用「頁面」維度和「事件」量度。</p> |
| [!UICONTROL **上一頁**] | 檢視人們在造訪特定頁面之前最常去的地方。 <p>**這有助於您**&#x200B;更了解哪些頁面會將最多流量引導至特定頁面。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估未顯示為先前頁面的頁面，與目前頁面之間的連結是否需要更醒目。</p><p>此範本使用「頁面」維度和「事件」量度。</p> |
| [!UICONTROL **產品**] | 按照產品檢視訂單數目。會顯示一段期間內的資料。 <p>**這有助於您**&#x200B;了解哪些產品的需求量最高或最低。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如調整您的行銷策略推銷高績效產品，或是改善或停止績效不佳的產品。您也可以根據資料分析來調整產品庫存。</p><p>此範本使用[「產品」維度](/help/components/dimensions/product.md)和[「訂單數」量度](/help/components/metrics/orders.md)。</p> |
| [!UICONTROL **上次接觸管道**] | 檢視訪客在參與期間 (預設為 30 天) 符合的最新行銷管道。<p>**這有助於您**&#x200B;了解哪些行銷管道最能有效地吸引人們造訪您的網站並成功轉換為客戶。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如分配更多資源給績效好的管道，或分配較少資源給績效不佳的管道。</p><p>此範本使用[「上次接觸管道」維度](/help/components/dimensions/last-touch-channel.md)和[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **上次接觸管道詳細資料**] | 檢視訪客在參與期間 (預設為 30 天) 符合的最新行銷管道的詳細資訊。<p>**這不僅有助於您**&#x200B;了解哪些行銷管道最能有效地吸引人們造訪您的網站並成功轉換為客戶，還可以了解這些行銷管道的詳細資訊。例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來了解他們使用哪個搜尋引擎，或已搜尋哪個關鍵字。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如分配更多資源給績效好的管道，或分配較少資源給績效不佳的管道。</p><p>此範本使用[「上次接觸管道詳細資料」維度](/help/components/dimensions/last-touch-detail.md)和[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **收入**] | 檢視所有訂單中購買的全部產品金額。會顯示一段期間內的資料，並與先前的期間進行比較。<p>**這有助於您**&#x200B;了解收入隨時間增加或減少的情況。您可以將這個量度與任何維度結合，以了解哪些維度項目對收入有貢獻。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據先前的趨勢預測未來的收入。您還可以新增另一個維度，例如追蹤程式碼維度，以了解哪些行銷活動所產生的收入最多。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「收入」量度](/help/components/metrics/revenue.md)。</p> |
| [!UICONTROL **訂單數**] | 檢視購買事件總數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解人們對您的產品和服務之興趣，隨時間而增加或減少的情況。您可以應用區段來了解哪些客戶或地區的訂單最多，以及這些訂單隨時間所呈現的趨勢。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如透過比較行銷活動發起前和發起後的訂單量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期訂單量。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「訂單數」量度](/help/components/metrics/orders.md)。</p> |
| [!UICONTROL **單位**] | 檢視所有訂單中購買的單位總數。會顯示一段期間內的資料，並與先前的時段進行比較。 <p>**這有助於您**&#x200B;更加了解單位銷售量隨時間增加或減少的情況。您可以套用區段來了解哪些客戶或地區購買的單位最多，以及這些單位銷售量隨時間呈現的趨勢分析。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如比較行銷活動發起前與發起後的單位銷售量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期期間單位銷售量。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「單位」量度](/help/components/metrics/units.md)。</p> |

### 參與 {#web-engagement}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--real-time"
>title="檢視目前在您的網站上收集的維度和量度。"
>abstract="**這有助於您**&#x200B;更了解您網站的趨勢。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如回應並主動管理目前行銷內容和行銷活動的成效。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="檢視訪客每次造訪期間平均在您網站上逗留的時間。會顯示一段期間內的資料，並與先前的時段進行比較。"
>abstract="**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。<br/>此範本使用「日」維度和「每次造訪逗留時間 (秒)」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="檢視使用者在成功事件之前的平均逗留時間。"
>abstract="**這有助於您**&#x200B;更加了解訪客執行其所需動作 (例如進行購買) 所花的時間。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否讓訪客更能夠快速達到成功事件。<br/>此範本使用「事件之前時間」維度和「不重複訪客」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="檢視在一系列預先定義的連續頁面中，訪客在哪個位置離開和繼續通過。"
>abstract="**這可以幫助您**&#x200B;更加了解人們在使用者歷程中的哪些位置流失。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如透過網站上的特定流程 (像是購買或註冊流程) 分析轉換率，或分析網站上事件之間的關聯。(例如，查看您的隱私權原則並繼續購買產品的人所佔的百分比)。您也可以使用此範本，在同一份報表中執行兩個不同區段的並排比較。<br/>此範本使用「流失」視覺效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="檢視訪客在歷程的所有時間點使用了哪些裝置。"
>abstract="**這可以幫助您**&#x200B;更加了解有多少人與您的品牌互動、他們使用的裝置類型，以及他們對多種裝置的使用如何影響其體驗。舉例來說，人們在行動裝置上開始工作，且稍後再移至桌上型電腦完成工作的頻率為何？使用者在裝置間移動最常採取的路徑為何？他們在哪裡退出？他們在哪裡獲得成功？以此類推。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如針對行動體驗將使用者歷程的特定部分最佳化。<br/>此範本使用「流量」視覺效果、「流失」視覺效果、「同類群組」分析、「人員」量度和「不重複裝置」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="檢視誰是您的忠實使用者，以及他們在您的網站上做什麼。"
>abstract="**這可以幫助您**&#x200B;更加了解使用者造訪您網站的平均次數、返回網站的頻率，以及回訪之間的天數。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如分析哪些內容最能有效地吸引人們返回網站。<br/>此範本使用「造訪次數」量度和「不重複訪客」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="檢視所有數位裝置上媒體音效消費的趨勢和熱門量度。"
>abstract="**這可以幫助您**&#x200B;更加了解訪客如何在您的網站上使用音訊內容。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如分析哪些內容最常被使用。<br/>此範本使用「造訪次數」量度和「不重複訪客」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="檢視所有數位裝置上媒體使用的趨勢和熱門量度。"
>abstract="**這可以幫助您**&#x200B;更加了解使用者造訪您網站的平均次數、返回網站的頻率，以及回訪之間的天數。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如分析哪些內容最能有效地吸引人們返回網站。<br/>此範本使用「造訪次數」量度和「不重複訪客」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="檢視重新載入期間維度項目出現的次數。訪客重新整理瀏覽器是觸發重新載入的最常見方式。"
>abstract="**這可以幫助您**&#x200B;判別特定頁面上何時可能出現問題，且會提示訪客重新載入頁面。<br/>**根據已知內容，您可以**&#x200B;採取各種動作，例如評估哪些頁面有需要解決的問題。<br/>此範本使用「重新載入」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="檢視訪客每次造訪期間平均在您網站上逗留的時間。會顯示一段期間內的資料，並與先前的時段進行比較。"
>abstract="**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。<br/>此範本使用「日」維度和「每次造訪逗留時間 (秒)」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="檢視訪客在期限中首次造訪您網站時的熱門存取頁面。"
>abstract="**這有助於您**&#x200B;更加了解哪些頁面為您的網站帶來最多流量，或進一步了解訪客對於網站的第一印象。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如將人們登入網站的初始體驗最佳化，或確保人們登入您的網站時最先看到的頁面呈現良好的互動氛圍，並且提供前往網站其他區域的必要連結。<br/>此範本使用工作階段量度。此範本亦使用長條圖視覺效果和自由格式表格視覺效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="檢視包含單一不重複頁面的造訪次數。"
>abstract="**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。<br/>此範本使用「單頁造訪次數」維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="檢視 Adobe Experience Manager 網站的效能資料。"
>abstract="**這可以幫助您**&#x200B;更加了解 Adobe Experience Manager 的價值實現。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將 Experience Manager 設定最佳化。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--formsPerformanceOverview"
>title="檢視 Adobe Experience Manager Forms 的成效資料。"
>abstract="**這可以幫助您**&#x200B;更加了解 Adobe Experience Manager 的價值實現。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將 Experience Manager 設定最佳化。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="檢視並分析智慧追蹤預防 (ITP) 對資料收集和報告的影響。"
>abstract="**這可以幫助您**&#x200B;更加了解由於 ITP 施加的 Cookie 限制而導致的潛在資料遺失。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如調整您的分析設定以將 ITP 的影響降至最低。"

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template_time_spent"
>title="檢視訪客每次造訪期間在您的網站上平均花費的時間，以及使用者在成功事件之前平均花費的時間。會顯示一段期間內的資料，並與先前的期間進行比較。"
>abstract="**這有助於您**&#x200B;更加了解訪客參與度，以及訪客執行其目標動作 (例如進行購買) 所需的時間。<br/>**根據了解到的內容，您可以**&#x200B;採各種行動，例如評估網站的變更是否讓訪客更能夠快速達到成功事件。<br/>此範本使用日維度和每次造訪所花費的時間 (秒) 量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-content-consumption"
>title="檢視使用者最常使用以及對使用者有吸引力的網頁內容。"
>abstract="**這有助於您**&#x200B;更加了解人們首次登入網站時會前往哪些部分、人們最常造訪網站的哪些區段，以及哪些頁面最有可能導致人們離開網站。<br/>**根據已知內容，您可以**&#x200B;採取各種行動，例如評估網站上哪些路徑會將人們帶到最重要的頁面，以及哪些頁面更有可能促使人們離開網站。<br/>此範本使用頁面維度和頁面瀏覽數量度、造訪次數量度、不重複訪客量度、登入率量度、跳出率量度、退出率量度和內容速度量度。此範本亦使用流量視覺化影像呈現進入、退出和熱門區段。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--media-content-consumption"
>title="檢視使用者最常使用以及對使用者有吸引力的媒體內容。"
>abstract="**這有助於您**&#x200B;更加了解人們首次登入網站時會前往哪些部分、人們最常造訪網站的哪些區段，以及哪些頁面最有可能導致人們離開網站。<br/>**根據已知內容，您可以**&#x200B;採取各種行動，例如評估網站上哪些路徑會將人們帶到最重要的頁面，以及哪些頁面更有可能促使人們離開網站。<br/>此範本使用頁面維度和頁面瀏覽數量度、造訪次數量度、不重複訪客量度、登入率量度、跳出率量度、退出率量度和內容速度量度。此範本亦使用流量視覺化影像呈現進入、退出和熱門區段；利用散佈圖視覺化影像呈現最常用頁面的頁面瀏覽數；利用條狀圖視覺化影像依分段時間呈現頁面瀏覽數；以及利用折線圖視覺化影像呈現平均網站逗留時間的趨勢檢視。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--flowreport"
>title="檢視人們在造訪特定地點之前或之後最常去的地方。"
>abstract="**這有助於您**&#x200B;了解流量如何從特定頁面移到網站的其他部分，並了解人們到達特定頁面的路徑。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估是否能夠將頁面設計或版面最佳化，引導人們前往更理想的頁面，例如購買或留下評論的頁面。或者評估目前頁面上的資訊，是否可能為從先前頁面到達這裡的人們提供所尋找的方向或動作。或者您可以評估那些並未像先前頁面一樣出現的頁面，其與目前頁面之間的連結是否需要更加顯眼。<br/>此範本使用下一個或上一個項目面板。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--page-summary-report"
>title="檢視您各項屬性中任何頁面的重要資訊。呈現頁面瀏覽數、趨勢線、流量視覺化影像等。"
>abstract="**這有助於您**&#x200B;更加了解人們與特定頁面互動的情況。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如分析一段期間內頁面的績效，或加強了解是哪些因素將流量導向頁面。<br/>此範本使用頁面瀏覽數量度。此範本亦使用折線圖視覺化影像和流量視覺化影像。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--entryPageRankedReport"
>title="檢視人們首次造訪您網站時最常存取的頁面。"
>abstract="**這有助於您**&#x200B;更加了解哪些頁面為您的網站帶來最多流量，或進一步了解訪客對於網站的第一印象。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如將人們登入網站的初始體驗最佳化，或確保人們登入您的網站時最先看到的頁面呈現良好的互動氛圍，並且提供前往網站其他區域的必要連結。<br/>此範本使用工作階段量度。此範本亦使用長條圖視覺效果和自由格式表格視覺效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--exitPageRankedReport"
>title="檢視人們在離開您的網站前最常存取的頁面。"
>abstract="**這有助於您**&#x200B;更加了解哪些頁面會導致人們離開網站。<br/>**根據已知內容，您可以**&#x200B;採取各種行動，例如更新常見的退出頁面，將人們離開網站前的體驗最佳化，或包括鼓勵人們在您網站上停留的內容或連結。<br/>此範本使用工作階段量度。此範本亦使用長條圖視覺效果和自由格式表格視覺效果。"

<!-- markdownlint-enable MD034 -->

可使用以下範本：

| 範本名稱 | 為什麼使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **關鍵量度**] | <!--duplicated in Most popular section--> 檢視以並排方式顯示頁面瀏覽數、造訪次數與不重複訪客量度的報告。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;比較這些重要量度，更全面地了解造訪網站的不重複訪客數量、頁面造訪次數，以及工作階段數量。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如評估每個人在特定一週或一個月內於造訪網站時檢視的頁面平均數量，以及在一年中的特定時期或行銷活動執行前和執行後的變化情況。 </p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)、[「頁面檢視次數」量度](/help/components/metrics/page-views.md)、[「造訪數」量度](/help/components/metrics/visits.md)，以及[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **頁面檢視**] | <!--duplicated in Most popular section-->檢視頁面總瀏覽數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站上的流量隨時間可能增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前與發起後的網站流量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期流量。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「頁面檢視次數」量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **頁面**] | <!--duplicated in Most popular section-->找出最受歡迎和最不受歡迎頁面。 <p>**這有助於您**&#x200B;更加了解您的對象，以及他們最感興趣的資訊類型。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如調整頁面中繼資料來提高檢視次數較少之頁面的可見度，或花時間改善檢視次數最多之頁面的內容。</p><p>此範本使用[「頁面維度」](/help/components/dimensions/page.md)和[「頁面檢視次數」量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **造訪數**] | <!--duplicated in Most popular section-->檢視造訪總次數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站上的流量隨時間可能增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前與發起後的網站流量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期流量。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「造訪數」量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **訪客**] | <!--duplicated in Most popular section-->檢視不重複訪客總數。會顯示一段期間內的資料，並與先前的期間進行比較。 <p>**這有助於您**&#x200B;更加了解網站的觸及範圍和對象規模，隨時間或與先前時期相比增加或減少的情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如比較行銷活動發起前和發起後的不重複訪客，評估最近發起之行銷活動是否成功吸引新使用者造訪網站。或者您可以比較逐年的假期期間造訪網站的人數。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **每次造訪逗留時間**] | 檢視訪客每次造訪期間平均在您網站上逗留的時間。會顯示一段期間內的資料，並與先前的時段進行比較。 <p>**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「每次造訪逗留時間 (秒)」量度](/help/components/metrics/time-spent-per-visit.md)。</p> |
| [!UICONTROL **事件之前時間**] | 檢視使用者在成功事件之前的平均逗留時間。 <p>**這有助於您**&#x200B;更加了解訪客執行其所需動作 (例如進行購買) 所花的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否讓訪客更能夠快速達到成功事件。</p><p>此範本使用[「事件之前時間」維度](/help/components/dimensions/time-prior-to-event.md)和[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **網站區段**] | <!--duplicated in Most popular section-->檢視您網站上最受歡迎或績效最好的區段。 <p>**這有助於您**&#x200B;更加了解使用者最常造訪網站的哪些區段。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估您提供的哪些產品或服務最能引起人們興趣。</p> <p>此範本使用[「網站區段」維度](/help/components/dimensions/site-section.md)和[「造訪數」量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **即時**] | 檢視目前在您的網站上收集的維度和量度。 <p>**這有助於您**&#x200B;更了解您網站的趨勢。</p><p>**根據已知內容，您可以**&#x200B;回應並主動管理目前行銷內容和行銷活動的成效。</p> <p>此範本使用[「即時」報告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)。</p> |
| [!UICONTROL **網頁內容使用量**] | 檢視使用者最常使用以及對使用者有吸引力的網頁內容。<p>**這有助於您**&#x200B;更加了解人們首次登入網站時會前往哪些部分、人們最常造訪網站的哪些區段，以及哪些頁面最有可能導致人們離開網站。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如評估網站上哪些路徑會將人們帶到最重要的頁面，以及哪些頁面更有可能促使人們離開網站。</p> <p>此範本使用[「頁面」維度](/help/components/dimensions/page.md)和[「頁面檢視次數」量度](/help/components/metrics/page-views.md)、[「造訪數」量度](/help/components/metrics/visits.md)、[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)、[「登入率」量度](/help/components/metrics/entries.md)、[「退回率」量度](/help/components/metrics/bounce-rate.md)、[「退出率」量度](/help/components/metrics/exits.md)，以及[「內容速度」量度](/help/components/metrics/content-velocity.md)。此範本亦使用[「流量」視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)，顯示進入、退出以及熱門區段。</p> |
| [!UICONTROL **媒體內容使用量**] | 檢視使用者最常使用以及對使用者有吸引力的媒體內容。<p>**這有助於您**&#x200B;更加了解人們首次登入網站時會前往哪些部分、人們最常造訪網站的哪些區段，以及哪些頁面最有可能導致人們離開網站。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如評估網站上哪些路徑會將人們帶到最重要的頁面，以及哪些頁面更有可能促使人們離開網站。</p> <p>此範本使用[「頁面」維度](/help/components/dimensions/page.md)和[「頁面檢視次數」量度](/help/components/metrics/page-views.md)、[「造訪數」量度](/help/components/metrics/visits.md)、[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)、[「登入率」量度](/help/components/metrics/entries.md)、[「退回率」量度](/help/components/metrics/bounce-rate.md)、[「退出率」量度](/help/components/metrics/exits.md)，以及[「內容速度」量度](/help/components/metrics/content-velocity.md)。此範本亦使用[「流量」視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) 顯示進入、退出以及熱門區段；[「散佈圖」視覺效果](/help/analyze/analysis-workspace/visualizations/scatterplot.md)顯示最常用頁面的頁面檢視次數；[「長條圖」視覺效果](/help/analyze/analysis-workspace/visualizations/bar.md)根據時段顯示頁面檢視次數；[「折線圖」視覺效果](/help/analyze/analysis-workspace/visualizations/line.md)顯示平均網站逗留時間的趨勢檢視。</p> |
| [!UICONTROL **下一頁和上一頁流量**] | 檢視人們在造訪特定地方之前或之後最常去的地方。<p>**這有助於您**&#x200B;更加了解人們首次登入網站時會前往何處、人們最常造訪網站的哪些區段，以及哪些頁面最有可能導致人們離開網站。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如評估網站上哪些路徑會將人們帶到最重要的頁面，以及哪些頁面更有可能促使人們離開網站。</p> <p>此範本使用[「頁面」維度](/help/components/dimensions/page.md)和[「頁面檢視次數」量度](/help/components/metrics/page-views.md)、[「造訪數」量度](/help/components/metrics/visits.md)、[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)、[「登入率」量度](/help/components/metrics/entries.md)、[「退回率」量度](/help/components/metrics/bounce-rate.md)、[「退出率」量度](/help/components/metrics/exits.md)，以及[「內容速度」量度](/help/components/metrics/content-velocity.md)。此範本亦使用[「流量」視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) 顯示進入、退出以及熱門區段；[「散點圖」視覺效果](/help/analyze/analysis-workspace/visualizations/scatterplot.md)顯示最常用頁面的頁面檢視次數；[「長條圖」視覺效果](/help/analyze/analysis-workspace/visualizations/bar.md)根據時段顯示頁面檢視次數；[「折線圖」視覺效果](/help/analyze/analysis-workspace/visualizations/line.md)顯示平均網站逗留時間的趨勢檢視。</p> |
| [!UICONTROL **流失**] | 檢視在一系列預先定義的連續頁面中，訪客在哪個位置離開和繼續通過。<p>**這可以幫助您**&#x200B;更加了解人們在使用者歷程中的哪些位置流失。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如透過網站上的特定流程 (像是購買或註冊流程) 分析轉換率，或分析網站上事件之間的關聯。(例如，查看您的隱私權原則並繼續購買產品的人所佔的百分比)。您也可以使用此範本，在同一份報表中執行兩個不同區段的並排比較。</p> <p>此範本使用[「流失」視覺效果](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)。</p> |
| [!UICONTROL **跨裝置分析**] | 檢視訪客在歷程的所有時間點使用了哪些裝置。<p>**這可以幫助您**&#x200B;更加了解有多少人與您的品牌互動、他們使用的裝置類型，以及他們對多種裝置的使用如何影響其體驗。舉例來說，人們在行動裝置上開始工作，且稍後再移至桌上型電腦完成工作的頻率為何？使用者在裝置間移動最常採取的路徑為何？他們在哪裡退出？他們在哪裡獲得成功？以此類推。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如針對行動體驗將使用者歷程的特定部分最佳化。</p> <p>此範本使用[「流量」視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)、[「流失」視覺效果](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)、[「同類群組」分析](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)、[「人員」量度](/help/components/metrics/people.md)，以及[「不重複裝置」量度](/help/components/metrics/unique-devices.md)。</p> |
| [!UICONTROL **網站保留率**] | 檢視誰是您的忠實使用者，以及他們在您的網站上做什麼。<p>**這可以幫助您**&#x200B;更加了解使用者造訪您網站的平均次數、返回網站的頻率，以及回訪之間的天數。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如分析哪些內容最能有效地吸引人們返回網站。<p>此範本使用[「造訪數」量度](/help/components/metrics/visits.md)和[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **串流媒體使用量**] | 檢視所有數位裝置上媒體音效消費的趨勢和熱門量度。<p>**這可以幫助您**&#x200B;更加了解訪客如何在您的網站上使用音訊內容。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如分析哪些內容最常被使用。<p>此範本使用[「造訪數」量度](/help/components/metrics/visits.md)和[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **媒體造訪間隔、頻率、忠誠度**] | 檢視所有數位裝置上媒體使用的趨勢和熱門量度。<p>**這可以幫助您**&#x200B;更加了解使用者造訪您網站的平均次數、返回網站的頻率，以及回訪之間的天數。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如分析哪些內容最能有效地吸引人們返回網站。<p>此範本使用[「造訪數」量度](/help/components/metrics/visits.md)和[「不重複訪客」量度](/help/components/metrics/unique-visitors.md)。</p> |
| **[!UICONTROL 頁面分析]** > [!UICONTROL **頁面摘要**] | 檢視訪客每次造訪期間平均在您網站上逗留的時間。會顯示一段期間內的資料，並與先前的時段進行比較。 <p>**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「每次造訪逗留時間 (秒)」量度](/help/components/metrics/time-spent-per-visit.md)。</p> |
| **[!UICONTROL 頁面分析]** > [!UICONTROL **重新載入**] | 檢視重新載入期間維度項目出現的次數。訪客重新整理瀏覽器是觸發重新載入的最常見方式。 <p>**這可以幫助您**&#x200B;判別特定頁面上何時可能出現問題，且會提示訪客重新載入頁面。</p><p>**根據已知內容，您可以**&#x200B;採取各種動作，例如評估哪些頁面有需要解決的問題。</p><p>此範本使用[「重新載入」量度](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/metrics/reloads)。</p> |
| **[!UICONTROL 頁面分析]** > [!UICONTROL **逗留頁面時間**] | 檢視訪客每次造訪期間平均在您網站上逗留的時間。會顯示一段期間內的資料，並與先前的時段進行比較。 <p>**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「每次造訪逗留時間 (秒)」量度](/help/components/metrics/time-spent-per-visit.md)。</p> |
| **[!UICONTROL 登入和退出]** > [!UICONTROL **登入頁面**] | 檢視人們首次造訪您網站特定工作階段時最常存取的頁面。 <p>**這有助於您**&#x200B;更加了解哪些頁面為您的網站帶來最多流量，或進一步了解訪客對於網站的第一印象。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如將人們登入網站的初始體驗最佳化，或確保人們登入您的網站時最先看到的頁面呈現良好的互動氛圍，並且提供前往網站其他區域的必要連結。</p><p>此範本使用「工作階段」量度。此範本亦使用長條圖視覺效果和自由格式表格視覺效果。</p> |
| **[!UICONTROL 登入和退出]** > [!UICONTROL **原始登入頁面**] | 檢視訪客在期限中首次造訪您網站時的熱門存取頁面。 <p>**這有助於您**&#x200B;更加了解哪些頁面為您的網站帶來最多流量，或進一步了解訪客對於網站的第一印象。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如將人們登入網站的初始體驗最佳化，或確保人們登入您的網站時最先看到的頁面呈現良好的互動氛圍，並且提供前往網站其他區域的必要連結。</p><p>此範本使用「工作階段」量度。此範本亦使用長條圖視覺效果和自由格式表格視覺效果。</p> |
| **[!UICONTROL 登入和退出]** > [!UICONTROL **單次頁面造訪數**] | 檢視包含單一不重複頁面的造訪次數。 <p>**這可以幫助您**&#x200B;更加了解訪客參與度以及訪客在網站上逗留的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如評估網站的變更是否會讓訪客在網站上停留更長時間。</p><p>此範本使用[「單次頁面造訪數」維度](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/dimensions/single-page-visits)。</p> |
| **[!UICONTROL 登入和退出]** > [!UICONTROL **退出頁面**] | 檢視人們在離開您的網站前最常存取的頁面。<p>**這有助於您**&#x200B;更加了解哪些頁面會導致人們離開網站。 </p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如更新常見的退出頁面，將人們離開網站前的體驗最佳化，或包括鼓勵人們在您網站上停留的內容或連結。</p><p>此範本使用「工作階段」量度。此範本亦使用長條圖視覺效果和自由格式表格視覺效果。</p> |
| [!UICONTROL **Adobe Experience Manager**] > [!UICONTROL **網站績效概觀**] > [!UICONTROL **AEM 網站績效**] | 檢視 Adobe Experience Manager 網站的效能資料。  <p>**這可以幫助您**&#x200B;更加了解 Adobe Experience Manager 的價值實現。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將 Experience Manager 設定最佳化。</p> |
| [!UICONTROL **Adobe Experience Manager**] > [!UICONTROL **表單效能概觀**] > [!UICONTROL **AEM 表單效能**] | 檢視 Adobe Experience Manager Forms 的成效資料。  <p>**這可以幫助您**&#x200B;更加了解 Adobe Experience Manager 的價值實現。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將 Experience Manager 設定最佳化。</p> |
| [!UICONTROL **ITP 影響**] | 檢視並分析智慧追蹤預防 (ITP) 對資料收集和報告的影響。 <p>**這可以幫助您**&#x200B;更加了解由於 ITP 施加的 Cookie 限制而導致的潛在資料遺失。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如調整您的分析設定以將 ITP 的影響降至最低。</p> |

### 轉換 {#web-conversion}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="檢視與您網站上每個產品類別相關的造訪次數。這對於使用產品變數且希望查看產品類別相關量度的實作作業非常實用。如果您的網站上沒有任何產品，則填入此範本的維度可能會刻意保留為空白。"
>abstract="**這有助於您** 更了解最暢銷或瀏覽次數最多的產品。&lt;/br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如測量指定產品的行銷活動有效性。<br/>此範本使用「類別」維度和「造訪次數」量度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="檢視零售商對您商業活動的預先建立深入解析，以幫助您提高銷售量。這是針對 Adobe Commerce 的使用者，但是任何線上零售商都可以運用。"
>abstract="**這可以幫助您**&#x200B;更加了解您的商業活動如何協助提升銷售數字。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將預算調整至 ROI 最高的活動上。"

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productConversionReport"
>title="在顯示購物車、結帳和訂單的漏斗視覺效果中檢視產品轉換。您也可以查看轉換百分比、平均收入、單位平均數和訂單平均數。"
>abstract="**這有助於您**&#x200B;更了解人們在轉換過程中的進度和流失情況。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如改善您的網站以促進更順暢的結帳程序。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-products-template"
>title="檢視哪些產品績效最佳。"
>abstract="**這有助於您**&#x200B;更加了解哪些產品最成功。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如增加成功產品的資金，及減少不太成功產品的資金。<br/>此範本使用產品瀏覽數、購物車新增量、訂單、收入和單位量度。此範本亦使用「產品」維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartConversionReport"
>title="檢視人們執行關鍵結帳事件的次數，例如新增商品到購物車、檢視購物車、移除購物車中的商品以及結帳。"
>abstract="**這有助於您**&#x200B;更加了解結帳程序漏斗的哪些部分會促成轉換，而哪些部分更容易導致購物車捨棄。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如減少結帳程序中某些步驟的摩擦。<br/>此範本使用"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartsOvertimeReport"
>title="檢視將產品加入購物車的人數。"
>abstract="**這有助於您**&#x200B;更加了解將產品加入到購物車的人數，而非加入到購物車的產品總數。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如測量產品頁面的成效。<br/>此範本使用購物車量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartViewsOvertimeReport"
>title="檢視人們檢視購物車的次數。"
>abstract="**這有助於您**&#x200B;更加了解結帳體驗以降低購物車捨棄率，或分析不同產品間從加入購物車到結帳之間的時間。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對購物車中保留時間最長且捨棄風險最大的產品提供促銷活動。<br/>此範本使用購物車瀏覽數量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartAdditionsOvertimeReport"
>title="檢視人們將商品加入購物車的次數。"
>abstract="**這有助於您**&#x200B;更加了解在轉換漏斗中哪個部分，客戶對產品產生足夠興趣並將其加入到購物車。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如改善所有客戶的產品推薦內容。透過分析哪些產品經常加入到同一購物車，並根據已加入購物車的商品來建議相關產品，即可改善推薦內容。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartRemovalsOvertimeReport"
>title="檢視人們移除購物車中某件商品的次數。"
>abstract="**這有助於您**&#x200B;更加了解轉換漏斗中哪個部分讓客戶對產品不再感到興趣，或者可以幫助您了解結帳程序中哪個部分可能存在問題。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如移除結帳程序中可能存有的任何潛在阻礙，例如複雜的使用者體驗。<br/>此範本使用購物車移除數量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--purchaseConversionReport"
>title="在顯示工作階段、購物車和訂單的漏斗視覺效果中檢視購買轉換。您也可以查看轉換百分比、平均收入、單位平均數和訂單平均數。"
>abstract="**這有助於您**&#x200B;更了解人們在轉換過程中的進度和流失情況。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如改善您的網站以促進更順暢的結帳程序。"

<!-- markdownlint-enable MD034 -->

可使用以下範本：

| 範本名稱 | 為什麼使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **產品轉換漏斗**] | 在顯示購物車、結帳和訂單的漏斗視覺效果中檢視產品轉換。您也可以查看轉換百分比、平均收入、單位平均數和訂單平均數。<p>**這有助於您**&#x200B;更了解人們在轉換過程中的進度和流失情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如改善您的網站以促進更順暢的結帳程序。</p> |
| **產品** | 檢視哪些產品正在推動關鍵量度，例如暢銷產品或瀏覽次數最多的產品。 <p>**這有助於您**&#x200B;更加了解哪些產品最成功。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如增加成功產品的資金，及減少不太成功產品的資金。</p><p>此範本使用「訂單數」量度和「產品」維度。 |
| **產品效能** | 檢視哪些產品績效最佳。<p>**這有助於您**&#x200B;更加了解哪些產品最成功。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如增加成功產品的資金，及減少不太成功產品的資金。</p><p>此範本使用產品檢視次數、購物車新增量、訂單數、收入以及單位量度。此範本亦使用「產品」維度。 |
| **類別** | 檢視與您網站上每個產品類別相關的造訪次數。這對於使用產品變數且希望查看產品類別相關量度的實作作業非常實用。如果您的網站上沒有任何產品，則填入此範本的維度可能會刻意保留為空白。<p>**這有助於您** 更了解最暢銷或瀏覽次數最多的產品。 </p><p>**根據已知內容，您可以**&#x200B;採取各種動作，例如測量指定產品的行銷活動有效性。</p><p>此範本使用「類別」維度和「造訪數」量度。 |
| **購物車轉換漏斗** | 檢視人們執行關鍵結帳事件的次數，例如新增商品到購物車、檢視購物車、移除購物車中的商品以及結帳。 <p>**這有助於您**&#x200B;更加了解結帳程序漏斗的哪些部分會促成轉換，而哪些部分更容易導致購物車捨棄。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如減少結帳程序中某些步驟的摩擦。</p><p>此範本使用 |
| **購物車** | 檢視將產品加入購物車的人數。<p>**這有助於您**&#x200B;更加了解將產品加入到購物車的人數，而非加入到購物車的產品總數。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如測量產品頁面的成效。</p><p>此範本使用「購物車」量度。 |
| **購物車檢視次數** | 檢視人們檢視購物車的次數。 <p>**這有助於您**&#x200B;更加了解結帳體驗以降低購物車捨棄率，或分析不同產品間從加入購物車到結帳之間的時間。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對購物車中保留時間最長且捨棄風險最大的產品提供促銷活動。</p><p>此範本使用「購物車檢視次數」量度。 |
| **購物車新增** | 檢視人們將商品加入購物車的次數。 <p>**這有助於您**&#x200B;更加了解在轉換漏斗中哪個部分，客戶對產品產生足夠興趣並將其加入到購物車。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如改善所有客戶的產品推薦內容。透過分析哪些產品經常加入到同一購物車，並根據已加入購物車的商品來建議相關產品，即可改善推薦內容。 |
| **購物車移除數** | 檢視人們移除購物車中某件商品的次數。<p>**這有助於您**&#x200B;更加了解轉換漏斗中哪個部分讓客戶對產品不再感到興趣，或者可以幫助您了解結帳程序中哪個部分可能存在問題。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如移除結帳程序中可能存有的任何潛在阻礙，例如複雜的使用者體驗。</p><p>此範本使用「購物車移除數」量度。 |
| **購買轉換漏斗** | 在顯示工作階段、購物車和訂單的漏斗視覺效果中檢視購買轉換。您也可以查看轉換百分比、平均收入、單位平均數和訂單平均數。<p>**這有助於您**&#x200B;更了解人們在轉換過程中的進度和流失情況。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如改善您的網站以促進更順暢的結帳程序。</p> |
| **收入** | <!--duplicated in Most popular section-->檢視所有訂單中所購買產品的金額。<p>透過將收入量度和任意維度結合，**有助於您**&#x200B;更了解哪些維度項目對收入有幫助。例如，您可以查看對收入有幫助的熱門促銷活動 (使用追蹤程式碼維度)。 </p><p>**根據您所了解的情況，您可以**&#x200B;做很多事情，例如調整未達到您預期收入目標的廣告系列。</p><p>此範本使用「收入」量度。 |
| **訂單數** | <!--duplicated in Most popular section-->檢視您網站上發生的購買事件總數。 <p>透過將訂單量度與任意維度結合，**有助於您**&#x200B;更了解哪些維度項目對訂單有幫助。例如，您可以查看對購買有幫助的熱門廣告系列 (使用追蹤程式碼維度)。</p><p>**根據已知情況，您可以**&#x200B;採取各種行動，例如調整未達到您預期購買目標的廣告系列。 </p><p>此範本使用「訂單數」量度。 |
| [!UICONTROL **單位**] | 檢視所有訂單中購買的單位總數。會顯示一段期間內的資料，並與先前的時段進行比較。 <p>**這有助於您**&#x200B;更加了解單位銷售量隨時間增加或減少的情況。您可以套用區段來了解哪些客戶或地區購買的單位最多，以及這些單位銷售量隨時間呈現的趨勢分析。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如比較行銷活動發起前與發起後的單位銷售量，評估最近發起之行銷活動的成效。或者您可以比較逐年的假期期間單位銷售量。</p><p>此範本使用[「日」維度](/help/components/dimensions/day.md)和[「單位」量度](/help/components/metrics/units.md)。</p> |
| [!UICONTROL **Magento：行銷和商務**] | 檢視零售商對您商業活動的預先建立深入解析，以幫助您提高銷售量。這是針對 Adobe Commerce 的使用者，但是任何線上零售商都可以運用。 <p>**這可以幫助您**&#x200B;更加了解您的商業活動如何協助提升銷售數字。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將預算調整至 ROI 最高的活動上。</p> |

### 客群 {#web-audience}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--people"
>title="檢視與您品牌互動的人數。"
>abstract="**這有助於您**&#x200B;更了解網站上的使用趨勢。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如測量近期行銷活動為您的網站帶來新訪客的有效性。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--bots"
>title="檢視有關您網站上機器人流量的頁面瀏覽量和趨勢。"
>abstract="**這有助於您**&#x200B;更了解根據您設定的機器人規則，從報告中篩選過的機器人流量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如繼續監視機器人活動以識別新模式。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstvsrepeatvisitors"
>title="檢視首次訪客和重複訪客的比較。"
>abstract="**這有助於您**&#x200B;更了解您的網站在維持客戶忠誠度方面的有效性，或您獲得新客戶的速度。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如為首次訪客提供未來購買的獎勵，以吸引他們回訪。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--personid"
>title="檢視各管道中的個別使用者行為。"
>abstract="**這有助於您**&#x200B;更了解多個接觸點間的完整客戶歷程與互動。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將行銷活動個人化，以更完善地鎖定使用者偏好。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="檢視存取您網站之訪客所在的熱門時區。"
>abstract="**這可以幫助您**&#x200B;更加了解訪客居住的時區。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將網站維修時間調整為受影響人數最少的時段。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--location"
>title="在地圖視覺效果中檢視訪客位置的概觀。"
>abstract="**這有助於您**&#x200B;更了解造訪您網站之訪客的所在位置。<br/>**根據已知內容，您可以**&#x200B;採取各種動作，例如將行銷資源集中於您認為最感興趣和機會最多的位置。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="檢視存取您網站之訪客使用的熱門網域。"
>abstract="**這可以幫助您**&#x200B;更加了解您的訪客來自哪些組織。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將最大的客戶群作為目標來進行內容設定。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="檢視存取您網站之訪客使用的熱門網域。"
>abstract="**這可以幫助您**&#x200B;更加了解您的訪客來自哪些組織。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將最大的客戶群作為目標來進行內容設定。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="檢視訪客用來存取您網站的熱門瀏覽器寬度。"
>abstract="**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的瀏覽器寬度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。<br/>此範本使用瀏覽器維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="檢視訪客用來存取您網站的熱門瀏覽器高度。"
>abstract="**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的瀏覽器高度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。<br/>此範本使用瀏覽器維度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="檢視訪客存取您網站時使用的作業系統名稱與版本。"
>abstract="**這可以幫助您**&#x200B;更加了解訪客使用的最常見作業系統及其版本。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用熱門作業系統及版本來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="檢視訪客存取您網站時使用的作業系統名稱。"
>abstract="**這能幫助您**&#x200B;更加了解訪客使用的最常見作業系統。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用熱門作業系統來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="檢視人們用來存取您的網站之行動裝置，由哪些電信公司提供行動網路連線。"
>abstract="**這有助於您**&#x200B;更加了解您的使用者群最常使用哪些行動電信業者。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同電信業者的網路功能自訂內容傳送方式，以確保流暢的使用者體驗。<br/>此範本使用行動電信業者維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="檢視人們用來存取您的網站之行動裝置，由哪些電信公司提供行動網路連線。"
>abstract="**這有助於您**&#x200B;更加了解您的使用者群最常使用哪些行動電信業者。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同電信業者的網路功能自訂內容傳送方式，以確保流暢的使用者體驗。<br/>此範本使用行動電信業者維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="檢視個別訪客造訪網站的次數。"
>abstract="**這可以幫助您**&#x200B;更加了解訪客返回您網站時的參與度。此維度會套用至訪客的期限，無論專案日期範圍為何。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如對常客調整行銷工作。<br/>此範本使用「造訪次數」維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="檢視您網站上先前購買 0 次、先前購買 1 次、先前購買 2 次或先前購買 3 次以上的訪客數量。"
>abstract="**這可以幫助您**&#x200B;更加了解您的網站如何影響購買行為。<br/>**根據已知內容，您可以**&#x200B;採取各種動作，例如將焦點放在返回購買的訪客，藉此鼓勵新訪客也採取類似的行為。<br/>此範本使用「客戶忠誠度」維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="檢視訪客首次瀏覽網站和進行購買之間的間隔天數。舉例來說，如果訪客在首次造訪一天後購買，則所有後續造訪或事件都屬於「1 天」維度項目。"
>abstract="**這可以幫助您**&#x200B;更加了解訪客通常會在多久後進行購買。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如更新您的網站以促進訪客更快進行購買。<br/>此範本使用「首次購買間隔天數」維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="檢視訪客目前的點擊與他們先前最近一次購買之間所經過的時間。"
>abstract="**這可以幫助您**&#x200B;更加了解在您網站上購買商品後的訪客行為。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如更新您的網站以鼓勵後續購買。<br/>此範本使用「上次購買間隔天數」維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="檢視訪客存取您網站時最常使用的行動裝置螢幕尺寸。"
>abstract="**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的行動裝置螢幕尺寸來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="檢視訪客存取您網站時最常使用的行動裝置螢幕長度。"
>abstract="**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的行動裝置螢幕長度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="檢視訪客存取您的網站時最常使用的行動裝置螢幕寬度。"
>abstract="**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的行動裝置螢幕寬度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。"

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--countryGeoReport"
>title="檢視造訪網站的人們來自哪個國家/地區。"
>abstract="**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些國家/地區。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如利用資料來加強這些國家/地區的行銷工作，或者確保您的網站體驗在使用不同主要語言的國家/地區能達到最佳效果。<br/>此範本使用國家/地區維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--stateGeoReport"
>title="檢視造訪網站的人們來自哪個州 (美國國內)。此範本與地理區域範本相似，差別僅在限定於美國。"
>abstract="**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自美國的哪些州。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用資料來加強這些州的行銷工作。<br/>此範本使用美國州別維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--regionGeoReport"
>title="檢視造訪網站的人們來自哪個地理區域。區域指的是小於國家/地區但大於城市的地理範圍。在某些國家/地區，區域是指一個州、省或府/縣。在其他地方，則是指構成國、行政區或大都會區域。 "
>abstract="**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些區域。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用資料加強這些區域的行銷工作，或者確保您的網站體驗在使用不同主要語言的區域能達到最佳效果。<br/>此範本使用 ID (變數/地理位置) 和區域維度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cityGeoReport"
>title="檢視造訪網站的人們來自哪個城市。"
>abstract="**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些城市。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用資料加強這些城市的行銷工作。<br/>此範本使用城市維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--dmaGeoReport"
>title="檢視造訪網站的人們來自美國境內哪些指定行銷區域 (DMA)。"
>abstract="**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些區域。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用資料加強最成功區域的行銷工作。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--languageRankedReport"
>title="檢視訪客查看內容時偏好的最常用語言。"
>abstract="**這有助於您**&#x200B;更加了解訪客最常使用的語言。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最常用的語言加強本地化工作或行銷工作。<br/>此範本使用語言維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-technology-template"
>title="檢視人們用來存取您網站的技術相關資訊，例如作業系統、瀏覽器和裝置。"
>abstract="**這有助於您**&#x200B;更了解存取您網站時最常使用的技術。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如針對所使用的技術將您的網站最佳化。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserRankedReport"
>title="檢視人們存取您的網站時最常使用的瀏覽器名稱與版本。"
>abstract="**這有助於您**&#x200B;更加了解訪客最常用的瀏覽器。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用最常用的瀏覽器針對網站新版本進行測試，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。<br/>此範本使用瀏覽器維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserTypeRankedReport"
>title="檢視人們存取您的網站時最常使用的瀏覽器之製作組織名稱。這與瀏覽器範本不同，不會將相同瀏覽器的不同版本列為單獨的維度項目。"
>abstract="**這有助於您**&#x200B;更加了解訪客最常用的瀏覽器&#x200B;<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用最常用的瀏覽器針對網站新版本進行測試，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。<br/>此範本使用瀏覽器類型維度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappscreens"
>title="檢視與行動應用程式上每個畫面相關的事件、工作階段和人員數量。"
>abstract="**這有助於您**&#x200B;更了解您網站上的哪些畫面最受歡迎。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如改善最受歡迎畫面上的內容。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappactions"
>title="檢視人們在您的行動應用程式上執行的動作。"
>abstract="**這有助於您**&#x200B;更了解人們如何使用您的應用程式以及他們從中獲得的價值。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如可補充或改進最受歡迎功能的開發功能。"

<!-- markdownlint-enable MD034 -->

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-lifecycle-metrics-app-usage-template"
>title="檢視應用程式的使用者數量、啟動次數和首次啟動次數，以及平均工作階段長度。"
>abstract="**這可以幫助您**&#x200B;更加了解應用程式的使用量。<br/>**根據已知內容，您可以**&#x200B;採取各種行動，例如提升應用程式效能，使其能夠根據使用量進行擴展。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-journeys"
>title="檢視行動應用程式的主要使用模式。"
>abstract="**這可以幫助您**&#x200B;更加了解人們如何使用您的應用程式。<br/>**根據已知內容，您可以**&#x200B;採取各種行動，例如改進人們從一個螢幕轉到另一個螢幕的方式，以達到最常見的工作流程目標。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-key-metrics"
>title="檢視一些最常見的行動應用程式量度。"
>abstract="**這可以幫助您**&#x200B;更加了解行動應用程式的基本效能。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估應用程式的整體健康和效能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-messaging"
>title="檢視應用程式內傳送訊息和推播傳送訊息的效能資料。"
>abstract="**這可以幫助您**&#x200B;更加了解人們如何使用應用程式內傳送訊息的功能，以及推播通知如何有效地為您的應用程式帶來流量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如提升應用程式內傳送訊息推播通知的體驗。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-performance-template"
>title="檢視應用程式的執行情況，以及使用者在何處遇到問題。"
>abstract="**這可以幫助您**&#x200B;更加了解應用程式的使用者是否遇到速度緩慢或效能下降的問題。<br/>**根據已知內容，您可以**&#x200B;採取各種行動，例如修復現有問題，或在問題發生之前提升應用程式效能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-retention"
>title="檢視哪些使用者是應用程式最忠實的使用者，以及他們在應用程式中執行哪些操作。"
>abstract="**這可以幫助您**&#x200B;更加了解最忠實的使用者如何使用您的應用程式。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最忠實使用者正在使用的功能來改善您的行銷工作。"

<!-- markdownlint-enable MD034 -->

可使用以下範本：

| 範本名稱 | 為什麼使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **人員量度**] | 檢視與您品牌互動的人數。 <p>**這有助於您**&#x200B;更了解網站上的使用趨勢。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如測量近期行銷活動為您的網站帶來新訪客的有效性。</p> |
| **訪客設定檔** > **位置概觀** | 在地圖視覺效果中檢視訪客位置的概觀。<p>**這有助於您**&#x200B;更了解造訪您網站之訪客的所在位置。 </p><p>**根據已知內容，您可以**&#x200B;採取各種動作，例如將行銷資源集中於您認為最感興趣和機會最多的位置。</p><!-- This template uses the --> |
| **訪客設定檔** > **地理劃分** > **地理國家/地區** | 檢視造訪網站的人們來自哪個國家/地區。<p>**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些國家/地區。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如利用資料來加強這些國家/地區的行銷工作，或者確保您的網站體驗在使用不同主要語言的國家/地區能達到最佳效果。</p><p>此範本使用「國家/地區」維度。 </p> |
| **訪客設定檔** > **地理劃分** > **地理美國各州** | 檢視造訪網站的人們來自哪個州 (美國國內)。此範本與地理區域範本相似，差別僅在限定於美國。<p>**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自美國的哪些州。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用資料來加強這些州的行銷工作。</p><p>此範本使用「美國州別」維度。 </p> |
| **訪客設定檔** > **地理劃分** > **地理區域** | 檢視造訪網站的人們來自哪個地理區域。區域指的是小於國家/地區但大於城市的地理範圍。在某些國家/地區，區域是指一個州、省或府/縣。在其他地方，則是指構成國、行政區或大都會區域。 <p>**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些區域。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如使用資料加強這些區域的行銷工作，或者確保您的網站體驗在使用不同主要語言的區域能達到最佳效果。 </p><p>此範本使用 ID (變數/地理位置) 和「區域」維度。 </p> |
| **訪客設定檔** > **地理劃分** > **地理城市** | 檢視造訪網站的人們來自哪個城市。 <p>**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些城市。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如使用資料加強這些城市的行銷工作。 </p><p>此範本使用「城市」維度。 </p> |
| **訪客設定檔** > **地理劃分** > **地理美國 DMA** | 檢視造訪網站的人們來自美國境內哪些指定行銷區域 (DMA)。<p>**這有助於您**&#x200B;更加了解造訪網站的訪客最常來自哪些區域。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用資料加強最成功區域的行銷工作。 </p><!-- This template uses the --> |
| **訪客設定檔** > **語言** | 檢視訪客查看內容時偏好的最常用語言。 <p>**這有助於您**&#x200B;更加了解訪客最常使用的語言。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最常用的語言加強本地化工作或行銷工作。</p><p>此範本使用「語言」維度。</p> |
| **訪客設定檔** > **時區** | 檢視存取您網站之訪客所在的熱門時區。 <p>**這可以幫助您**&#x200B;更加了解訪客居住的時區。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將網站維修時間調整為受影響人數最少的時段。</p> |
| **訪客設定檔** > **網域** | 檢視存取您網站之訪客使用的熱門網域。 <p>**這可以幫助您**&#x200B;更加了解您的訪客來自哪些組織。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將最大的客戶群作為目標來進行內容設定。</p> |
| **訪客設定檔** > **頂層網域** | 檢視存取您網站之訪客使用的頂層網域。 <p>**這可以幫助您**&#x200B;更加了解您的訪客來自哪些組織。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如將最大的客戶群作為目標來進行內容設定。</p> |
| **訪客設定檔** > **技術** > **技術概觀** | 檢視人們用來存取您網站的技術相關資訊，例如作業系統、瀏覽器和裝置。 <p>**這有助於您**&#x200B;更了解存取您網站時最常使用的技術。</p><p>**根據已知內容，您可以**&#x200B;採取各種動作，例如針對所使用的技術將您的網站最佳化。</p> |
| **訪客設定檔** > **技術** > **瀏覽器** | 檢視人們存取您的網站時最常使用的瀏覽器名稱與版本。<p>**這有助於您**&#x200B;更加了解訪客最常用的瀏覽器。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用最常用的瀏覽器針對網站新版本進行測試，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p><p>此範本使用瀏覽器維度。 </p> |
| **訪客設定檔** > **技術** > **瀏覽器類型** | 檢視人們存取您的網站時最常使用的瀏覽器之製作組織名稱。這與瀏覽器範本不同，不會將相同瀏覽器的不同版本列為單獨的維度項目。<p>**這有助於您**&#x200B;更了解訪客最常用的瀏覽器</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如使用最常用的瀏覽器針對網站新版本進行測試，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。 </p><p>此範本使用「瀏覽器類型」維度。 </p> |
| **訪客設定檔** > **技術** > **瀏覽器寬度** | 檢視訪客用來存取您網站的熱門瀏覽器寬度。<p>**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的瀏覽器寬度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p><p>此範本使用「瀏覽器」維度。 </p> |
| **訪客設定檔** > **技術** > **瀏覽器高度** | 檢視訪客用來存取您網站的熱門瀏覽器高度。<p>**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的瀏覽器高度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p><p>此範本使用「瀏覽器」維度。 </p> |
| **訪客設定檔** > **技術** > **作業系統** | 檢視訪客存取您網站時使用的作業系統名稱與版本。<p>**這可以幫助您**&#x200B;更加了解訪客使用的最常見作業系統及其版本。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用熱門作業系統及版本來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p> |
| **訪客設定檔** > **技術** > **作業系統類型** | 檢視訪客存取您網站時使用的作業系統名稱。<p>**這能幫助您**&#x200B;更加了解訪客使用的最常見作業系統。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用熱門作業系統來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p> |
| **訪客設定檔** > **技術** > [!UICONTROL **行動電信業者**] | 檢視人們用來存取您的網站之行動裝置，由哪些電信公司提供行動網路連線。<p>**這有助於您**&#x200B;更加了解您的使用者群最常使用哪些行動電信業者。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同電信業者的網路功能自訂內容傳送方式，以確保流暢的使用者體驗。</p><p>此範本使用「行動電信業者」維度。</p> |
| **訪客保留率** > **回訪頻率** | 檢視人們用來存取您的網站之行動裝置，由哪些電信公司提供行動網路連線。<p>**這有助於您**&#x200B;更加了解您的使用者群最常使用哪些行動電信業者。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同電信業者的網路功能自訂內容傳送方式，以確保流暢的使用者體驗。</p><p>此範本使用「行動電信業者」維度。</p> |
| **訪客保留率** > **回訪數** | 檢視人們用來存取您的網站之行動裝置，由哪些電信公司提供行動網路連線。<p>**這有助於您**&#x200B;更加了解您的使用者群最常使用哪些行動電信業者。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同電信業者的網路功能自訂內容傳送方式，以確保流暢的使用者體驗。</p><p>此範本使用「行動電信業者」維度。</p> |
| **訪客保留率** > **造訪次數** | 檢視個別訪客造訪網站的次數。<p>**這可以幫助您**&#x200B;更加了解訪客返回您網站時的參與度。此維度會套用至訪客的期限，無論專案日期範圍為何。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如對常客調整行銷工作。</p><p>此範本使用「造訪數」維度。</p> |
| **訪客保留率** > **銷售週期** > **客戶忠誠度** | 檢視您網站上先前購買 0 次、先前購買 1 次、先前購買 2 次或先前購買 3 次以上的訪客數量。 <p>**這可以幫助您**&#x200B;更加了解您的網站如何影響購買行為。</p><p>**根據已知內容，您可以**&#x200B;採取各種動作，例如將焦點放在返回購買的訪客，藉此鼓勵新訪客也採取類似的行為。</p><p>此範本使用「客戶忠誠度」維度。</p> |
| **訪客保留率** > **銷售週期** > **首次購買間隔天數** | 檢視訪客首次瀏覽網站和進行購買之間的間隔天數。例如，如果訪客在首次造訪一天後購買，則所有後續造訪或事件均屬於「1 天」維度項目。<p>**這可以幫助您**&#x200B;更加了解訪客通常會在多久後進行購買。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如更新您的網站以促進訪客更快進行購買。</p><p>此範本使用「首次購買間隔天數」維度。</p> |
| **訪客保留率** > **銷售週期** > **上次購買的間隔天數** | 檢視訪客目前的點擊與他們先前最近一次購買之間所經過的時間。<p>**這可以幫助您**&#x200B;更加了解在您網站上購買商品後的訪客行為。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如更新您的網站以鼓勵後續購買。</p><p>此範本使用「上次購買間隔天數」維度。</p> |
| **行動** > **裝置** | 檢視人們存取您的網站所使用的行動裝置品牌和型號。<p>**這有助於您**&#x200B;更加了解您的使用者群最喜歡使用哪些行動裝置。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最常見的行動裝置將網站呈現最佳化。</p><p>此範本使用「行動裝置名稱」維度。</p> |
| **行動** > **裝置類型** | 檢視人們使用哪些類型的行動裝置存取您的網站，例如手機和平板電腦。<p>**這有助於您**&#x200B;更了解人們存取您的網站所使用的各種行動裝置。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如針對最常用的行動裝置類型將您的網站最佳化。</p><p>此範本使用「行動裝置類型」維度。</p> |
| **行動** > **製造商** | 檢視人們存取您的網站所使用的行動裝置由哪些製造商製造，例如 Apple 和 Samsung。<p>**這有助於您**&#x200B;更加了解您的使用者群最喜歡哪些製造商。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同製造商的能力自訂內容傳送方式，以確保流暢的使用者體驗。</p><p>此範本使用「行動製造商」維度。</p> |
| **行動** > **螢幕尺寸** | 檢視訪客存取您網站時最常使用的行動裝置螢幕尺寸。<p>**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的行動裝置螢幕尺寸來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p> |
| **行動** > **螢幕高度** | 檢視訪客存取您網站時最常使用的行動裝置螢幕長度。<p>**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的行動裝置螢幕長度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p> |
| **行動** > **螢幕寬度** | 檢視訪客存取您的網站時最常使用的行動裝置螢幕寬度。<p>**這可以幫助您**&#x200B;更加了解內容呈現給訪客的方式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如使用最常用的行動裝置螢幕寬度來測試新版本的網站，以提升網站品質。這樣做可以讓品質控管工作發揮最大效果。</p> |
| **行動裝置** > **行動應用程式使用情況** | 檢視應用程式的使用者數量、啟動次數和首次啟動次數，以及平均工作階段長度。<p>**這有助於您**&#x200B;更了解應用程式的使用量。 </p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如提升應用程式效能，使其能夠根據使用量進行擴展。</p><!-- This template uses the --> |
| **行動裝置** > **行動應用程式歷程** | 檢視行動應用程式的主要使用模式。 <p>**這有助於您**&#x200B;更了解人們如何使用您的應用程式。 </p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如改進人們從一個螢幕轉到另一個螢幕的方式，以達到最常見的工作流程目標。 </p><!-- This template uses the --> |
| **行動裝置** > **行動應用程式量度** | 檢視一些最常見的行動應用程式量度。 <p>**這可以幫助您**&#x200B;更加了解行動應用程式的基本效能。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如評估應用程式的整體健康和效能。</p><!-- This template uses the --> |
| **行動裝置** > **行動應用程式訊息傳送** | 檢視應用程式內傳送訊息和推播傳送訊息的效能資料。<p>**這可以幫助您**&#x200B;更加了解人們如何使用應用程式內傳送訊息的功能，以及推播通知如何有效地為您的應用程式帶來流量。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如提升應用程式內傳送訊息推播通知的體驗。</p><!-- This template uses the --> |
| **行動裝置** > **行動應用程式效能** | 檢視應用程式的執行情況，以及使用者在何處遇到問題。 <p>**這有助於您**&#x200B;更了解應用程式的使用者是否遇到速度緩慢或效能下降的問題。 </p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如修復現有問題，或在問題發生之前提升應用程式效能。</p><!-- This template uses the --> |
| **行動裝置** > **行動應用程式保留率** | 檢視哪些使用者是應用程式最忠實的使用者，以及他們在應用程式中執行哪些操作。 <p>**這可以幫助您**&#x200B;更加了解最忠實的使用者如何使用您的應用程式。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最忠實使用者正在使用的功能來改善您的行銷工作。</p><!-- This template uses the --> |
| **機器人** | 檢視有關您網站上機器人流量的頁面瀏覽量和趨勢。 <p>**這有助於您**&#x200B;更了解根據您設定的機器人規則，從報告中篩選過的機器人流量。</p><p>**根據已知內容，您可以**&#x200B;採取各種動作，例如繼續監視機器人活動以識別新模式。</p><!-- This template uses the --> |

### 贏取 {#web-acquisition}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="檢視您的網站如何吸引使用行動裝置的訪客。"
>abstract="**這有助於您**&#x200B;更加了解促成贏取客戶的各種因素，例如搜尋關鍵字、反向連結網域等。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最有成效的管道加強行銷工作。<br/>此範本使用跳出率量度和跳出次數量度。此範本亦使用「搜尋引擎」維度、「搜尋關鍵字」維度、「登入頁面」維度、「反向連結網域」維度、「追蹤程式碼」維度和「反向連結」維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="並排檢視您所有的 Google 和 Bing 付費搜尋資料。"
>abstract="**這可以幫助您**&#x200B;更加了解傳送到您網站的流量，以及客戶是否正在轉換。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如預估廣告行銷活動的成本效益。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="檢視訪客點擊搜尋結果中的哪一個頁面來進入您的網站。例如，若您的網站出現在搜尋引擎搜尋結果的第二頁，此變數的維度項目就是「搜尋頁面 2」。"
>abstract="**這有助於您**&#x200B;更了解您的頁面在搜尋結果中之排名。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作如改善您的 SEO 策略，以確保您的內容顯示在搜尋結果的第一頁中。"

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--marketing-channel-overview-template"
>title="使用自訂歸因時，此範本會顯示訪客如何到達您的網站。"
>abstract="**這有助於您**&#x200B;更加了解哪些行銷管道最有效。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對有效的行銷管道加重投資，並放棄投資效果較差的行銷管道。<br/>此範本使用 ID (變數/行銷管道) 維度和收入量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelRankedReport"
>title="檢視訪客在參與期間 (預設為 30 天) 符合的第一個行銷管道。"
>abstract="**這有助於您**&#x200B;更加了解哪些行銷管道將初始流量導向您的網站。<br/>**根據已知內容，您可以**&#x200B;採取各種行動，例如針對最有成效的領域加強行銷工作。<br/>此範本使用首次接觸管道維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelDetailRankedReport"
>title="檢視訪客在參與期間 (預設為 30 天) 符合之第一個行銷管道的詳細資訊。"
>abstract="**這有助於您**&#x200B;更加了解是什麼因素促成與行銷管道相符的點擊。例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來了解他們使用哪個搜尋引擎，或已搜尋哪個關鍵字。<br/>**根據已知內容，您可以**&#x200B;採取各種行動，例如針對最有成效的領域加強行銷工作。<br/>此範本使用首次接觸管道詳細資訊維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignConversionReport"
>title="檢視行銷活動的點進次數和結帳次數。"
>abstract="**這有助於您**&#x200B;更了解行銷活動如何促進轉換。<br/>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如確定哪些行銷活動會產生最高的 ROI。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-campaign-performance-template"
>title="檢視您的行銷活動績效的詳細資訊。"
>abstract="**這有助於您**&#x200B;更加了解與行銷活動相關的各種成功指標，例如收入、產品瀏覽數、訂單等。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對帶來最多收入的行銷活動加強行銷工作。<br/>此範本使用收入量度、產品瀏覽數量度、新增購物車量度、訂單量度和單位量度。此範本亦使用「追蹤程式碼」維度和「反向連結網域」維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-acquisition-template"
>title="檢視您的網站如何吸引訪客。"
>abstract="**這有助於您**&#x200B;更加了解促成贏取客戶的各種因素，例如搜尋關鍵字、反向連結網域等。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最有成效的管道加強行銷工作。<br/>此範本使用跳出率量度和跳出次數量度。此範本亦使用「搜尋引擎」維度、「搜尋關鍵字」維度、「登入頁面」維度、「反向連結網域」維度、「追蹤程式碼」維度和「反向連結」維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchKeywordRankedReport"
>title="檢視訪客造訪您網站所使用的搜尋關鍵字，無論是付費或免費。"
>abstract="**這有助於您**&#x200B;更加了解人們搜尋哪些關鍵字而帶來網站流量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如找出所使用的關鍵字和能夠帶來網站流量的關鍵字之間有哪些 SEO 差距，並彌補這些差距。<br/>此範本使用搜尋關鍵字維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidKeywordRankedReport"
>title="檢視訪客用來到達您網站的搜尋關鍵字 (與付費搜尋偵測相符)。"
>abstract="**這有助於您**&#x200B;更了解人們搜尋哪些關鍵字而帶來網站流量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如找出所使用的關鍵字和能夠帶來網站流量的關鍵字之間有哪些 SEO 差距，並彌補這些差距。<br/>此範本使用搜尋關鍵字 - 付費維度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalKeywordRankedReport"
>title="檢視訪客用來到達您網站的搜尋關鍵字 (與付費搜尋偵測不符)。"
>abstract="**這有助於您**&#x200B;更了解人們搜尋哪些關鍵字而帶來網站流量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如找出所使用的關鍵字和能夠帶來網站流量的關鍵字之間有哪些 SEO 差距，並彌補這些差距。<br/>此範本使用搜尋關鍵字 - 免費維度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchRankedReport"
>title="檢視訪客造訪您網站所使用的搜尋引擎，無論是付費或免費。"
>abstract="**這有助於您**&#x200B;更加了解人們使用哪些搜尋引擎而帶來網站流量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對為網站帶來最多流量的搜尋引擎加強 SEO 工作。<br/>此範本使用搜尋引擎維度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidRankedReport"
>title="檢視訪客用來到達您網站的搜尋引擎 (與付費搜尋偵測相符)。"
>abstract="**這有助於您**&#x200B;更加了解人們使用哪些搜尋引擎而帶來網站流量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對為網站帶來最多流量的搜尋引擎加強 SEO 工作。<br/>此範本使用搜尋引擎 - 付費維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalRankedReport"
>title="檢視訪客用來到達您網站的搜尋關鍵字 (與付費搜尋偵測不符)。"
>abstract="**這有助於您**&#x200B;更加了解人們使用哪些搜尋引擎而帶來網站流量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對為網站帶來最多流量的搜尋引擎加強 SEO 工作。<br/>此範本使用搜尋引擎 - 免費維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainRankedReport"
>title="檢視人們點進哪些網域來到達您的網站。"
>abstract="**這有助於您**&#x200B;更加了解哪些協力廠商網站為您的網站帶來最多流量。(外部網站上必須有連結，且訪客必須點選該連結來顯示維度項目。)<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如建立或調整內容，使更加符合來自熱門反向連結網域的訪客之興趣。<br/>此範本使用反向連結網域維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainOriginalRankedReport"
>title="檢視人們到達您的網站前點進的第一個反向連結網域。(設定後，該訪客 ID 的整個期限內都會包含相同的值。)"
>abstract="**這有助於您**&#x200B;更加了解哪些協力廠商網站會帶動原始流量到您的網站。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如建立或調整內容，使更加符合來自熱門原始反向連結網域的訪客之興趣。<br/>此範本使用原始反向連結網域維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerRankedReport"
>title="檢視訪客點擊哪一個 URL 以造訪您的網站。(外部 URL 上必須有連結，且訪客必須點選該連結來顯示維度項目。)"
>abstract="**這有助於您**&#x200B;更了解哪些特定 URL 為您的網站帶來最多流量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如建立或調整內容，使更符合來自最常見 URL 的訪客之興趣。<br/>此範本使用反向連結網域維度。</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerTypeRankedReport"
>title="檢視訪客點進哪個通用管道來到達您的網站。Adobe 會維護每個管道的規則。可能的管道包括搜尋引擎、社交網路、其他網站、硬碟或電子郵件。"
>abstract="**這有助於您**&#x200B;更加了解哪種類型的反向連結能為您的網站帶來最多流量。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如建立或調整內容，使更加符合來自特定管道的訪客之興趣。<br/>此範本使用反向連結類型維度。"

<!-- markdownlint-enable MD034 -->

可使用以下範本：

| 範本名稱 | 為什麼使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **行銷管道**] > [!UICONTROL **管道概觀報告**] | 使用自訂歸因時，此範本會顯示訪客如何到達您的網站。<p>**這有助於您**&#x200B;更加了解哪些行銷管道最有效。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對有效的行銷管道加重投資，並放棄投資效果較差的行銷管道。</p><p>此範本使用「ID (變數/行銷管道)」維度和「收入」量度。</p> |
| [!UICONTROL **行銷管道**] > [!UICONTROL **首次接觸管道**] | 檢視訪客在參與期間 (預設為 30 天) 符合的第一個行銷管道。 <p>**這有助於您**&#x200B;更加了解哪些行銷管道將初始流量導向您的網站。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如針對最有成效的領域加強行銷工作。</p><p>此範本使用「首次接觸管道」維度。</p> |
| [!UICONTROL **行銷管道**] > [!UICONTROL **首次接觸管道詳細資料**] | 檢視訪客在參與期間 (預設為 30 天) 符合之第一個行銷管道的詳細資訊。<p>**這有助於您**&#x200B;更加了解是什麼因素促成與行銷管道相符的點擊。例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來了解他們使用哪個搜尋引擎，或已搜尋哪個關鍵字。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如針對最有成效的領域加強行銷工作。</p><p>此範本使用「首次接觸管道詳細資料」維度。</p> |
| [!UICONTROL **行銷管道**] > [!UICONTROL **上次接觸管道**] | 檢視訪客在參與期間 (預設為 30 天) 符合的最近行銷管道。<p>**這有助於您**&#x200B;更了解哪些行銷管道將初始流量導向您的網站而造成轉換。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如針對最有成效的領域加強行銷工作。</p><p>此範本使用「上次接觸管道」維度。  </p> |
| [!UICONTROL **行銷管道**] > [!UICONTROL **上次接觸管道詳細資料**] | 檢視訪客在參與期間 (預設為 30 天) 符合的最近行銷管道詳細資訊。<p>**這有助於您**&#x200B;更加了解是什麼因素促成與行銷管道相符的點擊。例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來了解他們使用哪個搜尋引擎，或已搜尋哪個關鍵字。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如針對最有成效的領域加強行銷工作。 </p><p>此範本使用「上次接觸管道詳細資料」維度。 </p> |
| [!UICONTROL **促銷活動**] > [!UICONTROL **促銷活動轉換漏斗**] | 檢視行銷活動的點進次數和結帳次數。 <p>**這有助於您**&#x200B;更了解行銷活動如何促進轉換。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如確定哪些行銷活動會產生最高的 ROI。</p> |
| [!UICONTROL **促銷活動**] > [!UICONTROL **促銷活動成效**] | 檢視您的行銷活動績效的詳細資訊。<p>**這有助於您**&#x200B;更加了解與行銷活動相關的各種成功指標，例如收入、產品瀏覽數、訂單等。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如針對帶來最多收入的行銷活動加強行銷工作。 </p><p>此範本使用「收入」量度、「產品檢視次數」量度、「購物車新增」量度、「訂單數」量度和「單位」量度。此範本亦使用「追蹤程式碼」維度和「反向連結網域」維度。 </p> |
| [!UICONTROL **促銷活動**] > [!UICONTROL **追蹤程式碼**] | 檢視您網站上的追蹤程式碼名稱。您可以在網際網路中的不同位置放置具有不同查詢字串參數值的連結。<p>**這有助於您**&#x200B;更了解哪些連結最能成功吸引流量進入您的網站。在電子郵件、廣告、社群媒體貼文以及您組織使用的其他行銷活動中附加追蹤程式碼查詢字串，是很常見的情況</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如針對帶來最多收入的行銷活動加強行銷工作。</p><p>此範本使用「追蹤程式碼」維度。 </p> |
| **網頁收購** | 檢視您的網站如何吸引訪客。<p>**這有助於您**&#x200B;更加了解促成贏取客戶的各種因素，例如搜尋關鍵字、反向連結網域等。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最有成效的管道加強行銷工作。</p><p>此範本使用「退回率」量度和「退回」次數量度。此範本亦使用「搜尋引擎」維度、「搜尋關鍵字」維度、「登入頁面」維度、「反向連結網域」維度、「追蹤程式碼」維度和「反向連結」維度。  </p> |
| **行動收購** | 檢視您的網站如何吸引使用行動裝置的訪客。<p>**這有助於您**&#x200B;更加了解促成贏取客戶的各種因素，例如搜尋關鍵字、反向連結網域等。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最有成效的管道加強行銷工作。</p><p>此範本使用「退回率」量度和「退回」次數量度。此範本亦使用「搜尋引擎」維度、「搜尋關鍵字」維度、「登入頁面」維度、「反向連結網域」維度、「追蹤程式碼」維度和「反向連結」維度。  </p> |
| **Advertising Analytics：付費搜尋** | 並排檢視您所有的 Google 和 Bing 付費搜尋資料。 <p>**這可以幫助您**&#x200B;更加了解傳送到您網站的流量，以及客戶是否正在轉換。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種動作，例如預估廣告行銷活動的成本效益。</p> |
| **搜尋關鍵字 - 所有** | 檢視訪客造訪您網站所使用的搜尋關鍵字，無論是付費或免費。 <p>**這有助於您**&#x200B;更了解人們搜尋哪些關鍵字而帶來網站流量。 </p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如找出所使用的關鍵字和能夠帶來網站流量的關鍵字之間有哪些 SEO 差距，並彌補這些差距。</p><p>此範本使用「搜尋關鍵字」維度。 </p> |
| **搜尋關鍵字 - 付費** | 檢視訪客用來到達您網站的搜尋關鍵字 (與付費搜尋偵測相符)。<p>**這有助於您**&#x200B;更了解人們搜尋哪些關鍵字而帶來網站流量。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如找出所使用的關鍵字和能夠帶來網站流量的關鍵字之間有哪些 SEO 差距，並彌補這些差距。 </p><p>此範本使用「搜尋關鍵字 - 付費」維度。 </p> |
| **搜尋關鍵字 - 免費** | 檢視訪客用來到達您網站的搜尋關鍵字 (與付費搜尋偵測不符)。<p>**這有助於您**&#x200B;更了解人們搜尋哪些關鍵字而帶來網站流量。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如找出所使用的關鍵字和能夠帶來網站流量的關鍵字之間有哪些 SEO 差距，並彌補這些差距。</p><p>此範本使用「搜尋關鍵字 - 免費」維度。 </p> |
| **搜尋引擎 - 所有** | 檢視訪客造訪您網站所使用的搜尋引擎，無論是付費或免費。 <p>**這有助於您**&#x200B;更加了解人們使用哪些搜尋引擎而帶來網站流量。 </p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對為網站帶來最多流量的搜尋引擎加強 SEO 工作。</p><p>此範本使用「搜尋引擎」維度。 </p> |
| **搜尋引擎 - 付費** | 檢視訪客用來到達您網站的搜尋引擎 (與付費搜尋偵測相符)。<p>**這有助於您**&#x200B;更加了解人們使用哪些搜尋引擎而帶來網站流量。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對為網站帶來最多流量的搜尋引擎加強 SEO 工作。 </p><p>此範本使用「搜尋引擎 - 付費」維度。 </p> |
| **搜尋引擎 - 免費** | 檢視訪客用來到達您網站的搜尋關鍵字 (與付費搜尋偵測不符)。<p>**這有助於您**&#x200B;更加了解人們使用哪些搜尋引擎而帶來網站流量。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對為網站帶來最多流量的搜尋引擎加強 SEO 工作。</p><p>此範本使用「搜尋引擎 - 免費」維度。 </p> |
| **所有搜尋頁面排名** | 檢視訪客點擊搜尋結果中的哪一個頁面來進入您的網站。例如，若您的網站出現在搜尋引擎搜尋結果的第二頁，此變數的維度項目則為「搜尋頁面 2」。<p>**這有助於您**&#x200B;更了解您的頁面在搜尋結果中之排名。</p><p>**根據已知內容，您可以**&#x200B;採取各種動作，例如改善您的 SEO 策略，以確保您的內容顯示在搜尋結果的第一頁中。 </p> |
| **反向連結網域** | 檢視人們點進哪些網域來到達您的網站。<p>**這有助於您**&#x200B;更加了解哪些協力廠商網站為您的網站帶來最多流量。(外部網站上必須有連結，且訪客必須點選該連結來顯示維度項目。)</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如建立或調整內容，以更加符合來自熱門反向連結網域的訪客之興趣。 </p><p>此範本使用「反向連結網域」維度。 </p> |
| **原始反向連結網域** | 檢視人們到達您的網站前點進的第一個反向連結網域。(設定後，該訪客 ID 的整個期限內都會包含相同的值。)<p>**這有助於您**&#x200B;更加了解哪些協力廠商網站會帶動原始流量到您的網站。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如建立或調整內容，以更加符合來自熱門反向連結網域的訪客之興趣。 </p><p>此範本使用「原始反向連結網域」維度。 </p> |
| **反向連結** | 檢視訪客點擊哪一個 URL 以造訪您的網站。(外部 URL 上必須有連結，且訪客必須點選該連結來顯示維度項目。)  <p>**這有助於您**&#x200B;更了解哪些特定 URL 為您的網站帶來最多流量。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如建立或調整內容，以更符合來自最常見 URL 的訪客之興趣。 </p><p>此範本使用「反向連結網域」維度。 </p><p>此範本使用「反向連結類型」維度。 </p> |
| **反向連結類型** | 檢視訪客點進哪個通用管道來到達您的網站。Adobe 會維護每個管道的規則。可能的管道包括搜尋引擎、社交網路、其他網站、硬碟或電子郵件。<p>**這有助於您**&#x200B;更加了解哪種類型的反向連結能為您的網站帶來最多流量。</p><p>**根據已知內容，您可以**&#x200B;採取各種行動，例如建立或調整內容，以更加符合來自特定管道的訪客之興趣。</p><p>此範本使用「反向連結類型」維度。</p> |

### Mobile {#mobile-not-ready-for-use}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileCarrierRankedReport"
>title="檢視人們用來存取您的網站之行動裝置，由哪些電信公司提供行動網路連線。"
>abstract="**這有助於您**&#x200B;更加了解您的使用者群最常使用哪些行動電信業者。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同電信業者的網路功能自訂內容傳送方式，以確保流暢的使用者體驗。<br/>此範本使用行動電信業者維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceNameRankedReport"
>title="檢視人們存取您的網站所使用的行動裝置品牌和型號。"
>abstract="**這有助於您**&#x200B;更加了解您的使用者群最喜歡使用哪些行動裝置。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最常見的行動裝置將網站呈現最佳化。<br/>此範本使用行動裝置名稱維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceTypeRankedReport"
>title="檢視人們使用哪些類型的行動裝置存取您的網站，例如手機和平板電腦。"
>abstract="**這有助於您**&#x200B;更加了解人們存取您的網站所使用的各種行動裝置。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最常用的行動裝置類型將您的網站最佳化。<br/>此範本使用行動裝置類型維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileManufacturerRankedReport"
>title="檢視人們存取您的網站所使用的行動裝置由哪些製造商製造，例如 Apple 和 Samsung。"
>abstract="**這有助於您**&#x200B;更加了解您的使用者群最喜歡哪些製造商。<br/>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同製造商的能力自訂內容傳送方式，以確保流暢的使用者體驗。<br/>此範本使用行動製造商維度。"

<!-- markdownlint-enable MD034 -->

可使用以下範本：

| 範本名稱 | 為什麼使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **行動電信業者**] | 檢視人們用來存取您的網站之行動裝置，由哪些電信公司提供行動網路連線。<p>**這有助於您**&#x200B;更加了解您的使用者群最常使用哪些行動電信業者。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同電信業者的網路功能自訂內容傳送方式，以確保流暢的使用者體驗。</p><p>此範本使用「行動電信業者」維度。</p> |
| **裝置** | 檢視人們存取您的網站所使用的行動裝置品牌和型號。<p>**這有助於您**&#x200B;更加了解您的使用者群最喜歡使用哪些行動裝置。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最常見的行動裝置將網站呈現最佳化。</p><p>此範本使用「行動裝置名稱」維度。</p> |
| **裝置類型** | 檢視人們使用哪些類型的行動裝置存取您的網站，例如手機和平板電腦。<p>**這有助於您**&#x200B;更加了解人們存取您的網站所使用的各種行動裝置。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如針對最常用的行動裝置類型將您的網站最佳化。</p><p>此範本使用行動裝置類型維度。</p> |
| **製造商** | 檢視人們存取您的網站所使用的行動裝置由哪些製造商製造，例如 Apple 和 Samsung。<p>**這有助於您**&#x200B;更加了解您的使用者群最喜歡哪些製造商。</p><p>**根據了解到的內容，您可以**&#x200B;採取各種行動，例如根據不同製造商的能力自訂內容傳送方式，以確保流暢的使用者體驗。</p><p>此範本使用「行動製造商」維度。</p> |


