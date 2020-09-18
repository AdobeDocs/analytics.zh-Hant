---
title: 反向連結
description: 訪客點進您的網站前所在的 URL。
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 48%

---


# 反向連結

「反向連結」維度會報告訪客從哪些 URL 點進您的網站。此維度有助於瞭解哪些特定的 URL 為您的網站帶來最多流量。外部URL上必須有連結，而訪客必須按一下連結，才能顯示維度項目。

>[!IMPORTANT]
>
>您必須設定報表套裝的[內部 URL 篩選器](/help/admin/admin/internal-url-filter-admin.md)，才能使用此維度。若未設定內部 URL 篩選器，則可能納入內部 URL，或使外部 URL 無法顯示。

相同的報表可顯示分析工作區和資料倉庫之間的不同結果。 分析工作區會報告每個個別頁面的反向連結，排除符合內部URL篩選器的值。 「資料倉庫」僅報告瀏覽的第一個反向連結，並忽略內部URL篩選器。

## 將資料填入此維度中

要使用此維度，必須在 Analytics 介面中進行設定，且需要影像要求中的資料。

* 在您的實作中，此維度會從影像要求中的 [`r` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會使用 JavaScript 變數 `document.referrer` 在瀏覽器中收集這項資料。您可以使用變 [`referrer`](/help/implement/vars/page-vars/referrer.md) 數覆寫來手動設定。 如果您使用 AppMeasurement 程式庫 (例如，透過 Adobe Experience Platform Launch)，此維度將可立即運作。如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在影像要求中包含 `r` 查詢字串參數。
* 在 Analytics 介面中，您必須設定報表套裝的[內部 URL 篩選器](/help/admin/admin/internal-url-filter-admin.md)。若未設定內部 URL 篩選器，則可能納入內部 URL，或使外部 URL 無法顯示。

## 維度項目

維度項目包含訪客點進您網站的URL。 If a hit does not have any referrer data, it groups under the dimension item `"Typed/Bookmarked"`. 此維度項目表示沒有反向連結值，例如訪客在位址列中手動輸入瀏覽器位址，或是按一下書籤。 維 `"Typed/Bookmarked"` 度項目也會針對不容納Analytics的重新導向而顯示。 請參 [閱Technotes使用指南](/help/technotes/redirects.md) 中的重新導向和別名。

### 包含 `googleusercontent.com`

使用者可以看到包含網域的維度項目 `googleusercontent.com`。

* **快取頁面**:谷歌的蜘蛛程式會不斷地爬網，並儲存頁面復本，以防頁面離線。 按一下「快取」連結，即可在大部分搜尋結果旁取得這些快取頁面。 當使用者按一下此連結並檢視Google快取的內容時， `webcache.googleusercontent.com` 是一個典型的維度項目。
* **翻譯頁面**：Google 提供強大且便利的翻譯服務。使用本服務檢視網站時，其來源為 `translate.googleusercontent.com`。如果使用者按一下連結以返回原始內容，就會顯示此維度項目。
