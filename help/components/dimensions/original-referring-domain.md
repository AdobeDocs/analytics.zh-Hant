---
title: 原始反向連結網域
description: 訪客點進您的網站前所在的第一個反向連結網域。
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 95%

---

# 原始反向連結網域

「原始反向連結網域」[維度](overview.md)會報告訪客點進您網站的第一個反向連結網域。 設定後，該訪客 ID 的整個存留期都會包含相同的值。此維度有助於了解哪些協力廠商網站原本會將流量帶往您的網站。

>[!IMPORTANT]
>
>您必須設定報表套裝的[內部 URL 篩選器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)，才能使用此維度。若未設定內部 URL 篩選器，則可能納入內部網域，或使外部網域無法顯示。

## 將資料填入此維度中

此維度需要在 Analytics 介面和您的實施作業中進行設定。

* 在您的實施作業中，此維度會從影像要求中的 [`r` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會使用 JavaScript 變數 `document.referrer` 在瀏覽器中收集這項資料。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在影像要求中包含 `r` 查詢字串參數。
* 在 Analytics 介面中，您必須設定報表套裝的[內部 URL 篩選器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。若未設定內部 URL 篩選器，則可能納入內部網域，或使外部網域無法顯示。

Adobe 會在訪客的存留期保留原始反向連結網域。如果訪客在任何時候離開並點按不同網域上的連結，則不會記錄新的值。如果想查看新值，請參閱[反向連結網域](referring-domain.md)。

## 維度項目

維度項目包含訪客點按以進入您的網站的網域。如果點擊沒有任何設定或保存的反向連結資料，則會歸類到維度項目 `"None"` 下。此維度項目表示沒有反向連結值，例如，當訪客在位址列中手動輸入瀏覽器位址，或按一下書籤時。

## 比較反向連結網域與原始反向連結網域

反向連結網域可以在造訪之間變更。例如，某個訪客經由 `google.com` 到達您的網站，然後在一週後經由 `twitter.com` 到達您的網站。他們最終在您的網站上購買產品。如果使用反向連結網域作為具有上次接觸歸因的維度，則 `twitter.com` 會獲得購買的評分。如果使用原始反向連結網域作為維度，那麼無論歸因模型為何，`google.com` 都會獲得購買的評分。

指定訪客 ID 的整個存留期內原始反向連結網域都不會變更。
