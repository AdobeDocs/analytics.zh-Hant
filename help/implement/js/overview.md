---
title: JavaScript 適用的 AppMeasurement
description: 瞭解如何使用JavaScript在不使用標籤管理系統的情況下實作Adobe Analytics。
translation-type: tm+mt
source-git-commit: 59956169308291e7607a2712cd63a802d7b8bd11

---


# JavaScript 適用的 AppMeasurement

JavaScript適用的AppMeasurement向來是實作Adobe Analytics的常用方法。 不過，隨著標籤管理系統日益普及，建議 [使用Adobe Experience Platform Launch](../launch/overview.md) 。

## 使用JavaScript傳送資料至Adobe的整體工作流程

1. 載入檔 `AppMeasurement.js` 案。 此檔案包含傳送資料至Adobe所需的程式庫。

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. 在中定義配置變 `AppMeasurement.js`數。 當Analytics物件實例化時，這些變數會確保資料收集設定正確無誤。 如需 [您可定義之變數的完整清單](../vars/config-vars/configuration-variables.md) ，請參閱設定變數。

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.omtrdc.net";
   ```

3. 在網站的頁面代碼中定義頁面層級變數。 這些變數會決定傳送至Adobe的特定維度和量度。 如需 [您可定義之變數的完整清單](../vars/page-vars/page-variables.md) ，請參閱頁面變數。

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. 定義所有頁面層級變數後，請使用函式將資料傳送至 `t` Adobe。 如需詳 [細資訊](../vars/functions/t-method.md) ，請參閱「t」。

   ```js
   s.t();
   ```
