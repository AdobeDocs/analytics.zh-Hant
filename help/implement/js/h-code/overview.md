---
title: H 程式碼 JavaScript 實施概觀
description: 瞭解在網站上實施 H 程式碼的工作流程。
feature: Implementation Basics
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
role: Developer
TQID: 'https://experienceleague.adobe.com/-d3QyBm0RW5arsRHNHY4ov7YJxVFZrNdvXhVIuU6Ih4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 81%

---

# H 程式碼 JavaScript 實施概觀

>[!IMPORTANT]
>
>不再支援此版本的資料彙集。 請升級為 [Adobe Experience Platform 中的標記](../../launch/overview.md)或 [JavaScript 適用的 AppMeasurement](../overview.md)。

您必須擁有托管伺服器的存取權限，才能成功實施包含資料收集程式碼的頁面。 下列步驟將帶領您進行基本的 Analytics H 程式碼實施。

>[!NOTE]
>
>若要遵循這些指示，您必須擁有一份 `s_code.js` 的現有副本。 Adobe 不再提供在「代碼管理器」中下載 H 程式碼的選項。

1. **更新核心 JS 檔案變數**：編輯 `s_code.js` 檔案並確認下列變數已更新：
   * `s_account` 包含您要傳送資料的目的地報表套裝 ID。
   * `s.trackingServerSecure` 包含 Cookie 的儲存位置。
1. **在您的網站上托管 `s_code.js` 檔案**：此檔案通常與 Web 伺服器上的其他指令碼共存。
1. **在所有頁面上參考 `s_code.js`**：確認所有個別頁面都會呼叫核心 JavaScript 檔案，並在 HTML `<body>` 標記 (非 `<head>` 標記) 中執行。

   >[!TIP]
   >
   >H 程式碼要求在 `s_code.js` 標記中呼叫 `<body>` 指令碼。 這與其他實施方法不同，大部分的方法都要求將指令碼參考放置於 `<head>` 標記中。
1. **在每個頁面上定義頁面專用變數**：每個頁面都應定義各自的變數，如頁面名稱或 eVar。 個別變數通常會在每個頁面上的內嵌 `<script>` 標記中定義。
1. **使用偵錯工具來驗證資料彙集**：下載並安裝[CX Enterprise Debugger](../../validate/debugger.md)，以確定資料已傳送至Adobe，且頁面變數的定義正確。

## 快取

JavaScript檔案初次載入後，系統會在訪客的瀏覽器中快取，且通常不會為每個工作階段下載超過一次。 不會在每個頁面上下載檔案，即使網站上的每個頁面都使用它。 大部分網站上的使用者每個工作階段會進行多次頁面瀏覽，所以將多次使用的 JavaScript 傳輸至此檔案可以減少整體下載資料量。

## H 程式碼壓縮

如果您擔心 `s_code.js` 檔案的下載大小，Adobe 建議使用 GZIP 壓縮 `s_code.js` 檔案。 GZIP 受到所有主要瀏覽器支援，而且效能比 JavaScript 壓縮更好。 請參閱 Apache 文件中的 [Apache 模組 mod_deflate](https://httpd.apache.org/docs/current/mod/mod_deflate.html)。
