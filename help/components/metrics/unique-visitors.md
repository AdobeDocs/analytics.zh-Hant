---
title: 獨特訪客
description: 唯一個人（或裝置）的數目。
translation-type: tm+mt
source-git-commit: 9704267cd3ebf480facd68f6cca44167b1d9686d
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 10%

---


# 獨特訪客

「獨特訪客」量度顯示維度值的訪客ID數。 這是決定流量時最常用的度量之一，因為它提供維度值人氣的高階概述。 例如，某位訪客可以在一個月內每天瀏覽您的網站，但仍計為單一獨特訪客。

如果您使用 [跨裝置分析](../cda/overview.md)，此度量會重新命名為「唯一裝置」。

## 每日、每週、每月、每季和每年獨特訪客

「報告與分析」提供每日、每週、每月、每季和每年獨特訪客的選項。 獨特訪客不會計算整個時段的單一獨特訪客，而是會根據選取的量度計算。 例如，您想要查看網站的每日獨特訪客。 如果訪客在早上和晚上再次瀏覽您的網站，則會計為單一每日獨特訪客。 如果訪客在星期一和星期二再次瀏覽您的網站，則會計為兩個每日獨特訪客。

分析工作區會根據報表的詳細程度來處理獨特訪客。 例如，如果您使用 [Day](../dimensions/day.md) ，則會看到每個維度值的每日獨特訪客。 不過，對於報表總計，會針對自由表格的日期範圍去重複化獨特訪客。

## 此度量的計算方式

此量度會計算指定維度值的獨特訪客ID數目。 它使用多種進階機制來識別獨特訪客，因為有數種方法可識別獨特訪客。 下表列出訪客的識別方式及其優先順序。 有些點擊可以有多種訪客識別方法； 在這些情況下，會使用較高的優先順序方法。

| 使用順序 | 查詢參數 (收集方法) | 使用時機 |
| --- | --- | --- |
| 1 | `vid` | 變數 [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 已設定。 |
| 2 | `aid` | 訪客有現有 [`s_vi`](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-analytics.html) Cookie。 在實作訪客ID服務之前或未實作時，在實作上設定。 |
| 3 | `mid` | 訪客有現有 [`s_ecid`](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-analytics.html) Cookie。 在使用 [Adobe Experience Cloud Identity服務的實施上設定](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.html)。 |
| 4 | `fid` | 訪客有現有 [`s_fid`](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-analytics.html) Cookie，或 `aid` 是 `mid` 由於任何原因無法設定。 |
| 5 | IP 位址、使用者代理、閘道 IP 位址 | 若訪客的瀏覽器不接受Cookie，則最後可識別獨特訪客。 |

>[!NOTE]
>
>每個Analytics訪客ID都會系結至Adobe伺服器上的描述檔。 無論訪客ID Cookie有效期為何，這些訪客設定檔至少在閒置13個月後會被刪除。

## 影響獨特訪客計數的行為

唯一訪客識別碼通常儲存在瀏覽器Cookie中。 如果新的獨特訪客執行下列任一項作業，則會計入該訪客：

* 隨時清除其快取
* 在同一部電腦上開啟不同的瀏覽器。 每個瀏覽器會計算一個獨特訪客。
* 在不同裝置上瀏覽您網站的同一人。 個別獨特訪客會計入每個裝置。 您可以使用 [跨裝置分析](../cda/overview.md) ，使用「人物」度量將訪客 [結合在一起](people.md) 。
* 開啟私人瀏覽作業（例如Chrome的Incognito標籤）。

只要保留Cookie識 *別碼* ，就不會計算新的獨特訪客：

* 在較長時間內關閉瀏覽器
* 將其瀏覽器升級至最新版本
