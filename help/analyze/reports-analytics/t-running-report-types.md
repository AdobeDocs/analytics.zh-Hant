---
description: 執行不同報表類型的步驟。
title: 執行不同的報表類型
topic: Reports,Reports and analytics
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 執行不同的報表類型

執行不同報表類型的步驟。


## 執行排名報告 {#task_C570BA4A213F4F2EB7B30E012934BE7D}

在排名報告中，表格會根據數量或百分比，顯示與度量相關的報告頁面排名。「排名」報告可在一個報告中顯示多個量度。

<!-- 

t_reports_ranked.xml

 -->

1. Generate a report, such as a [!UICONTROL Pages Report] ( **[!UICONTROL Reports]** &gt; **[!UICONTROL Site Content]** &gt; **[!UICONTROL Pages]**).
1. 在報表標題中，按一下&#x200B;**[!UICONTROL 排名]**。
1. 若要將報告排名，請按一下表格中的欄標題。

   排名報告最多可在表格中列示 200 個項目 (例如產品、類別、網頁等等) 和 10 個度量 (收入、訂購、檢視等等)。

## 執行趨勢報告 {#task_F03B4E760B9E4EA29FC3F654E6316887}

「趨勢」報告顯示隨時間變化的度量。當您想瞭解一個部門從一個時間段到下一個時間段如何表現時，可使用此報告類型。

<!-- 

t_reports_trended.xml

 -->

大多數轉換報告和流量報告具有可用的趨勢檢視。使用[!UICONTROL 日曆]，您可顯示任何時段劃分的改進，包括一個月中的某些天、一年中的某些週、一個季度中的某些週、一年中的某些月等等。趨勢報告顯示單個度量 (收入、訂購、檢視等等) 的趨勢，可多達五個項目 (例如產品、類別、網頁等等) 的趨勢。

**若要執行趨勢報告**

1. Run a conversion or traffic report, such as **[!UICONTROL Reports]** &gt; **[!UICONTROL Site Content]** &gt; **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

## 執行轉換漏斗報告 {#task_B926A74AA6A641138C2986C1635120CB}

「轉換漏斗」報告顯示經由一組事件以執行所需動作的訪客之百分比。例如，您可以看到有多少訪客從瀏覽網站逐漸發展為向購物車新增物品，然後再到購買。此報告亦顯示中途放棄的數量。

<!-- 

t_reports_conversion_funnel.xml

 -->

To run this report, select a report, such as a Pages report ( **[!UICONTROL Reports]** &gt; **[!UICONTROL Campaigns]** &gt; **[!UICONTROL Tracking Code]** &gt; **[!UICONTROL Campaign Conversion Funnel]**).

如需相關說明，請參閱[轉換報告](https://marketing.adobe.com/resources/help/en_US/reference/reports_conversion.html)。

## 執行流失報告 {#task_8FD97C8260464F9DA731A93DB8F80184}

[!UICONTROL 流失報告]會顯示瀏覽預先指定之頁面順序的訪客人數。也會顯示每個步驟之間的轉換率和流失率。

<!-- 

t_reports_fallout.xml

 -->

查看 Analysis Workspace 新的[流失分析](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/fallout_flow.html)面板!

1. In [!UICONTROL Adobe Analytics], click **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Fallout]**.
1. On the [!UICONTROL Fallout Report] page, click **[!UICONTROL Launch the Fallout Report Builder]**.

   ![步驟結果](assets/fallout_add_items.png)

1. 在[!UICONTROL 定義查核點]頁面上，指定您想用於報告的查核點。
1. Click **[!UICONTROL Run Report]**.

   ![步驟結果](assets/fallout_report.png)

