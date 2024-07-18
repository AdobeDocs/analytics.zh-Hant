---
title: 反向連結網域
description: 訪客點進您的網站前所在的上層網域。
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 97%

---

# 反向連結網域

「反向連結網域」[維度](overview.md)會報告訪客從哪些網域點進您的網站。 此維度有助於瞭解哪些協力廠商網站為您帶來最多流量。外部網站上必須有連結，且訪客必須點按該連結，才會顯示維度項目。

>[!IMPORTANT]
>
>您必須設定報表套裝的[內部 URL 篩選器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)，才能使用此維度。若未設定內部 URL 篩選器，則可能納入內部網域，或使外部網域無法顯示。

相同的報表可顯示 Analysis Workspace 和 Data Warehouse 之間的不同結果。Analysis Workspace 會報告每個個別頁面的反向連結網域，排除與內部 URL 篩選器相符的值。Data Warehouse 只會報告造訪的第一個反向連結網域，並忽略內部 URL 篩選器。

## 將資料填入此維度中

要使用此維度，必須在 Analytics 介面中進行設定，且需要影像要求中的資料。

* 在您的實施作業中，此維度會從影像要求中的 [`r` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會使用 JavaScript 變數 `document.referrer` 在瀏覽器中收集這項資料。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在影像要求中包含 `r` 查詢字串參數。
* 在 Analytics 介面中，您必須設定報表套裝的[內部 URL 篩選器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。若未設定內部 URL 篩選器，則可能納入內部網域，或使外部網域無法顯示。

Adobe 會在造訪期間保存反向連結網域。如果訪客在單次造訪中離開並點進了不同網域的連結，新值將會更新，並持續存在於剩餘的造訪中。如果您只想查看原始值，請參閱[原始反向連結網域](original-referring-domain.md)。

## 維度項目

維度項目包含訪客點按以進入您的網站的網域。如果點擊沒有任何設定或保存的反向連結資料，則會歸類到維度項目 `"Typed/Bookmarked"` 下。此維度項目表示沒有反向連結值，例如，當訪客在位址列中手動輸入瀏覽器位址，或按一下書籤時。也會針對不符合 Analytics 的重新導向顯示 `"Typed/Bookmarked"` 維度項目。請參閱技術使用手冊中的[重新導向與別名](/help/technotes/redirects.md)。

### 維度項目包含 `googleusercontent.com`

使用者可以看到包含 `googleusercontent.com` 網域的維度項目。

* **快取頁面**：Google 的編目程式會持續對網站進行編目，並儲存網頁的複本以防網頁離線。按一下「已快取」連結，即可在大部分搜尋結果旁取得這些快取頁面。使用者按一下此連結並檢視 Google 快取的內容時，`googleusercontent.com` 即為維度項目。
* **翻譯頁面**：Google 提供強大且便利的翻譯服務。使用本服務檢視網站時，其來源為 `googleusercontent.com`。如果使用者按一下連結返回原始內容，則會顯示此維度項目。
