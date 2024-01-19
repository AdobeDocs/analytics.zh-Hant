---
description: 執行不同報表類型的步驟。
title: 執行不同的報表類型
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 2e8cac1b-d133-4095-b5db-886ce0566b82
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 94%

---

# 執行不同的報表類型

{{ra-eol}}

您可以在Analysis Workspace中執行許多不同型別的報表。 以下是幾個範例。

如需可用預先建立報表型別的完整清單，請參閱 [使用預先建立的報告](/help/analyze/analysis-workspace/reports/use-reports.md)

<!-- How do you do a Ranked Report in Workspace?

## Run a ranked report {#task_C570BA4A213F4F2EB7B30E012934BE7D}

In a ranked report, the table shows the rankings of the report pages in relation to the metric, according to number or percentage. Ranked reports can display multiple metrics in a report.

1. Generate a report, such as a [!UICONTROL Pages Report] ( [!UICONTROL **Workspace**] > **[!UICONTROL Engagement]** > **[!UICONTROL Pages]**).
1. In the report header, click **[!UICONTROL Ranked.]**
1. To rank the report, click a column heading in the table.

   Ranked reports can have up to 200 items listed in the table (such as products, categories, web pages, and so on) and ten metrics (revenue, orders, views, and so on).

-->

<!-- Can you do a Trended report? 

## Run a trended report {#task_F03B4E760B9E4EA29FC3F654E6316887}

Trended reports display metrics over time. You use this report type when you want to see how a segment performs from one time period to the next.

Most Conversion and Traffic reports have a Trended view available. Using the [!UICONTROL Calendar], you can show improvement for any time period breakdowns, including days of a month, weeks of a year, weeks of a quarter, months of a year, and so on. Trended reports show trends for a single metric (revenue, orders, views, and so on) for up to five items (such as products, categories, web pages, and so on).

**To run a trended report** 

1. Run a conversion or traffic report, such as **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

-->

## 執行流失報告 {#task_8FD97C8260464F9DA731A93DB8F80184}

[!UICONTROL 流失報表]會顯示瀏覽預先指定之頁面順序的訪客人數。也會顯示每個步驟之間的轉換率和流失率。

查看 Analysis Workspace 新的[流失分析](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=zh-Hant)面板！

1. 在 [!UICONTROL Adobe Analytics] 中，按一下&#x200B;**[!UICONTROL 「報表]** > **[!UICONTROL 路徑]** > **[!UICONTROL 頁面]** > **[!UICONTROL 流失」]**。
1. 在[!UICONTROL 流失報表]頁面上，按一下&#x200B;**[!UICONTROL 啟動流失 Report Builder]**。

1. 在[!UICONTROL 定義查核點]頁面上，指定您想用於報表的查核點。
1. 按一下&#x200B;**[!UICONTROL 「執行報表」]**。

## 執行頁面流程報告 {#task_133E8B87C3F04DA0A42D10CBA499305B}

「頁面流程報表」會顯示您的訪客存取頁面以及瀏覽網站的順序。此報表可協助解答

例如，按一下 **[!UICONTROL 工作區]** > **[!UICONTROL 報表]** > **[!UICONTROL 參與]** > **[!UICONTROL 下一頁和上一頁流量]**.

## 執行行銷管道報告 {#task_64ADED5CC75248319E06E3E029B47F78}

「行銷管道」報表可提供第一個接觸和最後一個接觸之管道配置的概述報表，並且搭配了標準的報表度量 (例如收入、訂購及成本)。這些報表可讓您分析每個頻道產生多少收入。

請參閱[行銷渠道](/help/components/c-marketing-channels/analyze-mc.md)說明系統，瞭解更多資訊。

## 執行異常偵測報告 {#task_4808C96327354D789C075823F5C3A049}

您可以執行 [異常偵測和貢獻分析](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) 僅適用於Analysis Workspace。

## 執行即時報告 {#task_5D25929C918E40B18965222FA94176B0}

說明如何檢視和解讀即時報表。

**[!UICONTROL 報表 > 網站量度 > 即時]**。

即時報表提供兩個主要報表 - 概述報表和詳細報表。這些分別包含許多小報表。

另請參閱 [即時報表概觀](/help/components/c-real-time-reporting/realtime.md) 以取得詳細資訊。

