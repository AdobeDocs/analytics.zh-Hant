---
title: 處理Adobe Analytics中的資料順序
description: 了解在Adobe Analytics中處理資料的元件和服務順序。
source-git-commit: 65ee7ae6d838f34149eb60547d976856e4da3b17
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---

# 處理Adobe Analytics中的資料順序

Adobe提供許多變更或操控資料的方式，之後才會顯示在報表中。 本頁面顯示各種Adobe Analytics功能處理資料的順序。 您可以使用此清單來疑難排解資料不一致，或決定需要進行資料調整時要使用的最佳功能。

## 資料傳送至Adobe之前

在將資料傳送至Adobe之前，通常會使用下列其中一種方法來編譯用戶端：

* **AppMeasurement**:在您的網站上托管且在每個頁面上參照的JavaScript檔案。 資料會直接傳送至Adobe Analytics。
* **Adobe Experience Platform Web SDK**:在您的網站上托管且在每個頁面上參照的JavaScript檔案。 資料會傳送至Adobe Experience Edge。
* **Adobe Experience Cloud資料收集中的標籤**:每個頁面上的JavaScript參考，包含在資料收集UI中建立的規則。 Adobe Analytics擴充功能提供更輕鬆的AppMeasurement實施方式。 Web SDK擴充功能提供更輕鬆的方式來實作Web SDK。

如果您將資料傳送至Adobe Experience Edge，可以設定它將資料轉送至Adobe Analytics(以及許多其他Adobe Experience Cloud解決方案)。 無論實施方法為何，最終都會將包含所需變數的影像要求傳送至Adobe資料收集伺服器。

## 資料到達Adobe Analytics資料收集伺服器時

資料到達Adobe Analytics後，下列功能會視需要調整資料：

1. **查閱表格**:依賴Adobe — 內部查閱表格的Dimension(例如 [瀏覽器](/help/components/dimensions/browser.md) 維度)與其對應的值相符。
2. [**動態變數**](/help/implement/vars/page-vars/dynamic-variables.md):如果在影像要求的任何部分看到動態變數，則會複製該值，並視為未來的獨立值。
3. [**機器人規則**](/help/admin/admin/bot-removal/bot-rules.md):套用標準或自訂機器人篩選，從報表中排除該資料。
4. [**處理規則**](/help/admin/admin/c-processing-rules/processing-rules.md):貴組織套用至資料的自訂規則。 包括 [內容資料變數](/help/implement/vars/page-vars/contextdata.md) 變數。
5. **VISTA規則**:由Adobe顧問套用至資料的自訂彈性規則。 VISTA規則可能會在處理規則之前或之後執行，視貴組織的需求而定。 大部分的VISTA規則通常在處理規則之後執行，但每個組織的設定都不同。 如需現有VISTA規則的詳細資訊，請連絡您的Adobe客戶經理。
6. [**行銷管道處理規則**](/help/components/c-marketing-channels/c-rules.md):您可以使用 [處理規則](/help/admin/admin/c-processing-rules/processing-rules.md) 以準備資料以用於行銷管道處理規則。
7. **地理位置資料**:依賴IP位址查閱的Dimension(例如 [國家/地區](/help/components/dimensions/countries.md) 維度)。
8. [**IP模糊化**](/help/admin/admin/general-acct-settings-admin.md):如果貴組織已選擇將原始資料中的IP位址模糊化，則會在所有其他處理功能完成後完成。

此時，個別點擊會記錄在報表套裝資料表中。 在標準之後 [延遲](latency.md) 間隔，可在報告中使用。

## 在處理資料後變更資料

Adobe Analytics的資料大多是永久性的；不過，有些功能可允許選擇性調整或移除資料：

* [**資料修復API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/):編輯特定欄或刪除所需的資料列。
* [**資料控管**](/help/admin/c-data-governance/an-gdpr-workflow.md):接受隱私權要求以永久刪除資料。
* [**分類**](/help/components/classifications/c-classifications.md):根據規則或上傳的資料建立維度，以便以不同方式組織資料。 基礎報表套裝資料不會變更，因此您可以自由編輯或覆寫分類資料。
* [**虛擬報表套裝**](/help/components/vrs/vrs-about.md):建立可變更造訪逾時或允許的替代報表套裝檢視 [跨裝置分析](/help/components/cda/overview.md).
