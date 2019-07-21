---
description: 顯示訪客存取您網站網頁之順序的相關資訊。您可以收集訪客瀏覽您網站任何頁面之前及之後所處位置的相關資訊。
seo-description: 顯示訪客存取您網站網頁之順序的相關資訊。您可以收集訪客瀏覽您網站任何頁面之前及之後所處位置的相關資訊。
seo-title: 路徑報表
solution: Analytics
title: 路徑報表
topic: Ad Hoc Analysis
uuid: 5881cb1c-6d66-49Fe-ac84-70b82662 acd2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 路徑報表

顯示訪客存取您網站網頁之順序的相關資訊。您可以收集訪客瀏覽您網站任何頁面之前及之後所處位置的相關資訊。

## Paths reports {#concept_CB32E270FB9E4D929C91FDFE428CB224}

顯示訪客存取您網站網頁之順序的相關資訊。您可以收集訪客瀏覽您網站任何頁面之前及之後所處位置的相關資訊。

「路徑」報告包括標準的深入和可選的進階分析報告，它們可揭示已檢視頁面的點按資料流。您可以查明完整路徑、最長路徑和最受歡迎的路徑；透過圖表對頁面流量、流失和中途退出情況進行說明；隨時間顯示新模式和變更模式；以及分析登入與退出路徑。

** [!UICONTROL Next Page Flow] ** or ** [!UICONTROL Next Site Flow]**: Displays a two-level-deep branching graphic of a selected page (or section, department, and so on), that your visitors view after moving away from the selected page. 使用此報告可以分析和識別訪客在檢視選定頁面後，最常採取的步驟。您可以︰

* 瞭解檢視選取頁面後採用最為頻繁的步驟。
* 最佳化網站路徑設計，以便將訪客流量引至預期的目標頁面。
* 確認訪客進入了哪些除預期目標頁面之外的頁面。

