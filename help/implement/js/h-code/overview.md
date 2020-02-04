---
title: H程式碼JavaScript實作概觀
description: 瞭解在您的網站上實作H代碼的工作流程。
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# H程式碼JavaScript實作概觀

> [!IMPORTANT] 不再支援此版本的資料收集。 升級至 [Adobe Experience Platform Launch](../../launch/overview.md) 或 [JavaScript適用的AppMeasurement](../overview.md)。

您必須擁有托管伺服器的存取權，才能成功實作包含程式碼的頁面以收集資料。 下列步驟會引導您進行基本的Analytics h程式碼實作。

> [!NOTE] 您必須已有現有的副本才能 `s_code.js` 遵循這些指示。 Adobe不再提供在「代碼管理器」中下載H代碼的選項。

1. **更新核心JS檔案變數**:編輯檔 `s_code.js` 案並確定下列變數已更新：
   * `s_account` 包含您要傳送資料至的報表套裝ID。 如需此工具的其他相關資訊，請參閱
   * `s.trackingServer` 包含儲存Cookie的位置。 請參閱 [trackingServer](../../vars/config-vars/trackingserver.md)。
2. **在您的`s_code.js`網站上托管檔案**:此檔案通常駐留在您的Web伺服器上的其他指令碼中。
3. **所有頁`s_code.js`面上的參考**:請確定所有個別頁面都呼叫核心JavaScript檔案，並在HTML標籤( `<body>` 非標籤)中 `<head>` 執行。
   > [!TIP] H代碼要求在標 `s_code.js` 記中調用該腳 `<body>` 本。 這與其他實作方法不同，其中大部份的實作方法都要求指令碼參考位於標 `<head>` 記中。
4. **定義每個頁面上的頁面特定變數**:每個頁面都應定義個別變數，例如頁面名稱或eVar。 個別變數通常在每個頁面上以內 `<script>` 嵌標籤定義。
5. **使用除錯程式來驗證資料收集**:下載並安裝 [Experience cloud除錯程式](../../validate/debugger.md) ，以確保資料已傳送至Adobe，且該頁面變數已正確定義。

## 快取

JavaScript 檔案初始載入後會置於訪客瀏覽器的快取中，通常一個工作階段不會下載超過一次。此檔案即使用於網站上的每個頁面，也不會下載至每個頁面上。大部分網站上的使用者每個工作階段會進行多次頁面檢視，所以將多次使用的 JavaScript 傳輸至此檔案可以減少整體下載資料量。

## H代碼壓縮

如果您擔心檔案的下載大小， `s_code.js` Adobe建議使用GZIP壓 `s_code.js` 縮檔案。 GZIP受到所有主要瀏覽器的支援，其效能比JavaScript壓縮更好。 請參 [閱Apache文檔中的Apache模組mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) 。
