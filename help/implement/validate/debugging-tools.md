---
title: Analytics實作的偵錯工具
description: 使用Analytics偵錯工具、瀏覽器開發人員工具和HTTP偵錯代理，檢查您的實施傳送至Adobe的資料。
keywords: 封包分析器，封包監視器，封包Sniffer，偵錯工具， charles， NS_BINDING_ABORTED， sendBeacon
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
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
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 3%
---
# Analytics實作的偵錯工具

偵錯工具（有時稱為封包分析器或封包Sniffer）可讓您檢查實施傳送至Adobe的資料。 它們可協助您確認請求是否成功引發、檢查這些請求中包含的變數和裝載，以及疑難排解非預期的實作行為。

>[!NOTE]
>
>此頁面上列出的工具並不完整。 它們代表Adobe Analytics客戶認為有用的工具。 除了Adobe提供的工具，Adobe不支援這些產品或為其疑難排解。 如需安裝、使用及支援資訊，請洽詢工具的發行者。

## 選擇偵錯工具

下列類別可協助您根據所要檢查的專案選取工具。

| 工具型別 | 使用時機 |
| --- | --- |
| **分析和標籤偵錯工具** | 您想讓Analytics變數、標籤、資料層或收集要求以人類看得懂的格式解譯和呈現。 |
| **瀏覽器開發人員工具** | 您正在偵錯Web實作，且想要直接檢查網路要求，而不安裝個別的偵錯應用程式。 |
| **個HTTP(S)偵錯代理** | 您想要檢查來自瀏覽器、行動應用程式、WebViews、API或其他使用者端的HTTP流量，或需要瀏覽器開發人員工具以外的功能。 |

## Analytics和標籤偵錯工具

Analytics和標籤偵錯工具可辨識分析技術並解譯其請求。 這些工具可讓您更輕鬆地識別Adobe Analytics變數、Experience Platform Web SDK裝載、標籤和相關實作資訊，而不需要手動解碼網路請求。

| 工具 | 可用性 | 可用於 | 考量事項 |
| --- | --- | --- | --- |
| **[Adobe Experience Platform Debugger](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/debugger/home)** | 瀏覽器延伸模組 | 針對Adobe Experience Platform和CX Enterprise實作除錯，包括Adobe Analytics、標籤、資料層和Experience Platform Web SDK | Adobe提供的專注於Adobe技術的工具 |
| **[Omnibug](https://omnibug.io)** | Chromium瀏覽器和Firefox | 解碼Adobe Analytics、Experience Platform Web SDK、Adobe標籤，以及其他許多分析和行銷廠商的請求 | 適合用於包含多家廠商技術的實作 |
| **[ObservePoint偵錯工具](https://www.observepoint.com/solutions/observepoint-debugger/)** | Chrome和Edge | 檢查和解碼分析、行銷和測量標籤，包括Adobe Analytics請求 | 瀏覽器型除錯程式；ObservePoint也提供個別的自動化實作驗證產品 |
| **[Adobe Experience Platform Assurance](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/assurance/home)** | CX Enterprise中的網頁應用程式 | 檢查及驗證Mobile SDK實作中的事件，並瞭解Edge Network如何處理事件 | Adobe提供的工具；將您的應用程式連線至Assurance工作階段以檢視其事件 |

## 瀏覽器開發人員工具

每個現代化瀏覽器都包含可檢查網路請求的開發人員工具，因此您通常不需要單獨的工具來偵錯Web實施。 按下&#x200B;**F12**&#x200B;或&#x200B;**Ctrl+Shift+I** （Windows和Linux）或&#x200B;**Cmd+Option+I** (macOS)，然後選取&#x200B;**網路**&#x200B;索引標籤。 在Safari中，請先在Safari的&#x200B;**進階**&#x200B;設定中啟用開發人員功能。

## HTTP(S)偵錯代理

HTTP偵錯代理會攔截使用者端與伺服器之間的HTTP和HTTPS流量。 當瀏覽器開發人員工具提供的可見度不足，或實作在傳統網頁瀏覽器之外執行時，這些變數很有用。

HTTPS檢查通常需要將使用者端設定為信任由偵錯Proxy提供的憑證。 安裝憑證或攔截加密流量時，請遵循您組織的安全性原則。

| 工具 | 可用於 |
| --- | --- |
| **[Charles](https://www.charlesproxy.com/)** | 檢查瀏覽器、應用程式、行動裝置和其他HTTP流量 |
| **[隨處都有Fiddler](https://www.telerik.com/fiddler/fiddler-everywhere)** | 擷取及檢查跨應用程式和裝置的HTTP(S)流量。 與舊版Fiddler Classic產品不同。 |
| **[Proxyman](https://proxyman.com/)** | 檢查和修改來自瀏覽器、應用程式和行動裝置的HTTP(S)流量 |
| **[HTTP Toolkit](https://httptoolkit.com/)** | 透過以應用程式和API偵錯為導向的工作流程，檢查來自應用程式、API、開發環境和行動裝置的流量 |
| **[mitmproxy](https://www.mitmproxy.org/)** | 可透過命令列和Web介面執行指令碼式HTTP(S)攔截、檢查和修改。 最適合熟悉命令列工作流程的使用者。 |

## 找到Adobe Analytics請求

對於直接將資料傳送至Adobe Analytics （例如AppMeasurement）的實作，請篩選下列專案的網路請求：

```text
/ss/
```

Adobe Analytics收集請求在請求URL或承載中包含Analytics變數。 原始請求使用查詢引數名稱而非變數名稱；例如，eVar1顯示為`v1`，prop1顯示為`c1`。 Analytics偵錯工具會為您解碼這些名稱。 若要自行解碼，請參閱資料插入API檔案中的[變數參考](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference)。

如需Analytics資料收集伺服器傳回的HTTP狀態碼，請參閱資料插入API檔案中的[HTTP回應碼](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes)。

針對使用Adobe Experience Platform Web SDK的實作，篩選下列專案的網路請求：

```text
/ee/
```

選取請求並檢查其裝載，以檢視傳送至Adobe Experience Platform Edge Network的資料。 網頁SDK會將資料傳送至Edge Network，再由後者將資料轉送至Adobe Analytics和其他已設定的服務。 檢查使用者端要求會驗證瀏覽器傳送至Edge Network的內容；本身不會確認每個下游服務是否已成功處理資料。 若要瞭解Edge Network如何處理事件，請使用[Adobe Experience Platform Assurance](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/assurance/home)。

## 中止的請求

當頁面導覽離開時，瀏覽器可以取消仍在進行中的請求。 Firefox為這些要求加上標籤`NS_BINDING_ABORTED`；Chrome和Edge則為這些要求加上標籤`(canceled)`。 若要在導覽後讓請求保持可見，請啟用&#x200B;**保留記錄檔** （Chrome和Edge）或&#x200B;**保留記錄檔** (Firefox)。

取消的請求不一定表示資料遺失。 瀏覽器可能已傳送完整要求，並僅停止等待回應。 瀏覽器開發人員工具通常無法顯示差異，但HTTP偵錯Proxy可以。

導覽時未取消與`navigator.sendBeacon()`一併傳送的請求。 AppMeasurement使用`sendBeacon`作為退出連結，且每當[`useBeacon`](/help/implement/vars/config-vars/usebeacon.md)啟用時。 Web SDK會將其用於與[`documentUnloading`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/documentunloading)一併傳送的事件。 如果連結追蹤請求經常被取消，請使用這些選項。
