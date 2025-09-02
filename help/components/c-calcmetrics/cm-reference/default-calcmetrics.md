---
description: Adobe 提供各種您可使用的計算量度。此頁面列出這些量度及其預期用途。
title: 預設計算量度
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: ht
source-wordcount: '758'
ht-degree: 100%

---

# 預設計算量度

Adobe Analytics 提供各種計算量度，以涵蓋最常見的使用案例。這些計算量度在 Analysis Workspace 中預設可用。

以下是 Adobe 提供的每個計算量度清單，包括其預定功能以及用於計算的基礎公式：

>[!NOTE]
>
>除了本頁所述的預設計算量度之外，您還可以在報告套裝中新增其他計算量度。
>
>您可以：
>
> * 如[計算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)中所述，新增串流媒體服務的預設計算量度
> * 如[計算和進階計算量度](/help/components/c-calcmetrics/cm-overview.md)所述，使用現有量度建立自訂計算量度。
>

>[!TIP]
>
>使用[資料字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)更深入地檢查預設計算量度的定義，以及構成該定義的個別元件。
>



| 計算量度名稱 | 函數 | 公式 |
| --- | --- | --- |
| 取得連結點按次數 | 為推動網站流量的連結點按次數。 | `[Campaign Click-throughs]` |
| 動作 | 應用程式中執行的動作總數 | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| 應用程式使用者 | 行動應用程式的使用者總數 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 平均工作階段長度 (行動裝置) | 在單一工作階段內訪客在網站上逗留的平均時間量。 | 空白 |
| 平均網站逗留時間 | 訪客離開之前在網站上停留的平均時間量。 | `[Average Time Spent on Site (Seconds)]` |
| 退回率 | 造訪數包含單一點按與該頁面上的造訪數之間的比率。此量度可協助您了解哪些維度項目具有最高的退回率，或查看網站在特定期間內彙總的總退回率。 | `[Bounces] / [Entries]` |
| 機器人頁面檢視次數比率 | 機器人頁面檢視次數與總頁面檢視次數的比率。 | `[Bot Page Views] / [Page Views]` |
| 內容速度 | 在網站上建立和發佈新內容的速度，以及新內容產生使用者參與的速度。 | `[Page Views] / [Visits]` |
| 轉換率 | 採取所需動作 (例如購買) 的訪客的百分比。 | `[Orders] / [Visits]` |
| 登入率 | 從指定頁面進入網站的訪客佔網站工作階段總數的百分比。 | `[Entries] / [Visits]` |
| 預估的不重複訪客 (ITP 2.1) | 針對 ITP 訪客 (Safari 瀏覽器上的使用者)，將不重複訪客數量除以 2 或更少。此計算量度假設您使用客戶端 JavaScript (而不是使用 CNAME 實施) 來設定 Cookie。從 ITP 2.1 開始，使用客戶端 JavaScript 設定 cookie 的實施受到影響。詳細資訊請參閱[智慧型追蹤預防](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Experience Cloud ID 涵蓋範圍 | 擁有 Experience Cloud ID 的訪客的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 退出率 | 檢視特定頁面後離開網站的訪客百分比。 | `[Exits] / [Visits]` |
| ITP 2.1 不重複訪客/不重複訪客 | 透過 ITP 2.1 Cookie 限制影響的瀏覽器不重複訪客百分比。 | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| 訂單協助 | 管道或來源促成客戶的購買歷程但未促成最終購買的次數。 | `[Orders (Visit Participation)] - [Orders]` |
| 訂單數/造訪數 | 造訪網站並完成交易的百分比。 | `[Orders] / [Visits]` |
| 訂單數/訪客數 | 每個網站訪客所產生的平均訂單或交易數。 | `[Orders] / [Unique Visitors]` |
| 頁面檢視次數/預估的不重複訪客 (ITP 2.1) | 預估的不重複訪客 (ITP 2.1) 的平均頁面檢視次數。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| 頁面檢視次數/不重複訪客 | 網站每個不重複訪客的檢視頁面平均數。 | `[Page Views] / [Unique Visitors]` |
| 頁面檢視次數/造訪數 | 使用者在單次造訪網站期間檢視的頁面平均數。 | `[Page Views] / [Visits]` |
| 頁面速度 | 一則內容所產生的額外頁面檢視次數。此量度可以協助您確定哪些內容可以推動其他參與度。 | `[Page Views] / [Visits]` |
| 重新載入/頁面檢視次數 | 導致頁面重新載入或重新整理的頁面檢視的百分比。 | `[Reloads] / [Page Views]` |
| 收入/訂單量 | 網站上每筆完成的交易或訂單所產生的平均收入金額。 | `[Revenue] / [Orders]` |
| 收入/造訪數 | 單次造訪網站所產生的平均收入金額。 | `[Revenue] / [Visits]` |
| 收入/訪客 | 每個網站訪客所產生的平均收入金額。 | `[Revenue] / [Unique Visitors]` |
| 狀態檢視 | 對應用程式的不同狀態或畫面的檢視次數。 | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| 逗留時間/使用者 (狀態) | 訪客在網站上的特定狀態中逗留的平均時間長度 | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 不重複訪客/7 天後返回的不重複訪客 | 在 7 天或更長時間後回訪的不重複訪客的百分比。 | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| 使用者 (行動) | 行動應用程式的使用者總數 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 造訪數/訪客 | 不重複訪客造訪網站的平均次數。 | `[Visits] / [Unique Visitors]` |
| 加權退回率 | 函數 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
