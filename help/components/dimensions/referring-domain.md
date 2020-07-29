---
title: 轉介網域
description: 訪客點進您的網站前所處的首要網域。
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---


# 轉介網域

「反向連結網域」維度會報告訪客點進哪些網域以進入您的網站。 此維度有助於瞭解哪些協力廠商網站對您的流量貢獻最大。 外部網站上必須有連結，而訪客必須按一下連結，才能顯示維度項目。

>[!IMPORTANT]
>
>您必須設定報表套裝的「內 [部URL」篩選器](/help/admin/admin/internal-url-filter-admin.md) ，才能使用此維度。 無法設定內部URL篩選器，可能包括內部網域或防止外部網域出現。

相同的報表可顯示分析工作區和資料倉庫之間的不同結果。 「分析工作區」會報告每個個別頁面的反向連結網域，排除與內部URL篩選器相符的值。 「資料倉庫」僅報告瀏覽的第一個反向連結網域，並忽略內部URL篩選器。

## 將資料填入此維度

此維度需要在Analytics介面中進行設定，並在影像要求中設定資料。

* 在您的實作中，此維度會從影像請求中的查 [`r` 詢字串擷取](/help/implement/validate/query-parameters.md) 資料。 AppMeasurement會在瀏覽器中使用JavaScript變數 `document.referrer` 收集此資料。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。 如果您在AppMeasurement以外使用資料收集方法（例如透過API），請務必在影像請求中包含 `r` 查詢字串參數。
* 在Analytics介面中，您必須設定報表套裝的內部 [URL篩選器](/help/admin/admin/internal-url-filter-admin.md)。 無法設定內部URL篩選器，可能包括內部網域或防止外部網域出現。

Adobe會持續存在瀏覽的反向連結網域。 如果訪客在單次瀏覽中離開並點按不同網域的連結，新值會更新並持續存在於剩餘的瀏覽中。 如果您只想查看原始值，請參閱「原始反 [向連結網域」](original-referring-domain.md)。

## 維度項目

維度項目包括訪客點進您網站的網域。 如果點擊沒有任何反向連結資料（設定或持續），則會在維度項目下分組 `"Typed/Bookmarked"`。 此維度項目表示沒有反向連結值，例如訪客在位址列中手動輸入瀏覽器位址，或是按一下書籤。

### 包含 `googleusercontent.com`

使用者可以看到包含網域的維度項目 `googleusercontent.com`。

* **快取頁面**: 谷歌的蜘蛛程式會不斷地爬網，並儲存頁面復本，以防頁面離線。 按一下「快取」連結，即可在大部分搜尋結果旁取得這些快取頁面。 當使用者按一下此連結並檢視Google快取的內容時，即 `googleusercontent.com` 為維度項目。
* **翻譯頁面**：Google 提供強大且便利的翻譯服務。使用本服務檢視網站時，其來源為 `googleusercontent.com`。如果使用者按一下連結以返回原始內容，就會顯示此維度項目。
