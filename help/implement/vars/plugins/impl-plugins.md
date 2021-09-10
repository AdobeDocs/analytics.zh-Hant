---
title: 外掛程式概述
description: 將程式碼貼在您的網站上以引入新功能。
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
source-git-commit: ab078c5da7e0e38ab9f0f941b407cad0b42dd4d1
workflow-type: ht
source-wordcount: '366'
ht-degree: 100%

---

# 外掛程式概述

外掛程式是程式碼的片段，可執行數種進階功能，協助您實施 Analytics。這些外掛程式可擴充 JavaScript 檔案的功能，讓您獲得更多在基本實施中無法使用的功能。Adobe 在進階解決方案中另外提供了許多外掛程式。

>[!IMPORTANT]
>
>Adobe Consulting 提供外掛程式，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供這些外掛程式的支援，包括安裝或疑難排解在內。如果您需要與外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

Adobe 提供多種安裝指定外掛程式的方式：

1. 使用 Adobe Experience Platform 中的標記來使用「常用 Analytics 外掛程式」擴充功能
2. 使用自訂程式碼編輯器貼上外掛程式的程式碼
3. 將外掛程式的程式碼貼入您的 `AppMeasurement.js` 檔案中

每個組織的實施需求均不同，您可以決定要如何將外掛程式納入實施中。在網站上加入程式碼時，請務必符合下列條件：

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

許多組織都使用 [`doPlugins`](../functions/doplugins.md) 函數呼叫外掛程式。雖然此函數並非必要項目，但 Adobe 認為使用此函數是最佳做法。AppMeasurement 會在編譯和傳送影像要求之前呼叫此函數，這是最理想的作法，因為有多個外掛程式相依於其他 Analytics 變數。
