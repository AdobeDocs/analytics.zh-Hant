---
title: Adobe Analytics 中的資料處理順序
description: 瞭解在 Adobe Analytics 中處理資料的元件和服務順序。
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: 6c947812d4fd8bc2ee951a5933c6e3b6d8ca1a6b
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 35%

---

# Adobe Analytics 中的資料處理順序

Adobe 提供了許多資料出現在報告之前變更或操縱資料的方法。此頁面會顯示各種 Adobe Analytics 功能處理資料的順序。您可以使用此清單來解決資料不一致問題，或在需要調整資料時決定使用哪種功能效果最好。

![正在處理訂單影像](assets/processing-order.png)

## 傳送到 Adobe 之前的資料

在將資料傳送到 Adobe 之前，通常會使用以下其中一種方法在用戶端對其進行編譯：

* **AppMeasurement**：託管在您的網站上並在每個頁面上參考的 JavaScript 檔案。資料直接傳送到 Adobe Analytics。
* **Adobe Experience Platform Web SDK**：託管在您的網站上並在每個頁面上參考的 JavaScript 檔案。資料會傳送到Adobe Experience Platform Edge Network。
* **Adobe Experience Platform資料彙集中的標籤**：每個頁面上參考的JavaScript檔案，包含在資料彙集UI中建立的規則。 Adobe Analytics 擴充功能可讓您用更簡單的方法實作 AppMeasurement。Web SDK 擴充功能可讓您用更簡單的方法執行 Web SDK。
* **API**： AppMeasurement和Edge Network都提供程式化方法，可將資料傳送至Adobe。 AppMeasurement提供[資料插入API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/)和[大量資料插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)；Edge Network提供[資料收集API](https://developer.adobe.com/data-collection-apis/docs/)。

如果您將資料傳送至Edge Network，您可以將其設定為將資料轉送至Adobe Analytics （以及許多其他Adobe Experience Cloud解決方案）。 無論實作方法為何，收集的點選資料最終都會以可剖析的格式送達Adobe Analytics處理伺服器。

## Adobe Analytics集合中的前置處理

資料到達Adobe Analytics時，會進入預先處理階段：

1. [**動態變數**](/help/implement/vars/page-vars/dynamic-variables.md)：如果在影像要求的任何部分中顯示動態變數，則會複製該值並將其視為向前移動的獨立值。
1. [**IP模糊化（最後一個八位元）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)：如果您的報表套裝設定為只模糊化最後一個八位元，則會套用這個模糊化。 請注意，IP模糊化（移除IP）稍後會在處理管道中發生。
1. **查閱表格**：依賴Adobe內部查閱表格的維度（例如[瀏覽器](/help/components/dimensions/browser.md)維度）與其對應的值相符。
1. [**IP排除**](/help/admin/tools/exclude-ip.md)：在此步驟中，會標籤您明確從報表排除的任何IP位址。
1. [**機器人規則**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)：套用標准或自訂機器人篩選以從報告中排除該資料。
1. **地理位置資料**：填入依賴 IP 地址查詢的維度 (例如[國家/地區](/help/components/dimensions/countries.md)維度)。
1. [**處理規則**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)：您的組織套用於您資料的自訂規則。包括[內容資料變數](/help/implement/vars/page-vars/contextdata.md)對應到它們各自的Analytics變數。
1. [**VISTA 規則**](vista.md)：VISTA 顧問套用於您資料的靈活自訂規則。VISTA 規則可能會在處理規則之前或之後執行，依您組織的需求而定。通常大多數 VISTA 規則會在處理規則之後執行，但每個組織的設定不同。如需有關現有VISTA規則的詳細資訊，請聯絡您的Adobe客戶團隊。
1. **貨幣轉換**：如果點選包含與報表套裝貨幣不同的[`currencyCode`](/help/implement/vars/config-vars/currencycode.md)，則任何適用的貨幣變數都會使用當天的匯率來轉換。
1. [**郵遞區號**](/help/components/dimensions/zip-code.md)：「郵遞區號」維度會根據報表套裝設定填入。

## 資料收集管道的「中值」階段

前置處理完成時，數項功能會使用這種經過部分處理的資料形式，稱為「中間值」。 將該資料傳送至任何地方之前，會套用某些中間值特定處理：

1. [**點選層級行銷頻道處理規則**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)：這些處理規則是專門針對Analytics Source Connector執行的。 由於還沒有造訪或訪客層級內容，這些處理規則會假設點選不是造訪的首次點選。 執行點選的處理規則的結果可在`channel.typeAtSource`和`channel._id`中使用。
1. [**IP模糊化（移除IP）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)：如果您的報表套裝設定為完全模糊化IP位址，則此處適用模糊化（僅適用於mid-values）。

此時，會將中值資料傳送至其個別功能：

* [**Livestream API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/)：將應用程式連線到Adobe的Livestream服務，以便收集資料流。
* [**Analytics Source Connector**](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/adobe-applications/analytics)：將Adobe Analytics報表套裝資料擷取至Adobe Experience Platform資料集。
* [**即時報告**](/help/components/c-real-time-reporting/realtime.md)：在Analysis Workspace中最多提供三個可設定的即時報告。

## 造訪和訪客層級處理

到目前為止，指定的點選沒有任何在其前後收集之點選的知識或內容。 此處理階段會填入造訪和訪客層級欄位。

1. [**造訪+訪客定義**](/help/implement/id/overview.md)：會根據其包含的訪客變數識別點選。
1. [**造訪次數**](/help/components/dimensions/visit-number.md)：根據已識別訪客的其他造訪，計算造訪次數。
1. **事件重複資料刪除**：如果點選包含重複的[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)或[事件序列化](/help/implement/vars/page-vars/events/event-serialization.md)，則會檢查這些ID並加以分別標幟。
1. [**造訪層級行銷管道處理規則**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)：每次點選都會透過行銷管道處理規則執行，而其管道+管道詳細資料則會判斷該點選是否符合任何規則。 這些規則會填入Analysis Workspace中可用的[行銷管道](/help/components/dimensions/marketing-channel.md)和[行銷管道詳細資料](/help/components/dimensions/marketing-detail.md)維度。
1. **變數持續性**：對於具有持續性的維度（例如[eVars](/help/components/dimensions/evar.md)），此值在此步驟中確定。 一般而言，大部分`post`值都設定在這裡。
1. **交易ID**：如果點選包含新的[`transactionID`](/help/implement/vars/page-vars/transactionid.md)值，則會儲存所有支援值的「快照」。 當資料來源上載包含相符的交易ID時，此快照中支援的所有值都會包含在該資料來源列中。
1. [**IP模糊化（移除IP）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)：如果您的報表套裝設定為完全模糊化IP位址，則所有其他處理完成後會套用該模糊化。

此時，單依點擊記錄在報告套裝資料表中。在標準[延遲](latency.md)間隔之後，它可以在報告中使用。

## 在處理後變更資料

Adobe Analytics 中的資料大多是永久性的；但有些功能允許選擇資料調整或刪除：

* [**資料修復 API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)：編輯特定欄或刪除所需的資料列。
* [**資料治理**](/help/technotes/privacy/privacy-overview.md)：滿足隱私要求而永久刪除資料。
* [**分類**](/help/components/classifications/classifications-overview.md)：根據允許您以不同方式組織資料的規則或上傳的資料建立維度。基礎報告套裝資料不會變更，因此您可以自由編輯或覆寫分類資料。
* [**虛擬報表套裝**](/help/components/vrs/vrs-about.md)：建立可以變更造訪逾時的備用報表套裝檢視。
