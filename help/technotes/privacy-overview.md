---
description: 概述 Adobe Analytics 收集哪些資料以及其他隱私權考量事項。
keywords: 隱私權
title: 隱私權概觀
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 9fd055fd747c7124d49e280af1b0acc24d79be8e
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 3%

---

# 隱私權概觀

Adobe想要啟用您的組織，以便您遵守適用的法律和法規。 另請參閱 [Adobe Experience Cloud隱私權](https://www.adobe.com/tw/privacy/experience-cloud.html){target=_blank} 以取得詳細資訊。 在Adobe Analytics與您的組織之間，Adobe會充當「資料處理者」，而您則是「資料控制者」（或根據適用的隱私權與資料保護法律屬同）。 貴組織實作Adobe解決方案的方式完全由貴組織控制，因此是否揭露使用Adobe產品和服務的方式取決於貴組織。 使用Adobe Analytics時，您的組織有責任遵守您自己的隱私權原則、您與Adobe的服務合約以及所有適用法律。

Adobe強烈建議遵循下列重要概念：

* **如果您收集個人資料，請務必遵守隱私權法規。** 自訂變數可讓您收集幾乎任何您可以存取的內容；不過，您也必須考慮組織的隱私權政策和適用法律。
* **為貴組織提供易於找到且易於理解的隱私資訊，供客戶使用。** 實用資訊包括選擇退出連結、如何使用其瀏覽資料，以及您如何使用或計畫使用Adobe服務。
* **請注意您適用的當地法律和國際法律。** 如果貴組織以全球規模運作，則可能適用某些國際法。

## 資料收集劃分

Adobe提供多個資料收集程式庫，協助將資料傳送至Adobe。 值得注意的範例包括：

* **AppMeasurement**：程式庫，專為直接將資料傳送至Adobe Analytics而設計。
* **Web SDK**：此程式庫的設計用途是傳送資料至Adobe Experience Platform Edge網路，再由網路將資料轉送至Adobe Analytics。
* **標籤**：網頁式UI可讓您設定實作，而不需要存取網站或應用程式的原始程式碼，而不需要初始標籤實作。 擴充功能適用於AppMeasurement和Web SDK。

Adobe Analytics可收集下列型別的資料：

| 資料類型 | 詳細資料 | 包含此資料的範例變數 |
| --- | --- | --- |
| 您的網站上網頁的頁面名稱或URL | Adobe Analytics需要此資料才能運作。 每次點選都必須有URL或頁面名稱。 | [頁面](../components/dimensions/page.md)， [頁面URL](../components/dimensions/page-url.md) |
| 時間型資料 | Adobe Analytics需要此資料才能運作。 資料收集需要時間戳記，而以時間為基礎的資料衍生自時間戳記。 | [頁面逗留時間](../components/dimensions/time-spent-on-page.md)， [小時](../components/dimensions/hour-of-day.md)， [上午/下午](../components/dimensions/am-pm.md)， [平日/週末](../components/dimensions/weekday-weekend.md)， [星期](../components/dimensions/day-of-week.md)， [月份](../components/dimensions/month-of-year.md) |
| 反向連結資料 | 當訪客進入您的網站時，資料收集程式庫會依預設收集反向連結URL。 您可以自訂實作，以收集反向連結查詢字串中的資料。 此做法在行銷活動和追蹤廣告績效中很常見。 | [反向連結](../components/dimensions/referrer.md)， [反向連結網域](../components/dimensions/referring-domain.md) |
| 匿名訪客ID | 資料收集程式庫會針對造訪您網站的每個瀏覽器，產生並參考訪客ID。 此ID會儲存在Cookie中。 如果資料收集程式庫無法設定Cookie識別碼，程式庫會使用匿名訪客識別的備援方法。 此方法涉及使用訪客的IP位址和使用者代理字串將相關點選繫結至相同造訪。 如果您的組織已啟用IP模糊化，則會接受此設定。 另請參閱 [Adobe Analytics與瀏覽器Cookie](cookies/cookies.md) 以取得詳細資訊。 | [不重複訪客](../components/metrics/unique-visitors.md) |
| 可識別的訪客ID | Adobe不會自動收集自訂訪客ID。 不過，您可以自訂實施以收集此資料。 | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| 外部搜尋詞 | 外部搜尋資料包含源自搜尋引擎的關鍵字。 資料收集程式庫會根據反向連結URL尋找此資料。 不過，許多現代搜尋引擎不再包含這項資訊。 | [搜尋關鍵字](../components/dimensions/search-keyword.md) |
| 內部搜尋詞 | 內部搜尋資料包含源自您網站或應用程式搜尋功能的關鍵字。 Adobe不會自動收集內部搜尋資料。 不過，您可以自訂實施以收集此資料。 對於使用Adobe Analytics的組織來說，這個作法是很常見的。 | [eVar](../components/dimensions/evar.md) |
| 電腦和瀏覽器規格 | 資料收集程式庫會自動收集低平均資訊量瀏覽器提示，例如瀏覽器型別、作業系統型別，以及裝置是否為桌上型電腦或行動裝置。 需要自訂設定才能收集高平均資訊量提示，例如瀏覽器的特定版本/組建、裝置型號或作業系統版本。 另請參閱 [使用者端提示總覽](client-hints.md) 以取得詳細資訊。 | [瀏覽器](../components/dimensions/browser.md)， [作業系統](../components/dimensions/operating-systems.md)， [行動維度](../components/dimensions/mobile-dimensions.md)， [監視器解析度](../components/dimensions/monitor-resolution.md) |
| 地理位置資訊 | Adobe可讓您啟用或停用收集每個網站或應用程式的地理位置資料（在報表套裝層級）。 地理位置資料收集預設為啟用。 | [城市](../components/dimensions/cities.md)， [地區](../components/dimensions/regions.md)， [國家/地區](../components/dimensions/countries.md) |
| IP 位址 | Adobe提供在儲存此資料時，模糊化最後一個八位元或完全模糊化訪客IP位址的功能。 EMEA客戶的IP位址設定預設會完全模糊化。 無論模糊化設定為何，IP位址都不能當作Adobe Analytics中的維度，只會包含在 [資料摘要](../export/analytics-data-feed/data-feed-overview.md). | 無 |
| 您的網站上提供的表單資訊 | 所有實施型別都需要設定以收集此資料。 您可以將此資料包含在自訂變數中。 | [eVar](../components/dimensions/evar.md) |
| 已點按您網站上的廣告或連結 | 如果使用資料收集程式庫，則預設為收集。 啟用Activity Map時，還有其他資訊，例如點按的位置。 | [Activity Map](../analyze/activity-map/activity-map.md)， [退出連結](../components/dimensions/exit-link.md)， [下載連](../components/dimensions/download-link.md) |
| 在您的網站上購買的產品 | 所有實施型別都需要設定以收集此資料。 Adobe提供數個預設變數來收集此資訊。 | [產品](../components/dimensions/product.md)， [訂購](../components/metrics/orders.md)， [收入](../components/metrics/revenue.md) |

{style="table-layout:auto"}

請參閱下的導覽功能表 [Dimension概觀](../components/dimensions/overview.md) 和 [量度概觀](../components/metrics/overview.md) 以取得Adobe可能在下收集資料的更多變數。

## 資料處理位置

Adobe會為Adobe Analytics維護三個資料處理位置。 這些網站會接收原始資料，並將其處理為報表套裝，以最佳化資料儲存和報表擷取。 這些資料處理位置位於美國（奧勒岡州）、英國（倫敦）和新加坡。 另請參閱 [Adobe Analytics安全性總覽](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank} 以取得詳細資訊。
