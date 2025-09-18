---
title: 不重複訪客
description: 不重複訪客識別碼的數目。
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: e242276f931e9939081b948a9d9ef8a087e16461
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 95%

---

# 不重複訪客

「不重複訪客」[量度](overview.md)會顯示該維度項目的訪客 ID 數目。這是確認流量時最常用的量度之一，因為它可讓您概略了解維度項目的使用頻率。例如，某位訪客可能在一個月內每天造訪您的網站，但這仍會計為單一不重複訪客。

如果您使用「[跨裝置分析](../cda/overview.md)」，此量度會被「[不重複裝置](unique-devices.md)」量度取代。

## 每日、每週、每月、每季和每年不重複訪客

Analysis Workspace 會根據報告的詳細程度處理不重複訪客。例如，如果您使用[日](../dimensions/day.md)維度，則會看到每個維度項目的每日不重複訪客。但在計算報表總計時，則會針對自由表格的日期範圍刪除不重複訪客的重複項目。

## 此量度的計算方式

此量度會計算指定維度項目的不重複訪客 ID 數量。它會使用多種進階機制來識別不重複訪客，因為有數種方法可加以識別。下表列出識別訪客的方式及其優先順序。有些點擊可能有多種訪客識別方法；在這種情況下，將會使用優先順序較高的方法。

| 使用順序 | 查詢參數 (收集方法) | 使用時機 |
| --- | --- | --- |
| 1 | `vid` | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 變數已設定。 |
| 2 | `aid` | 訪客有現有的 [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hant) Cookie。在不實作訪客 ID 服務的情況下或實作該服務之前，設定於實作上。 |
| 3 | `mid` | 訪客有現有的 [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hant) Cookie。在使用[Adobe Experience Cloud Identity服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)的實施上設定。 Adobe建議儘可能將ID服務用於所有實作。 |
| 4 | `fid` | 訪客有現有的 [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hant) Cookie，或因任何原因而無法設定 `aid` 和 `mid`。 |
| 5 | IP 位址、使用者代理、閘道 IP 位址 | 訪客的瀏覽器不接受 Cookie 時，用來識別不重複訪客的最後方法。 |

>[!NOTE]
>
>每個 Analytics 訪客 ID 都會繫結至 Adobe 伺服器上的設定檔。無論訪客 ID Cookie 過期與否，這些訪客輪廓只要閒置至少 13 個月，就會遭到刪除。

## 影響不重複訪客計數的行為

不重複訪客識別碼通常會儲存在瀏覽器 Cookie 中。他們若執行了下列任一作業，則會計為新的不重複訪客：

* 在任何時間清除了其快取
* 在同一部電腦上開啟不同的瀏覽器。每個瀏覽器各會計算一個不重複訪客。
* 同一人在不同裝置上瀏覽您的網站。每個裝置各會計算一個不重複訪客。您可以使用[跨裝置分析](../cda/overview.md)，透過[人物](people.md)量度將訪客結合在一起。
* 開啟私人瀏覽工作階段 (例如 Chrome 的 Incognito 索引標籤)。

只要保留 Cookie 識別碼，就&#x200B;*不會*&#x200B;計算新的不重複訪客：

* 長時間關閉其瀏覽器
* 將其瀏覽器升級至最新版本
