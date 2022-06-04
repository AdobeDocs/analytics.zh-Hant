---
title: 使用AppMeasurement for JavaScript實現Adobe Analytics
description: 瞭解如何在不使用標記管理系統的情況下使用 JavaScript 實施 Adobe Analytics。
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
source-git-commit: 99fc7814eaa12d0d9e8e478629a4c2134a577aaa
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 91%

---

# 使用AppMeasurement for JavaScript實現Adobe Analytics

JavaScript 適用的 AppMeasurement 向來是實施 Adobe Analytics 的常用方法。但由於標記管理系統越來越熱門，所以建議使用 [Adobe Experience Platform 中的標記](../launch/overview.md)。

## 使用 JavaScript 將資料傳送至 Adobe 的整體工作流程

1. 載入 `AppMeasurement.js` 檔案。此檔案包含將資料傳送至 Adobe 所需的資料庫。

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. 在中定義設定 `AppMeasurement.js` 變數。Analytics 物件實例化時，這些變數可確保資料彙集設定正確無誤。如需可定義變數的完整清單，請參閱[設定變數](../vars/config-vars/configuration-variables.md)。

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. 在網站的頁面代碼中定義頁面層級變數。這些變數會決定傳送至 Adobe 的特定維度和量度。如需可定義變數的完整清單，請參閱[頁面變數](../vars/page-vars/page-variables.md)。

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. 定義所有頁面層級變數後，請使用 `t()` 方法將資料傳送至 Adobe。如需詳細資訊，請參閱 [t](../vars/functions/t-method.md)。

   ```js
   s.t();
   ```
