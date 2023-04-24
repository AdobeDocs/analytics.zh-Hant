---
title: 實施 Adobe Analytics
description: 在您的網站、屬性或應用程式上實施 Adobe Analytics。
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: bdd9473b0ac3bd77ffeff53a095876e21ca2f4d4
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 97%

---

# 實施 Adobe Analytics

![橫幅](../../assets/doc_banner_implement.png)

Adobe 需要您網站或應用程式的程式碼，才能將資料傳送至 Adobe 的資料收集伺服器。下列步驟說明典型實施的運作方式。

1. 訪客造訪您的網站時，會對您的網路伺服器送出要求。
2. 您的網站網路伺服器會傳送頁面代碼資訊，且頁面會顯示於瀏覽器。
3. 頁面會載入，Analytics JavaScript 程式碼會運作。JavaScript 程式碼會將影像要求傳送至 Adobe 資料彙集伺服器。您在實施中定義的頁面資料，會作為此影像要求中查詢字串的一部分傳送。

4. Adobe 回報空白像素影像。
5. Adobe 伺服器會將收集而來的資料儲存在一個或多個&#x200B;*報表套裝*&#x200B;中。
6. 報表套裝資料會填充在您可於網路瀏覽器取得的報表。

JavaScript 程式碼會快速開始執行，且對頁面載入時間的影響非常有限。訪客為到達特定頁面而點擊&#x200B;**[!UICONTROL 「重新載入」]**&#x200B;或&#x200B;**[!UICONTROL 「返回」]**&#x200B;時，此方法可讓您計數頁面，因為頁面自快取中擷取時，JavaScript 也可執行。

Adobe Analytics 需要您網站、行動應用程式或其他應用程式中的程式碼，才能將資料傳送至資料收集伺服器。實施此程式碼的方法有很多種，視平台和您組織的需求而定。

## 網站實施方法

對於您的&#x200B;**網站**，可以使用以下實施方法：

* **Web SDK 擴充功能**：為新客戶實施 Adobe Analytics 的建議標準化方法。在 Adobe Experience Platform 資料彙集&#x200B;**標記**&#x200B;中安裝 **AEP Web SDK 擴充功能**，在每一頁面上使用 Loader 標記，並以對您組織方便使用的格式傳送資料給 Adobe Experience Platform **Edge Network**。Edge Network 以正確格式轉寄傳入資料給 Adobe Analytics。
   ![Web SDK 擴充功能](./assets/websdk-extension-implementation.png)
有關詳細資訊，請參閱[使用 Adobe Experience Platform Web SDK 擴充功能實施 Adobe Analytics](./aep-edge/overview.md)。

* **Web SDK**：如果您不想使用 Adobe Experience Platform 資料彙集，可以手動將 Web SDK 程式庫載入您的網站。在每個頁面上參考 Web SDK 庫 (`alloy.js`)，並以對您組織方便使用的格式將所需的追蹤呼叫傳送到 Adobe Experience Platform **Edge Network**。Edge Network 以正確格式轉寄傳入資料給 Adobe Analytics。
   ![Web SDK](./assets/websdk-implementation.png)
有關詳細資訊，請參閱[使用 Adobe Experience Platform Web SDK 實施 Adobe Analytics](./aep-edge/overview.md)。


* **Analytics 擴充功能**：在 Adobe Experience Platform 資料彙集&#x200B;**標記**&#x200B;中安裝 **Adobe Analytics**。在每一頁面放置 Loader 標記，並使用 Adobe Analytics 擴充功能以決定如何定義每個變數。如果您想要標記的便利性，但又不想使用 Edge Network 基礎結構，請使用此實施方法。
   ![Adobe Analytics 擴充功能](./assets/analytics-extension-implementation.png)
有關詳細資訊，請參閱[使用 Analytics 擴充功能實施 Adobe Analytics](launch/overview.md)。

* **舊版 JavaScript**：舊版手動實施 Adobe Analytics 的方法。在每個頁面上參考 AppMeasurement 庫 (`AppMeasurement.js`)，然後概觀實施中使用的變數和設定。
   ![舊版 JavaScript](./assets/appmeasurement-implementation.png)
此實施方法對於使用自訂程式碼的實施非常有用，也建議在您 (想要) 進行以下行為時使用：

   * [activity map資料](../analyze/activity-map/activity-map.md),

      >[!INFO]
      >
      >使用最新的Web SDK，即支援Activity Map。 請參閱 [啟用Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) 以取得更多資訊。

   * [串流媒體測量](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=zh-Hant)

   * [直播 API 或直播觸發器](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)

   * [AMP 頁面追蹤](./other/amp.md)
   有關詳細資訊，請參閱[使用 AppMeasurement for JavaScript 實施 Adobe Analytics](js/overview.md)。

以下決策流程可幫助您選擇實施方法：

![決策樹](./assets/decision-tree.png)


>[!TIP]
>
>請聯絡 Adobe，以取得根據您目前情況該選擇哪種實施方式的建議和最佳做法。

## 行動應用程式實施方法

對於您的&#x200B;**行動應用程式**，可以使用以下實施方法：

* **Mobile SDK 擴充功能**：在您的行動應用程式中實施 Adobe Analytics 的建議標準化方法。使用專用的程式庫，可輕鬆將資料從行動應用程式傳送至 Adobe。在 Adobe Experience Platform 資料彙集&#x200B;**標記**&#x200B;中安裝 **Adobe Experience Platform Mobile SDK 擴充功能**，並在您的應用程式中實施正確的程式碼以匯入程式庫、註冊擴充功能和載入標記設定。這會將資料以您的組織方便的格式發送到 Adobe Experience Platform **Edge Network**。體驗 Edge 以正確格式轉寄傳入資料給 Adobe Analytics。
   ![Mobile SDK 擴充功能](./assets/mobilesdk-extension.png)

   有關詳細資訊，請參閱[使用 Adobe Experience Platform Mobile SDK 實施 Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md)。

* **Analytics 擴充功能**：在 Adobe Experience Platform 資料彙集&#x200B;**標記**&#x200B;中安裝 **Adobe Analytics 擴充功能**，並在您的應用程式中實施正確的程式碼以匯入程式庫、註冊擴充功能和載入標記設定。使用 Analytics 擴充功能以決定如何定義每個變數。如果您想要 Adobe Experience Platform 資料彙集的便利性，但又不想使用 Adobe 的 Experience Platform Edge Network 基礎結構，請使用此實施方法。
   ![Analytics 擴充功能](./assets/mobilesdk-analytics-extension.png)

   有關詳細資訊，請參閱[使用 Analytics 擴充功能實施 Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md)。


>[!CAUTION]
>
>版本 4 Mobile SDK 於 2021 年 8 月 31 日終止支援。 如需詳細資訊，請參閱[第 4 版 Mobile SDK 支援終止常見問題](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/)。

## 重要 Analytics 實施文章

* [負責現有的 Adobe Analytics 實施](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [在 Experience Platform 中建立標籤屬性](launch/create-analytics-property.md)
* [AppMeasurement 更新](appmeasurement-updates.md)

## 更多 Analytics 使用手冊

[Analytics 使用手冊](https://experienceleague.adobe.com/docs/analytics.html?lang=zh-Hant)

## 重要 Analytics 資源

* [連絡客戶服務](https://experienceleague.adobe.com/?support-solution=Analytics#support)
* [Analytics 論壇](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)
* [Adobe Analytics 資源](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666)
