---
title: 反向連結
description: 訪客點進您的網站前所在的URL。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---


# 反向連結

「反向連結」維度會報告訪客點進網站時所在的URL。 此維度對於瞭解哪些特定URL對您網站的流量最有用。 外部URL上必須有連結，而訪客必須按一下連結，才能顯示維度值。

>[!IMPORTANT] 您必須設定報表套裝的「內 [部URL」篩選器](/help/admin/admin/internal-url-filter-admin.md) ，才能使用此維度。 未能設定內部URL篩選器，可能會包含內部URL或防止出現外部URL。

## 將資料填入此維度

此維度需要在Analytics介面中進行設定，並在影像要求中設定資料。

* 在您的實作中，此維度會從影像請求中的查 [`r` 詢字串擷取](/help/implement/validate/query-parameters.md) 資料。 AppMeasurement會在瀏覽器中使用JavaScript變數 `document.referrer` 收集此資料。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。 如果您在AppMeasurement以外使用資料收集方法（例如透過API），請務必在影像請求中包含 `r` 查詢字串參數。
* 在Analytics介面中，您必須設定報表套裝的內部 [URL篩選器](/help/admin/admin/internal-url-filter-admin.md)。 未能設定內部URL篩選器，可能會包含內部URL或防止出現外部URL。

## 維度值

維度值包括訪客點進您網站的URL。 如果點擊沒有任何反向連結資料，則會在維度值下分組 `"Typed/Bookmarked"`。 此維度值表示沒有反向連結值，例如訪客在位址列中手動輸入瀏覽器位址，或是按一下書籤。
