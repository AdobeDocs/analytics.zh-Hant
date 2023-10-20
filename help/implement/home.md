---
title: 實施 Adobe Analytics
description: 在您的網站、屬性或應用程式上實施 Adobe Analytics。
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: b157674adf67fa6ef0f2e75775d0ec888cff3cba
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 55%

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

* **Web SDK 擴充功能**：為新客戶實施 Adobe Analytics 的建議標準化方法。新增 **Adobe Experience Platform Web SDK擴充功能** 在Adobe Experience Platform Data Collection **標籤**，然後在每個頁面上放置載入器標籤。 標籤會將資料傳送至Adobe Experience Platform **Edge Network**，會將資料轉送至Adobe Analytics。
  ![Web SDK擴充功能](./assets/websdk-extension-implementation.png)
另請參閱 [如何使用Adobe Analytics Web SDK擴充功能實施Adobe Experience Platform。](./aep-edge/overview.md)以取得更多資訊。

* **Web SDK**：如果您不想使用 Adobe Experience Platform 資料彙集，可以手動將 Web SDK 程式庫載入您的網站。在每個頁面上參考 Web SDK 庫 (`alloy.js`)，並以對您組織方便使用的格式將所需的追蹤呼叫傳送到 Adobe Experience Platform **Edge Network**。Edge Network會將該資料轉送至Adobe Analytics。
  ![Web SDK](./assets/websdk-implementation.png)
另請參閱 [如何使用Adobe Experience Platform Web SDK實作Adobe Analytics](./aep-edge/overview.md) 以取得詳細資訊。

* **Analytics擴充功能**：新增 **Adobe Analytics擴充功能** 在Adobe Experience Platform Data Collection **標籤**，然後在每個頁面上放置載入器標籤。 標籤會直接將資料傳送至Adobe Analytics。 如果您想要Tags的便利性，但不想使用Edge Network基礎結構，請使用此實作方法。
  ![Adobe Analytics擴充功能](./assets/analytics-extension-implementation.png)
另請參閱 [如何使用Analytics擴充功能實施Adobe Analytics](launch/overview.md) 以取得詳細資訊。

* **舊版 JavaScript**：舊版手動實施 Adobe Analytics 的方法。參考AppMeasurement程式庫(`AppMeasurement.js`)，然後在JavaScript中設定變數和設定。
  ![如何使用舊版JavaScript實施Adobe Analytics](./assets/appmeasurement-implementation.png)
此實作方法適用於使用自訂程式碼的實作，也非常適合其他地方未提供的實作型別，例如 [AMP頁面](other/amp.md).

下列決定流程可協助您選取實作方法：

![用於選取實施方法的決策樹，如本節所述。](./assets/decision-tree.png)


>[!TIP]
>
>請聯絡您的Adobe客戶團隊，以取得根據您目前的情況來選擇實作的建議和最佳實務。

## 行動應用程式實施方法

對於您的&#x200B;**行動應用程式**，可以使用以下實施方法：

* **Mobile SDK 擴充功能**：在您的行動應用程式中實施 Adobe Analytics 的建議標準化方法。使用專用的程式庫，可輕鬆將資料從行動應用程式傳送至 Adobe。新增 **Adobe Experience Platform Mobile SDK擴充功能** 在Adobe Experience Platform Data Collection **標籤**，然後在應用程式中實作Mobile SDK程式庫。 您可以使用SDK來匯入程式庫、註冊擴充功能及載入標籤設定。 將資料傳送至Adobe Experience Platform **Edge Network**；然後Edge將該資料轉送至Adobe Analytics。
  ![Mobile SDK 擴充功能](./assets/mobilesdk-extension.png)

  有關詳細資訊，請參閱[使用 Adobe Experience Platform Mobile SDK 實施 Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md)。

* **Analytics擴充功能**：新增 **Adobe Analytics擴充功能** 在Adobe Experience Platform Data Collection **標籤**，並在應用程式中實作Mobile SDK資料庫。 您可以使用SDK來匯入程式庫、註冊擴充功能及載入標籤設定。 此實作方法會將資料直接傳送至Adobe Analytics。 如果您想要Adobe Experience Platform資料收集的便利性，但不想使用Adobe的Experience Platform邊緣網路基礎結構，建議使用此功能。
  ![Analytics 擴充功能](./assets/mobilesdk-analytics-extension.png)

  有關詳細資訊，請參閱[使用 Analytics 擴充功能實施 Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md)。


>[!CAUTION]
>
>版本 4 Mobile SDK 於 2021 年 8 月 31 日終止支援。 如需詳細資訊，請參閱[第 4 版 Mobile SDK 支援終止常見問題](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/v4-faq/)。

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
