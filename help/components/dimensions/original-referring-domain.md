---
title: 原始反向連結網域
description: 訪客在點進您的網站之前所在的第一個反向連結網域。
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---


# 原始反向連結網域

「原始反向連結網域」維度會報告訪客點進來存取您網站的第一個反向連結網域。 設定後，該訪客ID的整個存留期都會包含相同的值。 此維度有助於瞭解哪些協力廠商網站原本會驅動您網站的流量。

## 將資料填入此維度

此維度需要在Analytics介面和您的實作中進行設定。

* 在您的實作中，此維度會從影像請求中的查 [`r` 詢字串擷取](/help/implement/validate/query-parameters.md) 資料。 AppMeasurement會在瀏覽器中使用JavaScript變數 `document.referrer` 收集此資料。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。 如果您在AppMeasurement以外使用資料收集方法（例如透過API），請務必在影像請求中包含 `r` 查詢字串參數。
* 在Analytics介面中，您必須設定報表套裝的內部 [URL篩選器](/help/admin/admin/internal-url-filter-admin.md)。 無法設定內部URL篩選器，可能包括內部網域或防止外部網域出現。

Adobe會在訪客的存留期間保留原始反向連結網域。 如果訪客隨時離開並點按不同網域上的連結，則不會記錄新值。 如果想查看新值，請參閱反 [向連結網域](referring-domain.md)。

## 維度值

維度值包括訪客點進您網站的網域。 如果點擊沒有任何反向連結資料（設定或持續），則會在維度值下分組 `"None"`。 此維度值表示沒有反向連結值，例如訪客在位址列中手動輸入瀏覽器位址，或是按一下書籤。
