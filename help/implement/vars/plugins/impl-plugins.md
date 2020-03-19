---
title: 增效模組概觀
description: 將程式碼貼在您的網站上，以引入新功能。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 增效模組概觀

外掛程式是程式碼的片段，可執行數種進階功能，以協助您實作Analytics。 這些外掛程式可擴充 JavaScript 檔案的功能，讓您獲得更多在基本實作中無法使用的功能。Adobe 在進階解決方案中另外提供了許多外掛程式。

> [!IMPORTANT] Adobe Consulting提供外掛程式，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供這些外掛程式的支援，包括安裝或疑難排解。 如果您需要外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

Adobe提供數種安裝特定外掛程式的方式：

1. 使用Adobe Experience Platform Launch的「通用分析外掛程式」擴充功能
2. 使用啟動自訂程式碼編輯器貼上外掛程式程式碼
3. 將外掛程式碼貼入您的檔 `AppMeasurement.js` 案

每個組織有不同的實作需求，因此您可以決定要如何將它們納入實作中。 在網站上加入程式碼時，請務必符合下列條件：

1. 先執行個體化Analytics追蹤物件(使 [`s_gi`](../functions/s-gi.md)用)。
   * 當Adobe Analytics載入時，Launch會自動執行個體化追蹤物件。
   * 使用的實 `AppMeasurement.js` 施通常會在JavaScript檔案頂端初始化追蹤物件。
2. 先加入外掛程式程式碼。
   * 「通用分析外掛程式」擴充功能有動作設定，您可在其中初始化外掛程式。
   * 如果您不想使用外掛程式，可在設定Analytics擴充功能時，在自訂程式碼編輯器中貼上外掛程式程式碼。
   * 如果您的實作不使用Launch，則可在執行個體化追蹤物件後，將外掛程式 `AppMeasurement.js` 碼貼至任何位置。
3. 呼叫增效模組第3個。
   * 所有實作（包括Launch內部和外部）都使用JavaScript來呼叫外掛程式。 使用外掛程式頁面上記載的格式呼叫外掛程式。
4. 驗證您的實作和發佈。

許多組織都使用函式呼叫外掛 [`doPlugins`](../functions/doplugins.md) 程式。 雖然此功能不是必要功能，但Adobe認為使用此功能是最佳實務。 AppMeasurement會在編譯和傳送影像要求之前呼叫此函式，這是最理想的選擇，因為數個外掛程式需仰賴其他Analytics變數。
