---
title: 外掛程式概觀
description: 將程式碼貼在您的網站上以引入新功能。
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ImzoBRU0DajPc99vRlu1698CteFNk9dOS2OZrN9DBZs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 79%

---

# 外掛程式概觀

外掛程式是程式碼的片段，可執行數種進階功能，協助您實施 Analytics。 這些外掛程式可擴充 JavaScript 檔案的功能，讓您獲得更多在基本實施中無法使用的功能。 Adobe 在進階解決方案中另外提供了許多外掛程式。

{{plug-in}}

Adobe 提供多種安裝指定外掛程式的方式：

* 透過Adobe Analytics擴充功能使用「常用Analytics外掛程式」擴充功能
* 使用自訂程式碼編輯器貼上外掛程式的程式碼
* 將外掛程式的程式碼貼入您的 `AppMeasurement.js` 檔案中

每個組織的實施需求均不同，您可以決定要如何將外掛程式納入實施中。 在網站上加入程式碼時，請務必符合下列條件：

1. 第一步為實例化 Analytics 追蹤物件 (使用 [`s_gi`](../functions/s-gi.md))。
   * 當 Adobe Analytics 載入時，您已啟用標記功能的網站會自動將追蹤物件實體化。
   * 使用 `AppMeasurement.js` 的實施通常會在 JavaScript 檔案最上方初始化追蹤物件。
2. 第二步為加入外掛程式的程式碼。
   * 「常用 Analytics 外掛程式」擴充功能具有動作設定，您可在其中初始化外掛程式。
   * 如果您不想使用擴充功能，可在設定 Analytics 擴充功能時，在自訂程式碼編輯器中貼上外掛程式程式碼。
   * 如果您的實作未使用 Adobe Experience Platform 中的標記，則當您將追蹤物件實體化之後，可以將外掛程式的程式碼貼到 `AppMeasurement.js` 中的任何地方。
3. 第三步為呼叫外掛程式。
   * 已啟用標記功能的網站內外的所有實作都會使用 JavaScript 來呼叫外掛程式。 請使用該外掛程式頁面上記錄的格式呼叫外掛程式。
4. 驗證您的實施並發佈。

許多組織都使用 [`doPlugins`](../functions/doplugins.md) 函數呼叫外掛程式。 雖然此函數並非必要項目，但 Adobe 認為使用此函數是最佳做法。 AppMeasurement 會在編譯和傳送影像要求之前呼叫此函數，這是最理想的作法，因為有多個外掛程式相依於其他 Analytics 變數。

## 淘汰的外掛程式

下列外掛程式已淘汰。 如果您在舊版實作中遇到這些錯誤，請參考這裡檔案。

* **`getPageLoadTime`**：使用JavaScript效能物件測量頁面完全載入所花的時間。 不再支援此功能，因為其程式碼依賴[`PerformanceTiming`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming)介面，該介面在大多數的現代瀏覽器中已停用。 沒有直接的替代方案，也不再提供安裝指示和外掛程式程式碼。
