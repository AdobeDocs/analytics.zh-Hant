---
title: Adobe Analytics 中的資料處理順序
description: 瞭解在 Adobe Analytics 中處理資料的元件和服務順序。
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 90%

---

# Adobe Analytics 中的資料處理順序

Adobe 提供了許多資料出現在報告之前變更或操縱資料的方法。此頁面會顯示各種 Adobe Analytics 功能處理資料的順序。您可以使用此清單來解決資料不一致問題，或在需要調整資料時決定使用哪種功能效果最好。

![處理順序](assets/processing-order.png)

## 傳送到 Adobe 之前的資料

在將資料傳送到 Adobe 之前，通常會使用以下其中一種方法在用戶端對其進行編譯：

* **AppMeasurement**：託管在您的網站上並在每個頁面上參考的 JavaScript 檔案。資料直接傳送到 Adobe Analytics。
* **Adobe Experience Platform Web SDK**：託管在您的網站上並在每個頁面上參考的 JavaScript 檔案。資料會傳送到Adobe Experience Platform Edge Network。
* **Adobe Experience Cloud 資料彙集中的標籤**：每個頁面上參考的 JavaScript 檔案，包含在資料彙集 UI 中建立的規則。Adobe Analytics 擴充功能可讓您用更簡單的方法實作 AppMeasurement。Web SDK 擴充功能可讓您用更簡單的方法執行 Web SDK。

如果您將資料傳送至Edge Network，您可以將其設定為將資料轉送至Adobe Analytics (以及許多其他Adobe Experience Cloud解決方案)。 不管執行方法如何，最終都會將具有所需變數的影像要求傳送到 Adobe 資料彙集伺服器。

## 資料到達 Adobe Analytics 資料彙集伺服器時

資料到達 Adobe Analytics 後，以下功能會根據需要調整資料：

1. **查詢表格**：依賴 Adobe 內部查詢表格的維度 (例如[瀏覽器](/help/components/dimensions/browser.md)維度) 與其對應的值相符。
2. [**動態變數**](/help/implement/vars/page-vars/dynamic-variables.md)：如果在影像要求的任何部分中顯示動態變數，則會複製該值並將其視為向前移動的獨立值。
3. [**機器人規則**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)：套用標准或自訂機器人篩選以從報告中排除該資料。
4. [**處理規則**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)：您的組織套用於您資料的自訂規則。包括[內容資料變數](/help/implement/vars/page-vars/contextdata.md)對應到其各自的變數。
5. **VISTA 規則**：VISTA 顧問套用於您資料的靈活自訂規則。VISTA 規則可能會在處理規則之前或之後執行，依您組織的需求而定。通常大多數 VISTA 規則會在處理規則之後執行，但每個組織的設定不同。如需有關現有VISTA規則的詳細資訊，請聯絡您的Adobe客戶團隊。
6. [**行銷管道處理規則**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md)：您可以使用[處理規則](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)來準備要用於行銷管道處理規則的資料。
7. **地理位置資料**：填入依賴 IP 地址查詢的維度 (例如[國家/地區](/help/components/dimensions/countries.md)維度)。
8. [**IP 混淆**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)：如果您的組織選擇在原始資料中混淆 IP 地址，則這會在完成其他處理功能後執行。

此時，單依點擊記錄在報告套裝資料表中。在標準[延遲](latency.md)間隔之後，它可以在報告中使用。

## 在處理後變更資料

Adobe Analytics 中的資料大多是永久性的；但有些功能允許選擇資料調整或刪除：

* [**資料修復 API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)：編輯特定欄或刪除所需的資料列。
* [**資料治理**](/help/technotes/privacy/privacy-overview.md)：滿足隱私要求而永久刪除資料。
* [**分類**](/help/components/classifications/classifications-overview.md)：根據允許您以不同方式組織資料的規則或上傳的資料建立維度。基礎報告套裝資料不會變更，因此您可以自由編輯或覆寫分類資料。
* [**虛擬報告套裝**](/help/components/vrs/vrs-about.md)：建立可以變更存取逾時或允許[跨裝置分析](/help/components/cda/overview.md)的備用報告套裝檢視。
