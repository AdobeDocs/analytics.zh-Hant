---
description: Adobe提供您可使用的各種計算量度。 本頁面列出這些量度及其預期用途。
title: 預設計算量度
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: 61a0292bf2f8ff22b414c2e91da476c1da69d163
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 41%

---

# 預設計算量度

Adobe Analytics提供各種計算量度，以涵蓋最常見的使用案例。 這些計算量度預設可在Analysis Workspace中使用。

以下為Adobe提供的每個計算量度的清單，以及其預期的函式和用於計算的基礎公式：

>[!NOTE]
>
>除了本頁所述的預設計算量度外，您也可以新增其他計算量度至報表套裝。
>
>您可以：
> * 新增串流媒體的預設計算量度，如 [計算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 從現有量度建立自訂計算量度，如 [計算與進階計算（衍生）量度](/help/components/c-calcmetrics/cm-overview.md).



| 計算量度名稱 | 函數 | 公式 |
| --- | --- | --- |
| 贏取連結點按次數 | 人們點按旨在增加網站流量的連結的次數。 | `[Campaign Click-throughs]` |
| 動作 | 應用程式中採取的動作總數 | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| 應用程式使用者 | 行動應用程式的使用者總數 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 平均工作階段長度（行動） | 訪客在單一工作階段期間在網站上逗留的平均時間。 | 空白 |
| 網站平均逗留時間 | 訪客離開或離開網站前在網站上逗留的平均時間。 | `[Average Time Spent on Site (Seconds)]` |
| 反彈率 | 包含單一點擊的造訪次數與該頁面上的造訪次數之比。 此量度可協助您了解哪些維度項目具有最高的跳出率，或查看網站在一段時間內的匯總跳出率。 | `[Bounces] / [Entries]` |
| 機器人頁面檢視率 | 機器人頁面檢視次數與頁面檢視總次數的比率。 | `[Bot Page Views] / [Page Views]` |
| 內容速度 | 在網站上建立和發佈新內容的速度，以及新內容產生使用者參與的速度。 | `[Page Views] / [Visits]` |
| 轉換率 | 採取所需動作 (例如購買) 的訪客的百分比。 | `[Orders] / [Visits]` |
| 登入率 | 在給定頁面上進入網站的訪客佔網站上工作階段總數的百分比。 | `[Entries] / [Visits]` |
| 預估不重複訪客(ITP 2.1) | 若為ITP訪客（Safari瀏覽器上的使用者），則將獨特訪客除以2或更少。 此計算量度假設您是使用用戶端JavaScript（而非使用CNAME實作）設定Cookie。 從ITP 2.1開始，使用用戶端JavaScript設定Cookie的實作會受到影響。請參閱 [智慧型追蹤預防](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 以取得詳細資訊。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Experience Cloud ID 涵蓋範圍 | 擁有 Experience Cloud ID 的訪客的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 退出率 | 檢視特定頁面後離開網站的訪客的百分比。 | `[Exits] / [Visits]` |
| ITP 2.1不重複訪客/不重複訪客 | 受ITP 2.1 Cookie限制影響的使用瀏覽器的獨特訪客百分比。 | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| 訂購協助 | 管道或來源促成客戶的購買歷程但未促成最終購買的次數。 | `[Orders (Visit Participation)] - [Orders]` |
| 訂購量/瀏覽次數 | 促使完成交易的網站造訪的百分比。 | `[Orders] / [Visits]` |
| 訂購量/訪客量 | 網站每位個別訪客產生的訂單或交易平均數量 | `[Orders] / [Unique Visitors]` |
| 頁面檢視/預估的不重複訪客 (ITP 2.1) | 預估的不重複訪客 (ITP 2.1) 的平均頁面檢視次數。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| 頁面檢視/不重複訪客 | 網站的每個不重複訪客的平均頁面檢視次數。 | `[Page Views] / [Unique Visitors]` |
| 頁面檢視次數/瀏覽次數 | 使用者在單次造訪網站期間檢視的平均頁面數量。 | `[Page Views] / [Visits]` |
| 頁面速度 | 內容片段產生的其他頁面檢視次數。 此量度可協助您判斷哪些內容可促進額外參與。 | `[Page Views] / [Visits]` |
| 重新載入/頁面檢視 | 導致頁面重新載入或重新整理的頁面檢視的百分比。 | `[Reloads] / [Page Views]` |
| 收入/訂購 | 網站上每筆完成的交易或訂單所產生的平均收入金額。 | `[Revenue] / [Orders]` |
| 收入/造訪 | 單次造訪網站所產生的平均收入金額。 | `[Revenue] / [Visits]` |
| 收入/訪客 | 每個網站訪客所產生的平均收入金額。 | `[Revenue] / [Unique Visitors]` |
| 州檢視 | 應用程式的不同狀態或畫面的檢視次數 | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| 逗留時間/使用者（狀態） | 訪客在網站上逗留於特定狀態的時間長度 | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 獨特訪客/7天後回訪的獨特訪客 | 在 7 天或更長時間後回訪的不重複訪客的百分比。 | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| 使用者（行動） | 行動應用程式的使用者總數 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 瀏覽/訪客 | 不重複訪客對網站的平均造訪次數。 | `[Visits] / [Unique Visitors]` |
| 加權反彈率 | 函數 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
