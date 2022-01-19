---
description: 資料來源類別可識別具有類似功能的不同資料來源類型。
subtopic: Data sources
title: 資料類型和類別的概觀
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 91%

---

# 資料類型和類別的概觀

資料來源類別可識別具有類似功能的不同資料來源類型。

類別是以使用者的觀點將資料來源分門別類。通過建立資料源時 [!DNL Data Sources] UI，首先選擇資料源類別，然後選擇特定資料源類型。 每個類別包含的資料來源類型，皆支援相似類型的資料。[!DNL Data Sources] 提供了以下資料源類別：

## 網站使用 {#web-usage}

| 資料來源 | 處理類型 | 說明 |
| --- | --- | --- |
| [!UICONTROL 網站伺服器記錄檔] | [網站記錄檔](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | 多數網站伺服器都會產生可記錄所提供每一個頁面的記錄檔。使用此資料來源，您可以處理來自多數網站伺服器資料的記錄檔，並將此資料加入到您的報表中。 |
| [!UICONTROL Advertising Cloud 大量上傳] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 提供手動和Excel自動批量上載 [!DNL Advertising Cloud]。 |
| [!UICONTROL 網站等級流量資料來源] | [流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | 匯入您整個網站的流量資料。比如說， [!UICONTROL 頁面視圖]。 |
| [!UICONTROL 劃分流量資料來源] | [流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | 匯入由其他網站變數劃分的流量資料。比如說， [!UICONTROL 頁面視圖] 分 [!UICONTROL 產品]。 |

## 廣告活動 {#ad-campaigns}

| 資料來源 | 處理類型 | 說明 |
| --- | --- | --- |
| [!UICONTROL 通用廣告伺服器] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您將廣告伺服器上有關廣告服務活動的印象及其他首要量度整合到行銷報表中。此資料來源是通用廣告伺服器資料來源，如果您的特定廣告伺服器不受支援，則應使用此資料來源。 |
| [!UICONTROL 通用電子郵件促銷活動伺服器] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您將量度從電子郵件促銷活動伺服器整合到行銷報表。常見的整合量度包括已傳送、已送達及已閱讀郵件的數量。此資料來源是通用電子郵件促銷活動資料來源，如果您的特定電子郵件促銷活動伺服器不受支援，則應使用此資料來源。 |
| [!UICONTROL 每次點按付費普通服務] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您匯入每次點按付費的效能資料，包括印象、點按及成本。此資料來源是通用的每次點按資料來源，如果您的特定每次點按服務不受支援，則應使用此資料來源。 |

## 客戶關係管理 (CRM) {#crm}

| 資料來源 | 處理類型 | 說明 |
| --- | --- | --- |
| [!UICONTROL 通用話務中心] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您將您話務中心的相關資訊整合到行銷報表。較常匯入的量度包括通話次數、通話時間、代理商及銷售總額。此資料來源是通用的話務中心資料來源，如果您的特定話務中心軟體不受支援，則應使用此資料來源。 |
| [!UICONTROL 通用客戶支援應用程式] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您將您客戶支援軟體中的資訊整合到行銷報表。它包括一些量度，如新事件的數量、已解決事件的數量與解決事件所花費的時間。此資料來源是通用的客戶支援資料來源，如果您的特定客戶服務程式不受支援，則可使用此資料來源。 |

## 客戶滿意度 {#csat}

| 資料來源 | 處理類型 | 說明 |
| --- | --- | --- |
| [!UICONTROL 通用調查資料] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您將協力廠商工具的調查結果整合到行銷報告中，並透過客戶與您的網站之間的互動情況，顯示客戶的整體滿意程度。此資料來源是通用調查資料來源，如果您的特定調查資料服務不受支援，則應可使用此資料來源。 |

## 網站績效 {#performance}

| 資料來源 | 處理類型 | 說明 |
| --- | --- | --- |
| [!UICONTROL 通用網站下載速度] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您將來自追蹤下載速度之應用程式或服務程式的資料整合到 資料當中。此資料來源是通用下載速度資料來源，如果您的特定下載速度軟體或服務程式不受支援，則應使用此資料來源。 |

## 通用 {#generic}

| 資料來源 | 處理類型 | 說明 |
| --- | --- | --- |
| [!UICONTROL 通用資料來源 (僅摘要資料)] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 當沒有更接近您要匯入行銷報表和分析的資料類型時，使用此資料來源。 |
| [!UICONTROL 通用資料來源 (完全處理)] | 完全處理 | Adobe2022年1月31日不建議使用完全處理資料源。 [了解更多](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md). Adobe建議您使用 [批量資料插入API(BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) 的雙曲餘切值。 |
| [!UICONTROL 通用資料來源 (交易 ID)] | <ul><li>交易 ID</li><li>訪客 ID</li></ul> | 可讓您連接任何離線事件至線上事件。的 [!UICONTROL 事務ID] 在離線事件和聯機事件之間起關鍵作用。 |

## 線上購買 {#purchases}

| 資料來源 | 處理類型 | 說明 |
| --- | --- | --- |
| [!UICONTROL 產品退貨] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您匯入產品退貨資料並使之與購買 ID 關聯，因此您可找出搜尋引擎、關鍵字、促銷活動及其他較可能發生退貨的屬性。 |
| [!UICONTROL 產品成本] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您關聯個別產品的成本或利潤，提供網站上產品購買和運送的實際成本，因此您可以正確報告網站上獲利最多的促銷活動、關鍵字及內部促銷活動。 |
| [!UICONTROL 訂單狀態] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您使用量度識別每張訂單的狀態，包括已取消的訂單、已送貨的訂單、完成的訂單或被認為是欺騙的訂單。訂單狀態報表能識別何種贏取方式可產生最高的訂單完成率。 |

## 銷售機會和報價 {#leads}

| 資料來源 | 處理類型 | 說明 |
| --- | --- | --- |
| [!UICONTROL 銷售機會開發] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您上傳您網站上產生的每一個銷售機會的相關結果資訊，包括產生的實際收入。將收入準確地歸入銷售機會 ID 後，您便可識別出最有利的營銷和促銷活動。 |
| [!UICONTROL 線上報價] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您上傳您網站上產生的每一個銷售機會的相關結果資訊，包括產生的實際收入。將收入準確地歸入銷售機會 ID 後，您便可識別出最有利的營銷和促銷活動。 |
| [!UICONTROL 話務中心資料] | [轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 可讓您上傳話務中心交易，因此您可識別吸引客戶撥電話的策略為何 (促銷活動、行銷等)。 |
