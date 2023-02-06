---
title: 實作 Adobe Analytics
description: 在您的網站、屬性或應用程式上實作 Adobe Analytics。
feature: Implementation Basics
source-git-commit: d9a5d8a15b9e108af795cdfb7ed5481d51311328
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 40%

---

# 實作 Adobe Analytics

![橫幅](../../assets/doc_banner_implement.png)

Adobe 需要您網站或應用程式的程式碼，才能將資料傳送至 Adobe 的資料收集伺服器。下列步驟說明典型實作的運作方式。

1. 訪客造訪您的網站時，會對您的網路伺服器送出要求。
2. 您的網站網路伺服器會傳送頁面代碼資訊，且頁面會顯示於瀏覽器。
3. 頁面會載入，Analytics JavaScript 程式碼會運作。JavaScript程式碼會傳送影像要求給Adobe資料收集伺服器。 您在實作中定義的頁面資料，會作為此影像要求中查詢字串的一部分傳送。

4. Adobe 回報空白像素影像。
5. Adobe 伺服器會將收集而來的資料儲存在一個或多個&#x200B;*報表套裝*&#x200B;中。
6. 報表套裝資料會填充在您可於網路瀏覽器取得的報表。

JavaScript 程式碼會快速開始執行，且對頁面載入時間的影響非常有限。訪客為到達特定頁面而點擊&#x200B;**[!UICONTROL 「重新載入」]**&#x200B;或&#x200B;**[!UICONTROL 「返回」]**&#x200B;時，此方法可讓您計數頁面，因為頁面自快取中擷取時，JavaScript 也可執行。

Adobe Analytics 需要您網站、行動應用程式或其他應用程式中的程式碼，才能將資料傳送至資料收集伺服器。實作此程式碼的方法有很多種，視平台和您組織的需求而定。

## 網站實施方法

針對您的 **網站**，可使用下列實施方法：

* **Web SDK擴充功能**:為新客戶實作Adobe Analytics的標準化且建議的方法。 安裝 **AEP Web SDK擴充功能** 在Adobe Experience Platform資料收集 **標籤**，請在每個頁面上使用載入器標籤，並將資料傳送至Adobe Experience Platform **邊緣網路** 格式，方便您的組織使用。 邊緣網路以正確的格式將傳入的資料轉送至Adobe Analytics。
   ![Web SDK擴充功能](./assets/websdk-extension-implementation.png)
請參閱 [使用Adobe Experience Platform Web SDK擴充功能實作Adobe Analytics](./aep-edge/overview.md) 以取得更多資訊。

* **Web SDK**：如果您不想使用 Adobe Experience Platform 資料彙集，可以手動將 Web SDK 程式庫載入您的網站。參考Web SDK程式庫(`alloy.js`)，並將所需的追蹤呼叫傳送至Adobe Experience Platform **邊緣網路** 格式，方便您的組織使用。 邊緣網路以正確的格式將傳入的資料轉送至Adobe Analytics。
   ![Web SDK](./assets/websdk-implementation.png)
請參閱 [使用Adobe Experience Platform Web SDK實作Adobe Analytics](./aep-edge/overview.md) 以取得更多資訊。


* **Analytics擴充功能**:安裝 **Adobe Analytics擴充功能** 在Adobe Experience Platform資料收集 **標籤**. 在每個頁面上放置載入器標籤，並使用Adobe Analytics擴充功能來判斷每個變數的定義方式。 如果您想要方便標籤，但不想使用邊緣網路基礎架構，請使用此實施方法。
   ![Adobe Analytics擴充功能](./assets/analytics-extension-implementation.png)
請參閱 [使用Analytics擴充功能實作Adobe Analytics](launch/overview.md) 以取得更多資訊。

* **舊版 JavaScript：**&#x200B;舊版手動實作 Adobe Analytics 的方法。參考AppMeasurement程式庫(`AppMeasurement.js`)，然後概述實作中使用的變數和設定。
   ![舊版JavaScript](./assets/appmeasurement-implementation.png)
此實作方法對使用自訂程式碼的實作相當實用，但若您（想要）使用：

   * [點按層級activity map資料](../analyze/activity-map/activity-map.md),

   * [串流媒體測量](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=zh-Hant),

   * [livestream API或livestream觸發器](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md),

   * [AMP頁面追蹤](./other/amp.md)
   請參閱 [使用JavaScript適用的AppMeasurement實作Adobe Analytics](js/overview.md) 以取得更多資訊。

下列決策流程可協助您選取實施方法：

![決策樹](./assets/decision-tree.png)


>[!TIP]
>
>請連絡Adobe，以取得建議和最佳實務，以便根據您目前的情況選擇哪些實作。

## 行動應用程式實作方法

針對您的 **行動應用程式**，可使用下列實施方法：

* **行動SDK擴充功能**:在行動應用程式中實作Adobe Analytics的標準化且建議的方法。 使用專用的程式庫，輕鬆將資料從行動應用程式傳送至Adobe。 安裝 **Adobe Experience Platform Mobile SDK擴充功能** 在Adobe Experience Platform資料收集 **標籤** 並在您的應用程式中實作正確的程式碼，以匯入程式庫、註冊擴充功能及載入標籤設定。 這會將資料傳送至Adobe Experience Platform **邊緣網路** 格式，方便您的組織使用。 體驗 Edge 以正確格式轉寄傳入資料給 Adobe Analytics。
   ![行動SDK擴充功能](./assets/mobilesdk-extension.png)

   請參閱 [使用Adobe Experience Platform Mobile SDK實作Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md) 以取得更多資訊。

* **Analytics擴充功能**:安裝 **Adobe Analytics擴充功能** 在Adobe Experience Platform資料收集 **標籤**，並在您的應用程式中實作正確的程式碼，以匯入程式庫、註冊擴充功能及載入標籤設定。 使用Analytics擴充功能來判斷每個變數的定義方式。 如果您想要方便使用Adobe Experience Platform資料收集，但不想使用Adobe的Experience Platform邊緣網路基礎架構，請使用此實作方法。
   ![Analytics 擴充功能](./assets/mobilesdk-analytics-extension.png)

   請參閱 [使用Analytics擴充功能實作Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md) 以取得更多資訊。


>[!CAUTION]
>
>2021年8月31日停止支援第4版Mobile SDK。 如需詳細資訊，請參閱[第 4 版行動 SDK 支援終止常見問答](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/)。

## 重要 Analytics 實作文章

* [負責現有的 Adobe Analytics 實作](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [在 Experience Platform 中建立標籤屬性](launch/create-analytics-property.md)
* [AppMeasurement 更新](appmeasurement-updates.md)

## 更多 Analytics 使用手冊

[Analytics 使用手冊](https://experienceleague.adobe.com/docs/analytics.html)

## 重要 Analytics 資源

* [連絡客戶服務](https://experienceleague.adobe.com/?support-solution=Analytics#support)
* [Analytics 論壇](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)
* [Adobe Analytics 資源](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666)
