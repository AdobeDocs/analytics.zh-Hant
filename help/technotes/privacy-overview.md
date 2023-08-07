---
description: 概述 Adobe Analytics 收集哪些資料以及其他隱私權考量事項。
keywords: 隱私權
title: 隱私權概觀
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: ee0bf5beeac3c9780eb0c8420845114f7e840aec
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 12%

---

# 隱私權概觀

訪客可至 [Adobe 隱私權中心](https://www.adobe.com/tw/privacy.html)進一步瞭解 Adobe 一般如何使用收集到的資訊。貴組織實施作業 Adobe 服務的方式完全由貴組織控制，因此是否揭露使用 Adobe 產品和服務的方式取決於貴組織。貴組織有責任遵守您自己的隱私權原則、您與Adobe之間的服務合約以及所有適用法律。

Adobe強烈建議遵循下列重要概念：

* **避免在Adobe Analytics中收集個人識別資訊。** 自訂變數可讓您收集幾乎任何您可以存取的內容；不過，您也必須考慮組織的隱私權政策和適用法律。
* **為訪客提供容易找到且容易瞭解的選擇退出資訊。** 允許他們選擇退出任何非絕對必要的專案。 歐盟大部分國家不認為分析 Cookie 是絕對必要的。

## 資料收集劃分

Adobe Analytics會自動收集或可能收集下列型別的資料：

| 資料類型 | 詳細資料 | 包含此資料的範例變數 |
| --- | --- | --- |
| 您的網站上網頁的頁面名稱或URL | 一律收集。 每次點選都必須有URL或頁面名稱。 | [頁面](../components/dimensions/page.md)， [頁面URL](../components/dimensions/page-url.md) |
| 時間型資料 | 一律收集。 資料收集需要時間戳記，而以時間為基礎的資料衍生自時間戳記。 | [頁面逗留時間](../components/dimensions/time-spent-on-page.md)， [小時](../components/dimensions/hour-of-day.md)， [上午/下午](../components/dimensions/am-pm.md)， [平日/週末](../components/dimensions/weekday-weekend.md)， [星期](../components/dimensions/day-of-week.md)， [月份](../components/dimensions/month-of-year.md) |
| 來自其他網站網頁的資料 | Adobe無法收集您無法變更網站原始程式碼的非關聯網站上的資料。 當訪客進入您的網站時，AppMeasurement會自動收集反向連結URL。 您可以自訂實作，以便在查詢字串到達您的網站後收集該字串中的資料。 | [反向連結](../components/dimensions/referrer.md)， [反向連結網域](../components/dimensions/referring-domain.md) |
| 匿名訪客ID | AppMeasurement會自動產生並參照每個造訪您網站的瀏覽器的訪客ID。 此ID會儲存在Cookie中。 如果指定的實作無法使用Cookie，Adobe Analytics會使用IP位址和使用者代理字串作為訪客識別的備援方法。 另請參閱 [Adobe Analytics與瀏覽器Cookie](cookies/cookies.md) 以取得詳細資訊。 | [不重複訪客](../components/metrics/unique-visitors.md) |
| 可識別的訪客ID | Adobe不會自動收集自訂訪客ID。不過，您可以自訂實施以收集此資料。 | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| 外部搜尋詞 | AppMeasurement會嘗試根據反向連結URL自動收集此資料。 不過，許多現代搜尋引擎不再包含這項資訊。 | [搜尋關鍵字](../components/dimensions/search-keyword.md) |
| 內部搜尋詞 | Adobe不會自動收集內部搜尋資料。 不過，您可以自訂實施以收集此資料，這是使用Adobe Analytics的組織的一般做法。 | [eVar](../components/dimensions/evar.md) |
| 電腦和瀏覽器規格 | AppMeasurement會自動收集低平均資訊量瀏覽器提示，例如瀏覽器型別、作業系統型別，以及裝置是否為桌上型電腦或行動裝置。 收集高平均資訊量提示需要進行設定，例如瀏覽器的特定版本/組建、裝置型號或作業系統版本。 另請參閱 [使用者端提示總覽](client-hints.md) 以取得詳細資訊。 | [瀏覽器](../components/dimensions/browser.md)， [作業系統](../components/dimensions/operating-systems.md)， [行動維度](../components/dimensions/mobile-dimensions.md)， [監視器解析度](../components/dimensions/monitor-resolution.md) |
| 地理位置資訊 | Adobe可讓您啟用或停用收集每個網站或應用程式的地理位置資料（在報表套裝層級）。 許多實施型別(包括AppMeasurement)會自動收集此資料。 | [城市](../components/dimensions/cities.md)， [地區](../components/dimensions/regions.md)， [國家/地區](../components/dimensions/countries.md) |
| IP 位址 | Adobe可在儲存此資料時，模糊顯示最後一個八位元或完全模糊訪客的IP位址。 EMEA客戶的IP位址通常依預設會完全模糊。 IP位址無法當作Adobe Analytics中的維度使用；它只會包含在原始資料([資料摘要](../export/analytics-data-feed/data-feed-overview.md))。 | 無 |
| 您的網站上提供的表單資訊 | 所有實施型別都需要設定以收集此資料。 您可以將此資料包含在自訂變數中。 | [eVar](../components/dimensions/evar.md) |
| 在您的網站上點選的廣告或連結 | 使用AppMeasurement時自動收集。 啟用「Activity Map」後，可提供其他資訊，例如點按的位置。 | [Activity Map](../analyze/activity-map/activity-map.md)， [退出連結](../components/dimensions/exit-link.md)， [下載連](../components/dimensions/download-link.md) |
| 在您的網站上購買的產品 | 所有實施型別都需要設定以收集此資料。 Adobe提供數個預設變數來儲存此資訊。 | [產品](../components/dimensions/product.md)， [訂購](../components/metrics/orders.md)， [收入](../components/metrics/revenue.md) |

{style="table-layout:auto"}

請參閱下的導覽功能表 [Dimension概觀](../components/dimensions/overview.md) 和 [量度概觀](../components/metrics/overview.md) 以取得Adobe可能在下收集資料的更多變數。
