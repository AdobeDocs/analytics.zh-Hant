---
title: 偵錯Analytics資料收集
description: 確認Adobe Analytics會從AppMeasurement、Analytics擴充功能、Web SDK、Mobile SDK和資料插入API收到您需要的資料。
keywords: 偵錯，驗證，封包分析器，封包監視器， /b/ss/， Edge Trace， Assurance， hitdebugger，報表套裝
feature: Implementation Basics
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 049b9b7447c7f91d67eb58fc781898b685bd9d91
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 2%
---
# 偵錯Analytics資料收集

本文說明當您對傳送至Adobe Analytics的資料進行偵錯時，應檢查哪些專案。 請在下表中尋找您的實作方法，並前往其區段。 如果您正在調查非預期的報表資料，請從[比較請求與報表](#reports)開始。

如需適用於所有Adobe資料收集的步驟和工具，例如擷取網路要求、啟用偵錯記錄以及調查已取消的要求，請參閱[偵錯和疑難排解資料收集](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/overview)。

| 實作方法 | 若要檢視Analytics收到的資料，請前往 | 指南 |
| --- | --- | --- |
| AppMeasurement或Analytics標籤擴充功能 | 從瀏覽器直接向Analytics資料收集伺服器提出的請求 | [AppMeasurement](#appmeasurement) |
| Web SDK | Edge追蹤，在Edge Network將您的事件轉換為Analytics點選之後 | [Web SDK](#web-sdk) |
| Mobile SDK | Assurance中的Analytics事件檢視。 如果您使用Edge Network或Edge Bridge擴充功能，請開啟&#x200B;**[!UICONTROL Analytics Edge檢視]**。 | 在Assurance中檢視[Adobe Analytics事件](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/adobe-analytics) |
| 資料插入 API | 您伺服器的傳出要求及其回應 | [疑難排解資料插入API要求](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting) |

## AppMeasurement與Analytics擴充功能 {#appmeasurement}

### 尋找請求 {#appmeasurement-find}

[擷取網路要求](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#web)並篩選`/b/ss/`。 標籤偵錯工具（例如Adobe Experience Platform Debugger）會為您識別和解碼這些請求。

如果未出現`/b/ss/`請求：

* 檢查瀏覽器主控台是否有JavaScript錯誤。
* 如果您使用Analytics標籤擴充功能，請確認標籤內嵌程式碼位於頁面的`<head>`元素中，且您的程式庫已發佈至您正在測試的環境。 [標籤偵錯模式](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/logging)顯示傳送點選的規則是否觸發。
* 如果您自行託管AppMeasurement，請直接開啟程式庫的URL，確認檔案已載入且包含程式碼。
* 停用瀏覽器擴充功能（例如廣告封鎖程式），因為這些擴充功能會防止傳送請求。
* Debugger無法辨識從iframe內傳送的請求。 請改用瀏覽器開發人員工具。 請參閱[搭配iFrames使用AppMeasurement](../use-cases/iframe.md)。

### 檢查Analytics收到的內容 {#appmeasurement-contents}

* **報表套裝**： `/b/ss/`之後的路徑區段會列出接收點選的報表套裝ID。 確認它們是您期望的報表套裝，例如開發頁面上的開發報表套裝。
* **變數**：原始要求使用查詢引數名稱，而非變數名稱；例如，eVar1會顯示為`v1`，而prop1會顯示為`c1`。 檢視[變數參考](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference)。 當要求太長時，AppMeasurement會以HTTP `POST`傳送要求，因此要求內文中會顯示變數，而非URL。
* **點選型別**： [`tl()`](../vars/functions/tl-method.md)傳送的要求包含`pe`引數，且不會增加頁面檢視。 由[`t()`](../vars/functions/t-method.md)傳送的請求不包含`pe`。

如果值存在但錯誤，請參閱[疑難排解JavaScript實作](../js/troubleshooting.md)的常見原因，例如引號、大寫和空白。

### 檢查回應 {#appmeasurement-response}

`2xx`回應只會確認資料收集伺服器已收到要求，而不會確認點選已記錄。 使用預設的回應型別時，即使點選遭捨棄，請求也可以傳回成功。 新訪客的第一個要求應該會有`302`回應。 請參閱[HTTP回應代碼](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes)。

AppMeasurement會傳送退出連結要求，以及啟用[`useBeacon`](../vars/config-vars/usebeacon.md)時所有要求，並附帶`navigator.sendBeacon()`。 開發人員工具可標籤這些請求為已取消，即使瀏覽器已傳送這些請求亦然。 請參閱[中止的要求](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#aborted-requests)。

## Web SDK {#web-sdk}

### 尋找請求 {#web-sdk-find}

使用Web SDK時，瀏覽器會將事件傳送至Edge Network，而非直接傳送至Analytics，因此您不會看到`/b/ss/`請求。 [檢查Edge Network要求](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#edge-network-requests)並確認下列專案：

* `configId`引數符合已啟用[Adobe Analytics服務](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure#analytics)的資料流，並具有您期望的報表套裝。
* 裝載符合頁面檢視或連結事件的資格。 Analytics會忽略不含頁面詳細資料或網頁互動型別的裝載。 檢視Adobe Analytics[&#128279;](../aep-edge/hit-types.md)中的Edge Network事件型別。

### 檢查Analytics收到的內容 {#web-sdk-contents}

啟動[Edge追蹤](https://experienceleague.adobe.com/en/docs/experience-platform/debugger/edge-trace)並重現動作。 找出以&#x200B;**[!UICONTROL Analytics自動對應]**&#x200B;開頭的列，然後展開`mappedQueryParams`及其下方的報表套裝ID。

* **變數**：對應值使用與AppMeasurement要求相同的查詢引數名稱，有時以簡寫形式，例如`gn`代表頁面名稱，`pl`代表產品。 檢視[XDM物件欄位對應](../aep-edge/xdm-var-mapping.md)和[資料物件欄位對應](../aep-edge/data-var-mapping.md)。
* **內容資料**：未對應至Analytics變數的XDM欄位會顯示為前置詞為`c.a.x.`的內容資料。 使用[處理規則](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)將其指派給變數。
* **報表套裝**：如果您使用報表套裝覆寫，Edge追蹤中的資料流設定列會顯示Edge Network使用的報表套裝。

### 檢查處理 {#web-sdk-processing}

在Edge追蹤開啟的Assurance工作階段中，搜尋`hitdebugger`的事件。 這些事件使用廠商`com.adobe.analytics.hitdebugger`，而且其裝載會在Analytics處理後顯示值，例如Experience Cloud ID (`mcvisId`)和`pageName`。

如需引導式逐步解說，請參閱[使用Adobe Experience Platform Web SDK設定Adobe Analytics](https://experienceleague.adobe.com/zh-hant/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics)。

## 比較請求與報表 {#reports}

到達Analytics的點選不會立即出現在報表中，而且報告的值可能會與請求中的值不同：

* **延遲**：收集後大約兩小時，報表中通常會顯示完整的資料。 部分資料（例如時間戳記點選）可能需要更長的時間。 檢視[資料可用性和延遲](/help/technotes/latency.md)。
* **處理中**：處理規則、VISTA規則、機器人規則和其他處理步驟可以在收集後變更或排除值。 檢視Adobe Analytics[&#128279;](/help/technotes/processing-order.md)中資料的處理順序 Assurance後續處理的資料會顯示個別點選的處理結果。
* **報表套裝**：確認您正在檢視的報表套裝是請求或資料流鎖定的相同報表套裝。
* **非預期的值**：如果維度顯示非預期的尖峰或值，請參閱[雜湊衝突](hash-collisions.md)。

如需更廣泛的流量變更，請參閱[疑難排解資料中的尖峰與下降](/help/technotes/event/spikes-drops.md)。
