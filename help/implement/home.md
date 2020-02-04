---
title: 實作 Adobe Analytics
description: 在您的網站、屬性或應用程式上實作Adobe Analytics。
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# 實作 Adobe Analytics

![橫幅](../../assets/doc_banner_implement.png)

Adobe需要您網站或應用程式上的程式碼，才能將資料傳送至Adobe的資料收集伺服器。 下列步驟指出典型實作的運作方式。

1. 訪客造訪您的網站時，會對您的網路伺服器送出要求。
2. 您的網站網路伺服器會傳送頁面程式碼資訊，且頁面會顯示於瀏覽器。
3. 頁面會載入，Analytics JavaScript 程式碼會運作。JavaScript程式碼會傳送影像要求Adobe資料收集伺服器。 您在實作中定義的頁面資料會作為此影像要求中查詢字串的一部分傳送。

4. Adobe 回報空白像素影像。
5. Adobe伺服器會將收集的資料儲存在報 *表套裝中*。
6. 報告套裝資料會填充在您可於網路瀏覽器取得的報表。

   JavaScript 程式碼會快速開始執行，且對頁面載入時間的影響非常有限。訪客為到達特定頁面而點擊&#x200B;**[!UICONTROL 「重新載入」]**或**[!UICONTROL 「返回」]**時，此方法可讓您計數頁面，因為頁面自快取中擷取時，JavaScript 也可執行。

Adobe Analytics需要您網站、行動應用程式或其他應用程式中的程式碼，才能將資料傳送至資料收集伺服器。 實作此程式碼的方法有幾種，視平台和您組織的需求而定。

* **Adobe Experience Platform Launch**:實作Adobe Analytics的標準化和推薦方法。 在每個頁面上放置載入器標記，並使用 Launch 的介面來決定每個變數的定義方式。
* **動態標籤管理**:Launch的前身。 DTM 使用類似介面來實作 Analytics，但已不再更新，而且也不是那麼有彈性。Adobe 建議使用 Launch 來實作 Adobe Analytics。
* **舊版JavaScript**:實作Adobe Analytics的歷史手動方法。 概述實作中使用的變數和設定，這對使用自訂程式碼規則的 Launch 實作來說很有用。
* **行動SDK**:專屬的程式庫，可從行動應用程式輕鬆將資料傳送至Adobe。

## 重要 Analytics 實施文章

* [Adobe Debugger](validate/debugger.md)
* [在 Experience Platform Launch 中建立屬性](launch/create-analytics-property.md)
* [AppMeasurement更新](appmeasurement-updates.md)

## 更多 Analytics 使用手冊

[Analytics 使用手冊](/help/landing/home.md)

## 重要 Analytics 資源

* [連絡客戶服務](https://helpx.adobe.com/contact/enterprise-support.ec.html)
* [Analytics 論壇](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics 資源](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
