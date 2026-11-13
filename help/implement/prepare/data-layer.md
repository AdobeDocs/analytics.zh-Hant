---
title: 建立資料層
description: 瞭解資料層如何支援您的Analytics實施、Adobe為何建議Adobe使用者端資料層，以及如何使用每種實施方法讀取資料層值。
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 7%
---
# 建立資料層

資料層是網站上的JavaScript結構，會公開Analytics實作收集的資料，例如頁面名稱、產品詳細資料和訂單ID。 您的網站程式碼會寫入資料層，而實作會從中讀取資料，以設定Analytics變數。 由於您的實施不依賴頁面的HTML，因此您可以重新設計網站而不會中斷資料收集。

## 先決條件

[建立解決方案設計檔案](solution-design.md)：貴組織必須符合追蹤需求。 請確保在接洽組織內的開發團隊之前，已備妥解決方案設計文件。 解決方案設計所需的資料會決定資料層包含的內容。

## 選擇資料層規格 {#specifications}

Adobe建議針對新的或重組的實作使用[Adobe使用者端資料層](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/overview) (ACDL)。 ACDL是開放原始碼的JavaScript程式庫，可讓您的網站以標準方式推送資料和事件至全域`adobeDataLayer`陣列。 標籤、網頁SDK和AppMeasurement都可以讀取，而Adobe Experience Manager核心元件可以自動填入標籤。

