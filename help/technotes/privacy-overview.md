---
description: 概觀 Adobe Analytics 收集哪些資料以及其他隱私權考量事項。
keywords: 隱私權
title: 隱私權概觀
feature: Data Governance
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 98%

---

# 隱私權概觀

Adobe 希望幫助您的組織讓您能遵守適用的法律和法規。如需詳細資訊，請參閱[Adobe Experience Cloud隱私權](https://www.adobe.com/tw/privacy/experience-cloud.html){target=_blank}。 在 Adob&#x200B;&#x200B;e Analytics 和您的組織之間，Adobe 的角色是「資料處理方」，而您是「資料管控方」(在適用隱私權和資料保護法律下為同等責任方)。貴組織實施 Adobe 解決方案的方式完全由貴組織控制，因此是否揭露使用 Adobe 產品和服務的方式取決於貴組織。在使用 Adob&#x200B;&#x200B;e Analytics 時，您的組織有責任遵守您自己的隱私權原則、您與 Adob&#x200B;&#x200B;e 的服務協議以及所有適用的法律。

Adobe 強烈建議遵守以下總體概念進行：

* **如果您收集個人資料，請確保遵守隱私權法律和法規。** 自訂變數可讓您收集任何您可以存取的內容；但是，您還必須考慮自己組織的隱私權原則和適用的法律。
* **為客戶提供易搜尋且易了解的組織隱私權資訊。** 有用資訊包括選擇退出連結、他們瀏覽資料的使用方式，以及您如何使用或計劃使用 Adob&#x200B;&#x200B;e 的服務。
* **請注意適用於您的當地法律和國際法律。** 如果您的組織營運範圍遍及全球，則有些國際法適用。

## 資料收集劃分

Adobe 提供多個資料收集庫，可協助將資料傳送至 Adob&#x200B;&#x200B;e。顯著的範例包括：

* **AppMeasurement**：旨在將資料直接傳送到 Adob&#x200B;&#x200B;e Analytics 的資料庫。
* **Web SDK**：旨在將資料傳送至 Adobe Experience Platform Edge Network 的資料庫，後者再將資料轉送至 Adobe Analytics。
* **標記**：以 Web 為主的 UI，可讓您設定實施方法，而無需存取初始標記實施以外的網站或應用程式原始程式碼。AppMeasurement 和 Web SDK 均提供擴充功能。

Adobe Analytics 可以收集以下類型的資料：

| 資料類型 | 詳細資料 | 包含此資料的範例變數 |
| --- | --- | --- |
| 您網站上網頁的頁面名稱或 URL | Adobe Analytics 需要此資料才能發揮功能。每次點擊都需要使用 URL 或頁面名稱。 | [頁面](../components/dimensions/page.md)、[頁面 URL](../components/dimensions/page-url.md) |
| 時間類資料 | Adobe Analytics 需要此資料才能發揮功能。資料收集需要使用時間戳，且時間類資料是從時間戳得來。 | [在頁面上花費的時間](../components/dimensions/time-spent-on-page.md)、 [一天時數](../components/dimensions/hour-of-day.md)、 [上午/下午](../components/dimensions/am-pm.md)、 [平日/週末](../components/dimensions/weekday-weekend.md)、 [星期幾](../components/dimensions/day-of-week.md)、 [一年中的月份](../components/dimensions/month-of-year.md) |
| 反向連結資料 | 當訪客登陸您的網站時，資料收集庫預設會收集反向連結 URL。您可以自訂實施方法以收集反向連結查詢字串中的資料。這種做法在行銷活動和跟蹤廣告效益中很常見。 | [反向連結](../components/dimensions/referrer.md)、 [反向連結網域](../components/dimensions/referring-domain.md) |
| 匿名處理的訪客 ID | 資料收集庫會為造訪您網站的每個瀏覽器產生並引用訪客 ID。該 ID 儲存在 cookie 中。如果資料收集庫無法設定 cookie 識別碼，則該資料庫將使用匿名訪客識別的後備方法。此方法會使用訪客的 IP 位址和使用者代理字串，嘗試將相關點擊聯擊至相同的造訪。如果您的組織啟用了 IP 模糊化功能，則此設定會啟用。請參閱「[Adobe Analytics 和瀏覽器 Cookie](cookies/cookies.md)」，了解更多資訊。 | [不重複訪客](../components/metrics/unique-visitors.md) |
| 可識別的訪客 ID | Adobe 不會自動收集自訂訪客 ID。但是，您可以自訂實施方法來收集此資料。 | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| 外部搜尋詞 | 外部搜尋資料包括來自搜尋引擎的關鍵字。資料收集庫會根據反向連結 URL 來尋找此資料。然而，許多新型搜尋引擎不再包含此資訊。 | [搜尋關鍵字](../components/dimensions/search-keyword.md) |
| 內部搜尋詞 | 內部搜尋資料包括來自您網站或應用程式搜尋功能的關鍵字。Adobe 不會自動收集內部搜尋資料。但是，您可以自訂實施方法來收集此資料。對於使用 Adob&#x200B;&#x200B;e Analytics 的組織來說，這種做法很常見。 | [eVar](../components/dimensions/evar.md) |
| 電腦和瀏覽器規格 | 資料收集庫會自動收集低平均資訊量的瀏覽器提示，例如瀏覽器類型、作業系統類型，以及裝置是桌上型電腦或行動裝置。需要自訂設定來收集高平均資訊量提示，例如瀏覽器的特定版本、裝置型號或作業系統版本。查閱「[用戶提示概觀](client-hints.md)」以了解更多。 | [瀏覽器](../components/dimensions/browser.md)、[作業系統](../components/dimensions/operating-systems.md)、[行動維度](../components/dimensions/mobile-dimensions.md)、[顯示器解析度](../components/dimensions/monitor-resolution.md) |
| 地理位置資訊 | Adobe 提供功能可將 IP 位址最後一個八位元組設為 0，以防止識別出詳細地理位置。這樣會讓地理資訊變成不那麼精確，並可在[報表套裝設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/general-acct-settings-admin.html?lang=zh-Hant)中進行設定。 | [城市](../components/dimensions/cities.md)、[區域](../components/dimensions/regions.md)、[國家/地區](../components/dimensions/countries.md) |
| IP 位址 | Adobe 提供功能可在儲存此資料時混淆 (雜湊) 或完全移除訪客的 IP 位址。歐洲、中東和非洲 (EMEA) 客戶依預設通常會混淆 IP 位址設定。無論混淆設定如何，IP 位址都不可在 Analysis Workspace 中作為維度；只會包含在[資料摘要](../export/analytics-data-feed/data-feed-overview.md)中。請參閱管理員指南中的「[一般帳戶設定](../admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)」，了解有關適用混淆設定的詳細資訊。 | 無 |
| 您網站上提供的表單資訊 | 所有實施類型都需要收集此資料的設定。您可以將此資料包含在自訂變數中。 | [eVar](../components/dimensions/evar.md) |
| 您網站上的已點擊廣告或連結 | 如果 [`trackExternalLinks`](../implement/vars/config-vars/trackexternallinks.md) 或 [`trackDownloadLinks`](../implement/vars/config-vars/trackdownloadlinks.md) 已啟用則已收集。啟用 Activity Map 時，系統將提供更多資訊，例如點擊位置。 | [Activity Map](../analyze/activity-map/overview.md)、[退出連結](../components/dimensions/exit-link.md)、[下載連結](../components/dimensions/download-link.md) |
| 在您網站上購買的產品 | 所有實施類型都需要收集此資料的設定。Adobe 提供多個預設變數來收集此資訊。 | [產品](../components/dimensions/product.md)、[訂單](../components/metrics/orders.md)、[收入](../components/metrics/revenue.md) |

{style="table-layout:auto"}

請參閱下面的導覽選單「[維度概觀](../components/dimensions/overview.md)」和「[量度概觀](../components/metrics/overview.md)」下的導覽功能表，了解 Adob&#x200B;&#x200B;e 可能收集的更多變數。

## 資料處理地點

Adobe 為 Adob&#x200B;&#x200B;e Analytics 設有三個資料處理地點。這些站點會接收原始資料並將其處理至報表套裝，在套裝中會針對資料儲存和報告檢索進行最佳化。這些資料處理地點目前位於美國 (俄勒岡州)、英國 (倫敦) 和新加坡。如需詳細資訊，請參閱[Adobe Analytics安全性總覽](https://www.adobe.com/tw/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank}。
