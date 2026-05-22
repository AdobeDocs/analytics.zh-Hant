---
title: 反向連結
description: 訪客點進您的網站前所在的 URL。
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
TQID: https://experienceleague.adobe.com/VE1bJD2ah1N9t-fHKc5GC0-pC4YmXEDkCwhVmI5rHZQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 96%

---

# 反向連結

「反向連結」[維度](overview.md)會報告訪客點進您的網站時所在的URL。 此維度有助於瞭解哪些特定的 URL 為您的網站帶來最多流量。 外部 URL 上必須有連結，且訪客必須點按該連結，才會顯示維度項目。

>[!IMPORTANT]
>
>您必須設定報表套裝的[內部 URL 篩選器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)，才能使用此維度。 若未設定內部 URL 篩選器，則可能納入內部 URL，或使外部 URL 無法顯示。

相同的報表可顯示 Analysis Workspace 和 Data Warehouse 之間的不同結果。 Analysis Workspace 會報告每個頁面的反向連結，排除符合內部 URL 篩選器的值。 Data Warehouse 僅報告造訪的第一個反向連結，並忽略內部 URL 篩選器。

## 將資料填入此維度中

要使用此維度，必須在 Analytics 介面中進行設定，且需要影像要求中的資料。

* 在您的實施作業中，此維度會從影像要求中的 [`r` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。 AppMeasurement 會使用 JavaScript 變數 `document.referrer` 在瀏覽器中收集這項資料。 您可使用 [`referrer`](/help/implement/vars/page-vars/referrer.md) 變數覆寫以手動設定。 如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在影像要求中包含 `r` 查詢字串參數。
* 在 Analytics 介面中，您必須設定報表套裝的[內部 URL 篩選器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)。 若未設定內部 URL 篩選器，則可能納入內部 URL，或使外部 URL 無法顯示。

## 維度項目

維度項目包含訪客點按以進入您網站的 URL。 如果點擊沒有任何反向連結資料，則會歸類到維度項目 `"Typed/Bookmarked"` 下。 此維度項目表示沒有反向連結值，例如，當訪客在位址列中手動輸入瀏覽器位址，或按一下書籤時。 也會針對不符合 Analytics 的重新導向顯示 `"Typed/Bookmarked"` 維度項目。 請參閱技術使用手冊中的[重新導向與別名](/help/technotes/redirects.md)。

### 維度項目包含 `googleusercontent.com`

使用者可以看到包含 `googleusercontent.com` 網域的維度項目。

* **快取頁面**：Google 的編目程式會持續對網站進行編目，並儲存網頁的複本以防網頁離線。 按一下「已快取」連結，即可在大部分搜尋結果旁取得這些快取頁面。 使用者按一下此連結並檢視 Google 快取的內容時，`webcache.googleusercontent.com` 就是典型的維度項目。
* **翻譯頁面**：Google 提供強大且便利的翻譯服務。 使用本服務檢視網站時，其來源為 `translate.googleusercontent.com`。 如果使用者按一下連結返回原始內容，則會顯示此維度項目。