>[!MORELIKETHIS]
>
>* [流失報告說明](https://marketing.adobe.com/resources/help/en_US/reference/reports_fallout.html)


## 執行頁面流程報告 {#task_133E8B87C3F04DA0A42D10CBA499305B}

「頁面流程報告」會顯示您的訪客存取頁面以及瀏覽網站的順序。此報告可協助解答

<!-- 

t_reports_page_flow.xml

 -->

查看 Analysis Workspace 新的[流量視覺化](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html)!

執行[路徑](https://marketing.adobe.com/resources/help/en_US/reference/reports_paths.html)報告。

For example, click **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Next Page Flow]**.

![](assets/page_flow.png)

請從左至右閱讀此報告，並從選定頁面開始。在選取頁面後檢視的頁面將圖示為延伸到右側的分支。

檢視每個後續頁面的百分比顯示在頁面名稱的旁邊。連接到每個下一頁的線條寬度描繪了該相關百分比。

**[!UICONTROL 路徑檢視]**: 指出以顯示的路徑檢視某個頁面的次數。

例如，「隱私權原則」頁面的頁面檢視總次數可能為 10,000 次，但有 500 次是在進入「首頁」前直接檢視的。這樣，就可使用術語路徑檢視。

線條的相對寬度可說明相對百分比。依照預設，此報告顯示 5 個 2 級分支和 5 個 3 級分支。您可以將要檢視的分支數量增加到 10 個 2 級分支和 5 個 3 級分支。這會增加報表的高度，並很可能需要透過捲動來檢視整個圖形。

## 執行漏斗報告 {#task_2BBF6FACD48F479E8B2EE458919941CB}

您可以選取成功事件並將其新增至[!UICONTROL 購買轉換漏斗]報告或[!UICONTROL 產品轉換漏斗]報告。

<!-- 

t_reports_funnel.xml

 -->

1. Click **[!UICONTROL Reports]** &gt; **[!UICONTROL Products]** &gt; [Products Conversion Funnel](https://marketing.adobe.com/resources/help/en_US/reference/reports_conversion_funnel.html).

## 執行行銷管道報告 {#task_64ADED5CC75248319E06E3E029B47F78}

「行銷管道」報告可提供第一個接觸和最後一個接觸之管道配置的概述報告，並且搭配了標準的報告度量 (例如收入、訂購及成本)。這些報告可讓您分析每個頻道產生多少收入。

<!-- 

t_reports_marketing_channel.xml

 -->

請參閱[行銷渠道](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html)說明系統，瞭解更多資訊。

## 執行異常偵測報告 {#task_4808C96327354D789C075823F5C3A049}

說明如何解讀異常偵測中的摘要和個別度量表。

<!-- 

t_anomaly_view.xml

 -->

查看 Analysis Workspace 內新的[「異常偵測」和「貢獻邊際分析」](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/anomaly_detection.html)功能!

**[!UICONTROL 報表]** &gt;網 **[!UICONTROL 站量度]** &gt; **[!UICONTROL 異常偵測]** 。

> [!NOTE] 您也可以從分析工作區專案中執行異常偵測。 [更多...](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/anomaly_detection.html)

如需設定異常偵測的資訊，請參閱[參考指南](https://marketing.adobe.com/resources/help/en_US/sc/user/index.html#Setting_up_Anomaly_Detection)。

異常偵測顯示兩種圖表：摘要圖表和個別度量圖表。只有在至少對於度量偵測到一個異常時，個別度量圖表才會顯示。

<table id="table_88163CD8FC164342855D90D01F9C581A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>圖表類型 </p> </th> 
   <th colname="col2" class="entry"> <p>用途 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>摘要圖表 </p> <p><img placement="break"  src="assets/ad_summary_chart.png" width="570px" id="image_1CD4C4770BAA43C4AD7CBB824AD41338" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_D26DA3024CD7468291369F549557B28A"> 
      <li id="li_1C22B6E02FFB479FB71EFAD89EB37A4E">各個方塊代表一個每天追蹤的異常，這對應於下方的度量。 </li> 
      <li id="li_8FC587D3FF4E452D83263CC7A10B6675">綠色表示高於趨勢線的異常，藍色表示低於趨勢線的異常。 </li> 
      <li id="li_25135AB691BF443599AF2A3A60E2E71A">指出異常的強度：異常愈大，資料點的顏色愈深，而且愈遠離趨勢線。 </li> 
      <li id="li_0C42AFA8897D420D8AB1A5D0F65B3B3A">按一下個別異常，會將該異常的個別量度圖表顯示於頂端 (位在摘要圖表下方)。 </li> 
      <li id="li_85C0F426952547B5A75D6BD31DE19CA5">偏差百分比值 (圖表左邊) 的計算方式如下： 
       <ul id="ul_BEC0A88BFFAC4CF78BC9885FEB749694"> 
        <li id="li_1BAB2F50482745B69937DFAF1E09982E">如果上限和預期值相同，則偏差百分比為 100% </li> 
        <li id="li_CA48064F5788448C8646CCE196161237">否則偏差百分比為(（實際值——上界值）/（上界值——預期值）)* 100 </li> 
        <li id="li_4090357A0D214BC7B1C3DE0615875554">如果下界和預期值相同，則偏差百分比為-100% </li> 
        <li id="li_EF694E1A4E874ECD94E1E8F7302E494F">否則偏差百分比為(（下限值——實際值）/（預期值——下限值）)* -100 </li> 
       </ul> </li> 
      <li id="li_5C05EF7023484CC993E96D63E842B65C">按一下「<span class="uicontrol">顯示區段</span>」會開啟區段邊欄，供您套用區段至異常偵測報表。<a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/"  >深入了解</a>區段。 </li> 
      <li id="li_1B41CABF13D1407886C68EE3BC201E60">按一下「<span class="uicontrol">編輯量度</span>」可讓您選取和取消選取您要偵測異常的量度。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>個別度量圖表 </p> <p><img placement="break"  src="assets/metric_report.png" width="570px" id="image_5BBECFD91CF14478AA4761E6256BBCB9" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_739C5687013743A29B63089FDA763F45"> 
      <li id="li_456A0BDA4D4E46CE9CC1C3DBAA1E2220">將個別趨勢度量的異常資料點 (包括計算的度量) 顯示為點。 </li> 
      <li id="li_89FD847C65F04F48BCA7CD38D0EC51CD">在頂端顯示最近的異常，然後按照異常數排序。 </li> 
      <li id="li_98B97A9706DE4455B8D8850904CBDE03">顯示實線指出目前收集的實際資料。這會與預測和誤差限度相比，判斷資料點是否異常。 </li> 
      <li id="li_0EEA38DDDC344BF3879430E67D74EB72">顯示虛線，表示按照歷史資料 (也就是訓練時段) 進行的預測。 </li> 
      <li id="li_035BD2725D004AEDB630BF8DFF4DA4F3">以灰色陰影顯示上下 95% 容限/限度。 </li> 
      <li id="li_021A3D1F2EDB4319B9B39620EF1C038A">讓您按一下度量名稱旁邊的向上或向下箭頭，收合和展開個別報告。 </li> 
      <li id="li_722E4B9FC21047AC96D7B143197E293D">回應概述報告 (見上文) 中的向下切分，變更度量報表出現的順序 </li> 
      <li id="li_A2441169B185475AA68A64F81E6E40B8">讓您使用搜尋詞篩選圖表，例如「頁面」顯示所有頁面相關度量。 </li> 
      <li id="li_F1BBBFCA8E2A43C29658E4FCAA36C904">讓您顯示您定義的所有度量或僅顯示有異常的度量。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定異常偵測 {#task_AF347B34F56E44A6AE70E019B6EB2F08}

對於異常偵測選取報告套裝、度量和訓練/檢視期間。

<!-- 

t_anomaly_config.xml

 -->

您可以分別設定各個報告套裝的異常偵測。

1. 導覽至「**[!UICONTROL Analytics &gt; 報表 &gt; 網站量度 &gt; 異常偵測]**。
1. 選擇您要每日追蹤異常偵測的報告套組。若要顯示報表套裝，請按一下報表套裝選取器下拉式功能表。
1. To select the metrics and/or define filtered metrics, click **[!UICONTROL Edit Metrics]** at the top right of the screen:  ![](assets/metrics_icon.png).

   您可以從所有度量的清單或追蹤度量的清單選取度量 (包括計算的度量)。您也可以篩選特定詞彙以縮小清單。1. Once the report has been generated, define the **[!UICONTROL Training Period]** and the **[!UICONTROL View Period]** for anomaly detection. (可以將訓練時段視為演算法的「學習時段」。) 

   ![](assets/view_training_periods.png)

   請記住：

* 訓練時段將在視圖時段開始後立即結束。
* 兩者的預設值為 30 天，您可以將兩者延長到 60 或 90 天。
* 延長訓練時段可以讓擴大資料的範圍，而且可以減少異常的大小。

   每次您變更參數，異常偵測度量報告都會重新整理。
1. (Optional) Apply segments to the report by clicking **[!UICONTROL Show Segments]** and selecting one or more existing segments or creating a new segment and applying it.

   ![](assets/ad_top_menu.png)

   如需建立和管理區段的詳細資訊，請參閱[分析分段指南](https://marketing.adobe.com/resources/help/en_US/analytics/segment/)。1. (可選) 收藏報表或將報表設為書籤。
1. (選用) 變更視圖時段的結束日期。預設值為昨日。
1. 您現在可以開始解讀報告。[檢視異常偵測圖表](/help/analyze/reports-analytics/t-running-report-types.md#task_4808C96327354D789C075823F5C3A049)。

## 執行即時報告 {#task_5D25929C918E40B18965222FA94176B0}

說明如何檢視和解讀即時報告。

<!-- 

reports_realtime.xml

 -->

**[!UICONTROL 報表 &gt; 網站量度 &gt; 即時]**。

即時報告提供兩個主要報告 - 概述報告和詳細報告。這些分別包含許多小報告。

如需設定即時報告的資訊，請參閱[分析參考指南](https://marketing.adobe.com/resources/help/en_US/reference/index.html#RealTime_Reports_Configuration)。

1. Take a look at the **[!UICONTROL Overview]** report and its components:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> UI 元件 </th> 
   <th class="chdeschd"> 說明 </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>選取報表套裝</strong></td> 
   <td class="chdesc stentry"> 顯示此即時報告涵蓋的報告套裝。若要變更報告套裝，請參閱<a href="https://marketing.adobe.com/resources/help/en_US/reference/t_realtime_admin.html"  >即時報告組態</a>。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>切換報告</strong></td> 
   <td class="chdesc stentry"> 讓您切換您設定的報告 (最多 3 個)。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>選擇時間範圍</strong></td> 
   <td class="chdesc stentry"> 讓您選擇報告中的所有小報告使用的整體時間範圍。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>設定報表</strong></td> 
   <td class="chdesc stentry"> 只有在您擁有管理員權限時，這個齒輪圖示連結才會出現。按一下它將進入<span class="ignoretag"><span class="uicontrol">管理工具</span> &gt; <span class="uicontrol">報告套裝</span> &gt; <span class="uicontrol">編輯設定</span> &gt; <span class="uicontrol">即時</span></span>下的報告套裝管理員。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>全螢幕檢視</strong></td> 
   <td class="chdesc stentry"> 只有在監視器有特定的長寬比 (16:9 或 16:10) 而且瀏覽器支援它的情況下，全螢幕檢視圖示才會顯示。請注意，您無法在全螢幕模式中互動操作畫面 (按下 <span class="uicontrol">Esc</span> 即可退出)。全螢幕模式不會逾時。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>網站流量小報告</strong></td> 
   <td class="chdesc stentry"> 藍色趨勢線資料顯示整個網站的流量總計。X 軸使用常值標籤 (15 分鐘前、10 分鐘前)，不過目前值則顯示為即時運算式。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>網站總計小報告</strong></td> 
   <td class="chdesc stentry"> 對於最後 N 分鐘選擇的即時報告度量顯示網站總計計數。透過時間範圍選擇器即可設定「N」。 <p>箭頭顏色和方向均以下列演算法為準: 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">顯著增加 (向上箭頭): &gt; 100% </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">增加 (向右上箭頭): 介於 5% 與 100% 之間 </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> 持平 (向右箭頭): 介於 5% 與 -5% 之間 </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> 減少 (向右下箭頭): 介於 -5% 與 -100% 之間 </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> 顯著減少 (向下箭頭): &lt; -100% </li> 
      </ul> </p> <p>如果網站總計針對「例項」報告，這些例項將反映主要小報告的維度。如果例項特定名稱存在 (例如「頁面檢視」)，網站總計將報告該名稱。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>主要小報告</strong></td> 
   <td class="chdesc stentry"> 即時報告主要維度及其度量的報告。呈現所選時間範圍內該項目的趨勢線。度量總計代表整條趨勢線的總和。箭頭指示項目顯著增加、增加、持平、減少或顯著減少。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>搜尋對話方塊</strong></td> 
   <td class="chdesc stentry"> 搜尋將影響所有的小報告。只要您檢視報告，就會持續搜尋。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>排序依據... 最熱門/增加/減少</strong></td> 
   <td class="chdesc stentry"> 您可以切換為按照<span class="uicontrol">最熱門</span> (預設)、<span class="uicontrol">增加</span> (顯示最有成長) 和<span class="uicontrol">減少</span> (向下減少的維度) 進行排序。 <p>以下是用以判斷獲益者或損失者的公式：即時檢視最早的範例和最新的範例，並執行簡單的「%變更」計算。 因此，如果選取「最近15分鐘」，且n代表目前分鐘，則n-1會與n-15比較。 即時目前不進行任何加權。目前分鐘不會計入，因為它尚未完成，而且可能產生錯誤的百分比變更。 </p> <p>此公式在即時報告中使用的所有度量均保持一致。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>次要 1 小報告</strong></td> 
   <td class="chdesc stentry"> 對於第二個提供報告的維度和度量提供即時報告。 <p>次要 1 小報告顯示前 4 個類別；第 5 個類別是其餘所有值的累計。對於各個類別，均提供該類別的總計原生視圖。此外，中央會顯示所有類別的總計。 </p> <p> 暫留在區段上會強調顯示相關類別，並且在環形圖下顯示類別趨勢線。 </p> <p> 暫留在行項目上會強調顯示行項目及相關區段，並且在環形圖下顯示類別趨勢線。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>次要 2 小報告</strong></td> 
   <td class="chdesc stentry"> 對於第三個提供報告的維度和度量提供即時報告。暫留在項目標籤上會向右滑動標籤，並對於所暫留的項目顯現趨勢線。 </td> 
   </tr> 
   </table>

1. Click a list item in the Primary Reportlet to launch the **[!UICONTROL Details]** view for that list item:  ![](assets/rtr_detail_report.png)

   | **項目趨勢小報告** | 對於最後 N 分鐘在概述報告中選取的項目顯現趨勢線。透過時間範圍選擇器即可設定 N。 |
   |---|---|
   | **項目總計小報告** | 對於最後 N 分鐘在概述報告中選取的項目顯現總計度量計數。透過時間範圍選擇器即可設定 N。 |
   | **關連次要 1 小報告** | 這個小報告相當類似次要 1 小報告。唯一的差別是填入此報告所用的資料來源: 在此範例中，它顯示特定頁面 (您在概述報告的主要小報告中選取的頁面) 與檢視的例項之間的關連 (或劃分)。 |
   | **關連次要 2 小報告** | 這個小報告相當類似次要 2 小報告。唯一的差別是填入此報告所用的資料來源: 在此範例中，它顯示特定頁面 (您在概述報告的主要小報告中選取的頁面) 與語言維度之間的關連 (或劃分)。 |
