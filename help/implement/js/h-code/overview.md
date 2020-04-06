---
title: H 程式碼 JavaScript 實施概述
description: 瞭解在網站上實施 H 程式碼的工作流程。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# H 程式碼 JavaScript 實施概述

>[!IMPORTANT] 不再支援此版本的資料彙集。請升級為 [Adobe Experience Platform Launch](../../launch/overview.md) 或 [JavaScript 適用的 AppMeasurement](../overview.md)。

您必須擁有托管伺服器的存取權限，才能成功實施包含資料收集程式碼的頁面。下列步驟將帶領您進行基本的 Analytics H 程式碼實施。

>[!NOTE] 若要遵循這些指示，您必須擁有一份 `s_code.js` 的現有副本。Adobe 不再提供在「代碼管理器」中下載 H 程式碼的選項。

1. **更新核心 JS 檔案變數**：編輯 `s_code.js` 檔案並確認下列變數已更新:
   * `s_account` 包含您要傳送資料的目的地報表套裝 ID。如需此工具的其他相關資訊，請參閱
   * `s.trackingServer` 包含 Cookie 的儲存位置。請參閱 [trackingServer](../../vars/config-vars/trackingserver.md)。
2. **在您的網站上托管`s_code.js`檔案**：此檔案通常與 Web 伺服器上的其他指令碼共存。
3. **在所有頁面上參考`s_code.js`**：確認所有個別頁面都會呼叫核心 JavaScript 檔案，並在 HTML `<body>` 標記 (非 `<head>` 標記) 中執行。
   > [!TIP] H 程式碼要求在 `s_code.js` 標記中呼叫 `<body>` 指令碼。這與其他實施方法不同，大部分的方法都要求將指令碼參考放置於 `<head>` 標記中。
4. **在每個頁面上定義頁面專用變數**：每個頁面都應定義各自的變數，如頁面名稱或 eVar。個別變數通常會在每個頁面上的內嵌 `<script>` 標記中定義。
5. **使用除錯工具來驗證資料彙集**：下載並安裝 [Experience Cloud 除錯工具](../../validate/debugger.md)，確保將資料傳送至 Adobe，而且頁面變數的定義正確無誤。

## 快取

JavaScript檔案在初次載入後會在訪客的瀏覽器中快取，而且每個作業通常不會下載超過一次。 檔案不會下載至每個頁面，即使網站上的每個頁面都使用它。 在大多數網站上，使用者每個作業的頁面檢視次數平均超過幾次，因此將多次使用的JavaScript傳輸至此檔案可減少整體下載資料的量。

## H 程式碼壓縮

如果您擔心 `s_code.js` 檔案的下載大小，Adobe 建議使用 GZIP 壓縮 `s_code.js` 檔案。GZIP 受到所有主要瀏覽器支援，而且效能比 JavaScript 壓縮更好。請參閱 Apache 文件中的 [Apache 模組 mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html)。