您的組織可以自由使用其他規格，例如[客戶體驗數位資料層](https://www.w3.org/2013/12/ceddl-201312.pdf) (CEDDL) （將資料儲存在全域`digitalData`物件中）或自訂規格。 最重要的是貴組織必須符合其需求的規格。

下表比較ACDL與物件資料層（例如CEDDL）：

| | Adobe使用者端資料層(`adobeDataLayer`) | 物件資料層，例如CEDDL (`digitalData`) |
| --- | --- | --- |
| 網站程式碼如何寫入資料 | 推播物件： `adobeDataLayer.push({ page: { name: "Home" } })` | 設定屬性： `digitalData.page.pageInfo.pageName = "Home"` |
| 您的實施如何讀取值 | 來自Adobe使用者端資料層標籤延伸的`adobeDataLayer.getState("page.name")`或&#x200B;**資料層計算狀態**&#x200B;資料元素 | `digitalData.page.pageInfo.pageName`或核心標籤擴充功能中的&#x200B;**JavaScript變數**&#x200B;資料元素 |
| 您的實作如何知道資料已準備就緒 | 網站程式碼會推送事件（例如`{ event: "page view" }`），而您的實作會監聽該事件。 也會針對新增之前推送的事件執行監聽器。 | 您的實作必須在網站程式碼填入物件後（例如使用直接呼叫規則）讀取物件。 |

## 範例資料層 {#example}

ACDL不需要特定的資料結構。 設計解決方案設計檔案周圍的結構，並為寫入或讀取資料層的每個人製作檔案。 本指南中的範例使用下列結構。

頁面載入時，網站程式碼會推送頁面資料和頁面檢視事件：

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push({
  event: "page view",
  page: {
    name: "Home",
    section: "Products",
    url: "https://example.com/products",
    referrer: "https://example.com/"
  }
});
```

訪客完成購買時，網站程式碼會推送訂單詳細資料和購買事件：

```js
window.adobeDataLayer.push({
  event: "purchase",
  transaction: { id: "ABC123" },
  products: [
    { name: "Example product", category: "Example category", quantity: 1, price: 25 }
  ]
});
```

ACDL會將每次推播合併為稱為計算狀態的單一物件，您的實施會讀取該物件。 事件物件會告知您的實施何時讀取它。 檢視[資料及計算狀態](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/computed-state)和[事件](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/events)。

## 工作流程 {#workflow}

使用資料層實施 Adobe Analytics 時，通常會依照下列步驟操作：

1. **與您的網站開發團隊合作實作資料層**：您的網站開發團隊主要負責確保資料層包含正確的值。 請與您的網站開發團隊一起檢閱此頁面，確保團隊之間的期望相同。 請參閱[安裝Adobe使用者端資料層](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/install)。
1. **使用瀏覽器主控台驗證您的資料層**：開啟瀏覽器的開發人員主控台，大部分的瀏覽器都可以使用`F12`鍵來執行此作業。 執行`adobeDataLayer.getState()`以檢視計算狀態，或執行`adobeDataLayer.getState("page.name")`以檢視單一值。 請參閱[驗證安裝](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/install#verify)。
1. **將資料層連線至Adobe Analytics**：此步驟因您組織的實作方法而異。 請參閱[將資料層連線至Adobe Analytics](#connect)。

## 將資料層連結至Adobe Analytics {#connect}

下表顯示每種實作方法從Adobe Client Data Layer讀取的方式：

| 實作方法 | 如何讀取資料層 | 更多資訊 |
| --- | --- | --- |
| Web SDK 標記擴充功能 | 使用Adobe使用者端資料層擴充功能中的&#x200B;**資料層推播**&#x200B;事件觸發規則。 將資料層值對應至XDM欄位或透過Web SDK **更新變數**&#x200B;動作對應至`data`物件，然後透過&#x200B;**傳送事件**&#x200B;動作傳送。 | [使用網頁SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/web-sdk)、[XDM物件欄位對應](../aep-edge/xdm-var-mapping.md)和[資料物件欄位對應](../aep-edge/data-var-mapping.md)傳送Adobe使用者端資料層資料 |
| Web SDK JavaScript資料庫 | 接聽具有`addEventListener()`的資料層事件，並在您呼叫`sendEvent`時從資料層設定XDM或`data`欄位。 | [使用網頁SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/web-sdk)、[XDM物件欄位對應](../aep-edge/xdm-var-mapping.md)和[資料物件欄位對應](../aep-edge/data-var-mapping.md)傳送Adobe使用者端資料層資料 |
| Analytics 擴充功能 | 使用&#x200B;**資料層推播**&#x200B;事件觸發規則，並從Adobe使用者端資料層延伸建立&#x200B;**資料層計算狀態**&#x200B;資料元素。 在&#x200B;**設定變數**&#x200B;動作中將資料元素指派給Analytics變數，然後使用&#x200B;**傳送信標**&#x200B;動作傳送資料。 | [將資料層物件對應至資料元素](../launch/layer-to-elements.md)和[將資料元素對應至Analytics變數](../launch/elements-to-variable.md) |
| AppMeasurement | 在ACDL載入後以`getState()`讀取值，然後呼叫`s.t()`。 | [使用AppMeasurement讀取資料層](#appmeasurement) |

### 使用AppMeasurement讀取資料層 {#appmeasurement}

ACDL在程式庫載入時將其`getState()`方法新增至`adobeDataLayer`陣列。 若要確定程式庫已載入且計算狀態包含最新資料，請讀取事件接聽程式中的值：

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function(dl) {
  dl.addEventListener("page view", function(event) {
    s.pageName = dl.getState("page.name");
    s.channel = dl.getState("page.section");
    s.t();
  });
});
```

接聽程式針對每個`page view`事件執行一次，包括新增接聽程式之前推播的事件。 本指南中的變數頁面（例如[`pageName`](../vars/page-vars/pagename.md)）會顯示如何使用`getState()`讀取個別值。 在監聽器（如本監聽器）中，或在&#x200B;**資料層推播**&#x200B;事件觸發的Analytics擴充功能規則的自訂程式碼編輯器中，使用這些範例。

如果您的實作每頁傳送多個點選，例如在單頁應用程式中，請使用[`clearVars()`](../vars/functions/clearvars.md)，這樣來自一個點選的值就不會持續到下一個點選。

## 後續步驟

* [將資料層物件對應至資料元素](../launch/layer-to-elements.md)：在Adobe Experience Platform標籤中使用您網站的資料層。
* [Adobe Client Data Layer檔案](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/overview)：瞭解每個ACDL方法、事件和最佳實務。