1. 檢視&#x200B;**[!UICONTROL 概述]**&#x200B;報表及其元件：![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> UI 元件 </th> 
   <th class="chdeschd"> 說明 </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>選取報表套裝</strong></td> 
   <td class="chdesc stentry"> 顯示此即時報表涵蓋的報表套裝。若要變更報表套裝，請參閱<a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/real-time-reports/t-realtime-admin.html?lang=zh-Hant"  >即時報表組態</a>。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>切換報表</strong></td> 
   <td class="chdesc stentry"> 讓您切換您設定的報表 (最多 3 個)。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>選擇時間範圍</strong></td> 
   <td class="chdesc stentry"> 讓您選擇報表中的所有小報表使用的整體時間範圍。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>設定報表</strong></td> 
   <td class="chdesc stentry"> 只有在您擁有管理員權限時，這個齒輪圖示連結才會出現。按一下連結，即可進入<span class="ignoretag"><span class="uicontrol">「管理工具</span> &gt; <span class="uicontrol">報表套裝</span> &gt; <span class="uicontrol">編輯設定</span> &gt; <span class="uicontrol">即時」</span></span>下的報表套裝管理員。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>全螢幕檢視</strong></td> 
   <td class="chdesc stentry"> 只有在監視器有特定的長寬比 (16:9 或 16:10) 而且瀏覽器支援它的情況下，全螢幕檢視圖示才會顯示。請注意，您無法在全螢幕模式中互動操作畫面 (按下 <span class="uicontrol">Esc</span> 即可退出)。全螢幕模式不會逾時。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>網站流量小報表</strong></td> 
   <td class="chdesc stentry"> 藍色趨勢線資料顯示整個網站的流量總計。X 軸使用常值標籤 (15 分鐘前、10 分鐘前)，不過目前值則顯示為即時運算式。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>網站總計小報表</strong></td> 
   <td class="chdesc stentry"> 對於最後 N 分鐘選擇的即時報表度量顯示網站總計計數。透過時間範圍選擇器即可設定「N」。 <p>箭頭顏色和方向均以下列演算法為準： 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">顯著增加 (向上箭頭)：&gt; 100% </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">增加 (向右上箭頭)：介於 5% 與 100% 之間 </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> 持平 (向右箭頭)：介於 5% 與 -5% 之間 </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> 減少 (向右下箭頭)：介於 -5% 與 -100% 之間 </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> 顯著減少 (向下箭頭)：&lt; -100% </li> 
      </ul> </p> <p>如果網站總計針對「例項」報表，這些例項將反映主要小報表的維度。如果例項特定名稱存在 (例如「頁面檢視」)，網站總計將報表該名稱。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>主要小報表</strong></td> 
   <td class="chdesc stentry"> 即時報表主要維度及其度量的報表。呈現所選時間範圍內該項目的趨勢線。度量總計代表整條趨勢線的總和。箭頭指示項目顯著增加、增加、持平、減少或顯著減少。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>搜尋對話方塊</strong></td> 
   <td class="chdesc stentry"> 搜尋將影響所有的小報表。只要您檢視報表，就會持續搜尋。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>排序依據... 最熱門/增加/減少</strong></td> 
   <td class="chdesc stentry"> 您可以切換為按照<span class="uicontrol">最熱門</span> (預設)、<span class="uicontrol">增加</span> (顯示最有成長) 和<span class="uicontrol">減少</span> (向下減少的維度) 進行排序。 <p>判斷增加或減少的公式如下：「即時」會查看最早的範例和倒數第二個範例，並執行簡單的「百分比變更」計算。因此，如果選擇「最後 15 分鐘」，而且 n 代表目前的分鐘數，則 n-1 會與 n-15 比較。即時目前不進行任何加權。目前分鐘不會計入，因為它尚未完成，而且可能產生錯誤的百分比變更。 </p> <p>此公式在即時報表中使用的所有度量均保持一致。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>次要 1 小報表</strong></td> 
   <td class="chdesc stentry"> 對於第二個提供報表的維度和度量提供即時報表。 <p>次要 1 小報表顯示前 4 個類別；第 5 個類別是其餘所有值的累計。對於各個類別，均提供該類別的總計原生視圖。此外，中央會顯示所有類別的總計。 </p> <p> 暫留在區段上會強調顯示相關類別，並且在環形圖下顯示類別趨勢線。 </p> <p> 暫留在行項目上會強調顯示行項目及相關區段，並且在環形圖下顯示類別趨勢線。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>次要 2 小報表</strong></td> 
   <td class="chdesc stentry"> 對於第三個提供報表的維度和度量提供即時報表。暫留在項目標籤上會向右滑動標籤，並對於所暫留的項目顯現趨勢線。 </td> 
   </tr> 
   </table>

2. 按一下主要小報表中的清單項目將啟動該清單項目的&#x200B;**[!UICONTROL 詳細資料]**&#x200B;檢視：![](assets/rtr_detail_report.png)

   | **項目趨勢小報表** | 對於最後 N 分鐘在概述報表中選取的項目顯現趨勢線。透過時間範圍選擇器即可設定 N。 |
   |---|---|
   | **項目總計小報表** | 對於最後 N 分鐘在概述報表中選取的項目顯現總計度量計數。透過時間範圍選擇器即可設定 N。 |
   | **關連次要 1 小報表** | 這個小報表相當類似次要 1 小報表。唯一的差別是填入此報表所用的資料來源：在此範例中，它顯示特定頁面 (您在概述報表的主要小報表中選取的頁面) 與檢視的例項之間的關連 (或劃分)。 |
   | **關連次要 2 小報表** | 這個小報表相當類似次要 2 小報表。唯一的差別是填入此報表所用的資料來源：在此範例中，它顯示特定頁面 (您在概述報表的主要小報表中選取的頁面) 與語言維度之間的關連 (或劃分)。 |