** [!UICONTROL Next Page] ** (or next categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed after seeing a selected page. 例如，在選取並報告您整個網站時，此報告會顯示排名前 10 的登陸頁面，每個登陸頁面下方各列出 5 個最受歡迎的下一頁。這項資料可協助您瞭解哪些內容、功能和其他資料最能促使訪客瀏覽您的網站。

** [!UICONTROL Previous Page Flow] ** (or other previous categories flow): Displays two levels of the most popular pages that your visitors view before the selected page. 該報告還反白標示訪客登入網站的時間。

** [!UICONTROL Previous Page] ** (or other previous categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed before seeing a selected page on your site.

** [!UICONTROL Fallout] **: Displays the visit attrition and conversion rates between each checkpoint you define. 步驟依自上向下的順序排列，其中左邊是原始數字與百分數，右邊是轉換與流失百分比。

請參閱[流失報告](../../analyze/ad-hoc-analysis/c-reports-paths.md#concept_0ED452F3B1D04A19A59DD04D76D20347)，瞭解更多資訊。

** [!UICONTROL Path Length] **: Shows how deep visitors browse into your site (both by percentage and by total count). 也就是說，該報告將顯示訪客離開您網站前平均檢視的頁面數量。

** [!UICONTROL Page Analysis] **: Contains a subset of reports that let you analyze the following:

* ** [!UICONTROL Page Summary / Site Category Summary] **: Tells you everything you need to know about the page report. 此報告收集並整理單一頁面的特定資訊並在單一報告中展示此資訊。
* ** [!UICONTROL Reloads] **: Shows the number of times individual pages were reloaded by visitors.
* ** [!UICONTROL Time Spent on Page / Site Category] **: Displays the length of time that visitors browse individual pages in your site. 逗留時間分為 10 個類別: 少於 15 秒、15-30 秒、30-60 秒、1-3 分鐘、3-5 分鐘、5-10 分鐘、10-15 分鐘、15-20 分鐘、20-30 分鐘和超過 30 分鐘。
* ** [!UICONTROL Clicks to Page] **: Identifies the number of clicks visitors used to access each page in your site. 要測量頁面深度，需計算在該頁面之前檢視的頁面數量。

** [!UICONTROL Entries &amp; Exits] **: The [!UICONTROL Entry Page] report shows you, by percentage and by total visits, which pages on your site are the first ones seen by new visitors. 您可檢視︰

* ** [!UICONTROL Entry Pages] ** (or sections): Displays, by percentage and by total visits, which pages on your site are the first pages seen by a new visitor. 您可以使用該報告來識別您的網站中哪些網頁是最為繁忙的登入點；最佳化您網站上的主要登入點；以及將登入流量引至關鍵訊息。
* ** [!UICONTROL Original Entry Pages] **: Shows the first page viewed for first-time visitors to your site. 除非刪除他們的 Cookie 或沒有使用 Cookie 追蹤，否則每個使用者均只計算一次。
* ** [!UICONTROL Single Page Visits] **: Shows pages that are most often both the entry and exit pages for visitor browsing sessions.
* ** [!UICONTROL Exit Pages] **: Displays, by percentage and by total visits, the pages on your site that were the last pages visitors viewed before leaving your site.

## 流失報告 {#concept_0ED452F3B1D04A19A59DD04D76D20347}

[!UICONTROL 「流失報告」]顯示訪客離開 (流失) 和繼續瀏覽 (區間) 預先指定之頁面順序的位置，並會顯示每個步驟之間的轉換率和流失率。例如，您可以追蹤訪客在購買過程中的流失點。選取起點和結論點，然後新增中間點來建立網站導覽路徑。

<!-- 

c_reports_fallout.xml

 -->

您可以在存取或訪客層級分析流失資料。您亦可看到一個趨勢化路徑，顯示特定時段內的流失圖。您可以設定單一頁面或頁面群組作為報告查核點，也可以加入任何維度或度量的組合或順序。您亦可使用在 Marketing Reports &amp; Analytics 中設定的類別作為此報告的查核點。

此報告可用來分析:

* 網站特定過程的轉換率 (例如購買或註冊過程)。
* 更廣泛的一般流量流程: 此流量可顯示在瀏覽過首頁的人當中，有多少人接下來執行了搜尋操作，接著又有多少人最終瀏覽至某一特定項目。
* 網站上事件之間的關聯。關聯顯示在瀏覽過隱私政策的人當中，有百分之幾的人接下來執行了購買操作。

## 執行流失報告 {#task_3594E8BE55964C1C8B0BEC8DEABF82D3}

執行[!UICONTROL 「流失報告」]的步驟。

<!-- 

t_fallout.xml

 -->

1. Click **[!UICONTROL Reports]** &gt; **[!UICONTROL New Report]** &gt; **[!UICONTROL Fallout.]**

   Other Fallout reports are found in **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]**.

1. (可選) 如果要依據特定區段篩選資料，請拖曳區段至[!UICONTROL 「拖曳區段到此處」]欄位。
1. 拖曳維度項目至[!UICONTROL 「拖曳事件或維度項目到此處」]欄位。
1. Click **[!UICONTROL Show Fallout At]**Visit or Visitor level, depending on whether you want to view fallout at the visit level, or across visitor sessions.
1.  新增維度項目 (如頁面) 至報表。

## 指派頁面至流失報表 {#task_B386289703494FA7B5A40FF9F97CB537}

指派頁面至流失報表的步驟。

<!-- 

t_fallout_assign_pages.xml

 -->

1. Click **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Pages Fallout]**.
1. 在「維度」窗格中，找到要新增的頁面，然後將其拖曳至[!UICONTROL 拖曳事件或維度到此處]欄位。

## 流失報告 - 欄位說明 {#reference_74255CC8D6134F349FEBFEC72934C866}

[!UICONTROL 「流失」]報表的欄位說明。

<!-- 

r_dsc_fallout.xml

 -->

| 欄位 | 說明 |
|--- |--- |
| 顯示瀏覽或訪客層級的流失 | 可讓您切換瀏覽和訪客，分析訪客路徑。這些設定可讓您瞭解在訪客層級、跨瀏覽的訪客參與情形。網站分析、流量和流失報告可用於訪客路徑。變更此設定會重新執行報告，並將資料限制在該選取範圍。 |
| 成功總計 | 成功的總計指標。此值反映路徑中上一個查核點的值。 |
| 成功總計 % | 到達每個查核點的訪客百分比累積總計。 |
| 查核點 % | 兩個查核點間的成功百分比。(不累計。) |
| 包括所有訪客 | 新增所有訪客為初始查核點。 |
| 流失 | 可讓您查看訪客離開指定之查核點路徑後，所檢視的頁面。 |
| 區間 | 可讓您查看訪客在指定之查核點路徑中，下一個步驟所檢視的頁面。 |
