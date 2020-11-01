---
title: 不重複訪客
description: 獨特訪客ID的數目。
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 96%

---


# 不重複訪客

「不重複訪客」量度會顯示維度項目的訪客 ID 數量。這是確認流量時最常用的量度之一，因為它可讓您概略了解維度項目的使用頻率。例如，某位訪客可能在一個月內每天造訪您的網站，但這仍會計為單一不重複訪客。

如果您使用 [跨裝置分析](../cda/overview.md)，此量度會取代為 [獨特裝置](unique-devices.md) 。

## 每日、每週、每月、每季和每年的不重複訪客

Reports &amp; Analytics 提供每日、每週、每月、每季和每年不重複訪客的選項。不重複訪客不會計算整個時段的單一不重複訪客，而會根據選取的量度計算數量。例如，假設您想要查看網站上的每日不重複訪客。如果訪客在早上和晚上各造訪您的網站一次，則會計為單一每日不重複訪客。如果訪客分別在星期一和星期二造訪您的網站，則會計為兩個每日不重複訪客。

Analysis Workspace 會根據報表的詳細程度來處理不重複訪客。例如，如果您使用[日](../dimensions/day.md)維度，則會看到每個維度項目的每日不重複訪客。但在計算報表總計時，則會針對自由表格的日期範圍刪除不重複訪客的重複項目。

## 此量度的計算方式

此量度會計算指定維度項目的不重複訪客 ID 數量。它會使用多種進階機制來識別不重複訪客，因為有數種方法可加以識別。下表列出識別訪客的方式及其優先順序。有些點擊可能有多種訪客識別方法；在這種情況下，將會使用優先順序較高的方法。

| 使用順序 | 查詢參數 (收集方法) | 使用時機 |
| --- | --- | --- |
| 1 | `vid` | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 變數已設定。 |
| 2 | `aid` | 訪客有現有的 [`s_vi`](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-analytics.html) Cookie。在不實作訪客 ID 服務的情況下或實作該服務之前，設定於實作上。 |
| 3 | `mid` | 訪客有現有的 [`s_ecid`](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-analytics.html) Cookie。使用 [Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.html) 設定於實作上。 |
| 4 | `fid` | 訪客有現有的 [`s_fid`](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-analytics.html) Cookie，或因任何原因而無法設定 `aid` 和 `mid`。 |
| 5 | IP 位址、使用者代理、閘道 IP 位址 | 訪客的瀏覽器不接受 Cookie 時，用來識別不重複訪客的最後方法。 |

>[!NOTE]
>
>每個 Analytics 訪客 ID 都會繫結至 Adobe 伺服器上的設定檔。無論訪客 ID Cookie 過期與否，這些訪客設定檔只要閒置至少 13 個月，就會遭到刪除。

## 影響不重複訪客計數的行為

不重複訪客識別碼通常會儲存在瀏覽器 Cookie 中。他們若執行了下列任一作業，則會計為新的不重複訪客：

* 在任何時間清除了其快取
* 在同一部電腦上開啟不同的瀏覽器。每個瀏覽器各會計算一個不重複訪客。
* 同一人在不同裝置上瀏覽您的網站。每個裝置各會計算一個不重複訪客。您可以使用[跨裝置分析](../cda/overview.md)，透過[人物](people.md)量度將訪客結合在一起。
* 開啟私人瀏覽工作階段 (例如 Chrome 的 Incognito 索引標籤)。

只要保留 Cookie 識別碼，就&#x200B;*不會*&#x200B;計算新的不重複訪客：

* 長時間關閉其瀏覽器
* 將其瀏覽器升級至最新版本
