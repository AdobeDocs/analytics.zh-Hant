---
title: 實作 Adobe Analytics
description: 在您的網站、屬性或應用程式上實作 Adobe Analytics。
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: d2c291f7db465034ffadc4a2c1caf9639caf2a1d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 79%

---

# 實作 Adobe Analytics

![橫幅](../../assets/doc_banner_implement.png)

以下是 Adobe Analytics 的影片概觀：

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Adobe 需要您網站或應用程式的程式碼，才能將資料傳送至 Adobe 的資料收集伺服器。下列步驟說明典型實作的運作方式。

1. 訪客造訪您的網站時，會對您的網路伺服器送出要求。
2. 您的網站網路伺服器會傳送頁面程式碼資訊，且頁面會顯示於瀏覽器。
3. 頁面會載入，Analytics JavaScript 程式碼會運作。
4. JavaScript程式碼會傳送1x1像素影像要求給Adobe資料收集伺服器。 您在實作中定義的頁面資料，會作為此影像要求中查詢字串的一部分傳送。
5. Adobe的資料收集伺服器會傳回請求的影像。
6. Adobe伺服器會剖析並儲存報表套裝中收集的資料。
7. 報表套裝資料會填充在您可於網路瀏覽器取得的報表。


Adobe提供數種實作此程式碼的方法，視平台和您組織的需求而定。

* **Web SDK擴充功能**:目前、標準化且建議的實作Adobe Analytics方法。 在 Adobe Experience Platform 資料彙集中安裝 Web SDK 擴充功能，在每一頁面上使用 Loader 標記，並以對您組織方便使用的格式傳送資料給 Adobe Experience Platform Edge。體驗 Edge 以正確格式轉寄傳入資料給 Adobe Analytics。
* **Web SDK**:如果您不想使用「標籤」，可以手動載入網站上的Web SDK程式庫。 在每個頁面上參考 Web SDK 程式庫，並將所需的追蹤呼叫傳送到 Adobe Experience Edge。
* **Adobe Analytics 擴充功能**：在 Adobe Experience Platform 資料彙集中安裝 Adobe Analytics。在每一頁面放置 Loader 標記，並使用 Analytics 擴充功能以決定如何定義每個變數。
* **舊版 JavaScript：**&#x200B;舊版手動實作 Adobe Analytics 的方法。概述實作中使用的變數和設定，這對使用自訂程式碼規則的實作來說很有用。
* **行動 SDK**：專用的資料庫，可輕鬆將資料從行動應用程式傳送至 Adobe。

## 重要 Analytics 實作文章

* [負責現有的 Adobe Analytics 實作](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [在 Experience Platform 中建立標記屬性](launch/create-analytics-property.md)
* [AppMeasurement 更新](appmeasurement-updates.md)

## 更多 Analytics 使用手冊

[Analytics 使用手冊](https://experienceleague.adobe.com/docs/analytics.html)

## 重要 Analytics 資源

* [連絡客戶服務](https://experienceleague.adobe.com/?support-solution=Analytics#support)
* [Analytics 論壇](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics 資源](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
