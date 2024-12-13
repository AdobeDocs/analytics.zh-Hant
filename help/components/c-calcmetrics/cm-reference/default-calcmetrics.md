---
description: Adobe提供您能使用的各種計算量度。 此頁面列出這些量度及其預期用途。
title: 預設計算量度
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 40%

---

# 預設計算量度

Adobe Analytics提供各種計算量度，以涵蓋最常見的使用案例。 這些計算量度預設可在Analysis Workspace中使用。

以下為Adobe提供的每個計算量度清單，以及其預計的函式以及用於計算該函式的基礎公式：

>[!NOTE]
>
>除了此頁面所述的預設計算量度外，您也可以新增其他計算量度至報表套裝。
>
>您可以：
>
> * 新增串流媒體集合的預設計算量度，如[計算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)中所述
> * 從現有量度建立自訂計算量度，如[計算與進階計算量度](/help/components/c-calcmetrics/cm-overview.md)中所述。


| 計算量度名稱 | 函數 | 公式 |
| --- | --- | --- |
| 贏取連結點按次數 | 為增加網站流量的連結點按次數。 | `[Campaign Click-throughs]` |
| 動作 | 應用程式中執行的動作總數 | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| 應用程式使用者 | 行動應用程式的使用者總數 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 平均工作階段長度（行動） | 訪客在單一工作階段中花費在網站上的平均時間。 | 空白 |
| 網站平均逗留時間 | 訪客離開或導覽離開前在網站上逗留的平均時間。 | `[Average Time Spent on Site (Seconds)]` |
| 反彈率 | 包含單一點選的造訪次數與該頁面上的造訪次數之間的比率。 此量度可協助您瞭解哪些維度專案具有最高的反彈率，或檢視網站在一段時間內彙總的反彈率。 | `[Bounces] / [Entries]` |
| 機器人頁面檢視比率 | 機器人頁面檢視次數與頁面檢視總次數之間的比率。 | `[Bot Page Views] / [Page Views]` |
| 內容速度 | 在網站上建立和發佈新內容的速度，以及新內容產生使用者參與的速度。 | `[Page Views] / [Visits]` |
| 轉換率 | 採取所需動作 (例如購買) 的訪客的百分比。 | `[Orders] / [Visits]` |
| 登入率 | 從指定頁面進入網站的訪客佔網站訪問總數的百分比。 | `[Entries] / [Visits]` |
| 預估不重複訪客(ITP 2.1) | 若為ITP訪客（Safari瀏覽器的使用者），請將不重複訪客除以2或更少。 此計算量度假設您是使用使用者端JavaScript （而非使用CNAME實作）設定Cookie。 從ITP 2.1開始，使用使用者端JavaScript設定Cookie的實作會受到影響。如需詳細資訊，請參閱[智慧型追蹤預防](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Experience Cloud ID 涵蓋範圍 | 擁有 Experience Cloud ID 的訪客的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 退出率 | 檢視特定頁面後離開網站的訪客的百分比。 | `[Exits] / [Visits]` |
| ITP 2.1不重複訪客/不重複訪客 | 使用受ITP 2.1 Cookie限制影響的瀏覽器之不重複訪客的百分比。 | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| 訂購協助 | 管道或來源促成客戶的購買歷程但未促成最終購買的次數。 | `[Orders (Visit Participation)] - [Orders]` |
| 訂購/造訪 | 造訪網站並完成交易的百分比。 | `[Orders] / [Visits]` |
| 訂購/訪客 | 每個網站訪客所產生的平均訂單數或交易數 | `[Orders] / [Unique Visitors]` |
| 頁面檢視/預估的不重複訪客 (ITP 2.1) | 預估的不重複訪客 (ITP 2.1) 的平均頁面檢視次數。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| 頁面檢視/不重複訪客 | 網站每個不重複訪客的平均檢視頁數。 | `[Page Views] / [Unique Visitors]` |
| 頁面檢視/造訪 | 使用者在單次造訪網站期間檢視的平均頁面數量。 | `[Page Views] / [Visits]` |
| 頁面速度 | 一段內容產生的其他頁面檢視次數。 此量度可協助您判斷哪些內容可促進更多參與。 | `[Page Views] / [Visits]` |
| 重新載入/頁面檢視 | 導致頁面重新載入或重新整理的頁面檢視的百分比。 | `[Reloads] / [Page Views]` |
| 收入/訂單 | 網站上每筆完成的交易或訂單所產生的平均收入金額。 | `[Revenue] / [Orders]` |
| 收入/造訪 | 單次造訪網站所產生的平均收入金額。 | `[Revenue] / [Visits]` |
| 收入/訪客 | 每個網站訪客所產生的平均收入金額。 | `[Revenue] / [Unique Visitors]` |
| 狀態檢視 | 應用程式不同狀態或畫面的檢視次數 | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| 逗留時間/使用者（狀態） | 訪客平均在網站上逗留於特定州的時間長度 | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 不重複訪客/7天後回訪的不重複訪客 | 在 7 天或更長時間後回訪的不重複訪客的百分比。 | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| 使用者（行動） | 行動應用程式的使用者總數 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 造訪/訪客 | 不重複訪客造訪網站的平均次數。 | `[Visits] / [Unique Visitors]` |
| 加權反彈率 | 函數 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
