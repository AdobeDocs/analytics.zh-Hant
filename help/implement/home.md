---
title: 實作 Adobe Analytics
description: 在您的網站、屬性或應用程式上實作 Adobe Analytics。
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: 81da9ff9b00a69c49c028fc7f006c161d8ff21d4
workflow-type: ht
source-wordcount: '368'
ht-degree: 100%

---

# 實作 Adobe Analytics

![橫幅](../../assets/doc_banner_implement.png)

Adobe 需要您網站或應用程式的程式碼，才能將資料傳送至 Adobe 的資料收集伺服器。下列步驟說明典型實作的運作方式。

1. 訪客造訪您的網站時，會對您的網路伺服器送出要求。
2. 您的網站網路伺服器會傳送頁面程式碼資訊，且頁面會顯示於瀏覽器。
3. 頁面會載入，Analytics JavaScript 程式碼會運作。JavaScript 程式碼會將影像要求傳送至 Adobe 資料收集伺服器。您在實作中定義的頁面資料，會作為此影像要求中查詢字串的一部分傳送。

4. Adobe 回報空白像素影像。
5. Adobe 伺服器會將收集而來的資料儲存在一個或多個&#x200B;*報表套裝*&#x200B;中。
6. 報表套裝資料會填充在您可於網路瀏覽器取得的報表。

   JavaScript 程式碼會快速開始執行，且對頁面載入時間的影響非常有限。訪客為到達特定頁面而點擊&#x200B;**[!UICONTROL 「重新載入」]**&#x200B;或&#x200B;**[!UICONTROL 「返回」]**&#x200B;時，此方法可讓您計數頁面，因為頁面自快取中擷取時，JavaScript 也可執行。

Adobe Analytics 需要您網站、行動應用程式或其他應用程式中的程式碼，才能將資料傳送至資料收集伺服器。實作此程式碼的方法有很多種，視平台和您組織的需求而定。

* **Adobe Experience Platform Launch：** 標準化且建議的 Adobe Analytics 實作方法。在每個頁面上放置載入器標記，並使用 Launch 的介面來決定每個變數的定義方式。
* **動態標籤管理**：動態標籤管理的生命週期已結束。
* **舊版 JavaScript：**&#x200B;舊版手動實作 Adobe Analytics 的方法。概述實作中使用的變數和設定，這對使用自訂程式碼規則的 Launch 實作來說很有用。
* **行動 SDK**：專用的程式庫，可輕鬆將資料從行動應用程式傳送至 Adobe。

## 重要 Analytics 實作文章

* [負責現有的 Adobe Analytics 實作](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [在 Experience Platform Launch 中建立屬性](launch/create-analytics-property.md)
* [AppMeasurement 更新](appmeasurement-updates.md)

## 更多 Analytics 使用手冊

[Analytics 使用手冊](/help/landing/home.md)

## 重要 Analytics 資源

* [連絡客戶服務](https://helpx.adobe.com/tw/contact/enterprise-support.ec.html)
* [Analytics 論壇](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics 資源](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
