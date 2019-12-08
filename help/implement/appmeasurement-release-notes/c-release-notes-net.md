---
description: 'null'
subtopic: Release notes
title: Windows Silverlight、NET、IIS、XBOX
topic: Developer and implementation
uuid: 15c20bca-4886-4d57-9957-fe99743851ea
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Windows Silverlight、NET、IIS、XBOX{#windows-silverlight-net-iis-xbox}

>[!IMPORTANT]
>
>這些 SDK 已廢止，將不再由 Adobe 提供支援或分發。

> [!NOTE]若要尋找目前的程式庫版本，請開啟偵錯記錄功能。

## 版本 1.4.2 {#section_2B70F52C4D214A43844CCEC6B45037F0}

發行日期: **2014 年 8 月**

* 移除 [!DNL Microsoft Silverlight Analytics Framework] 的支援。Adobe 不再支援獲分發對 [!DNL AppMeasurement] 的 [!DNL Microsoft Silverlight Analytics Framework] 整合。

* 進行內部變更，以支援未來功能。

## 版本 1.4.1 {#section_9134F77804BF472291DA7243FAC89C2B}

發行日期: **2013 年 3 月**

* 修正在外部瀏覽器內容外和在 [!DNL Microsoft Silverlight Analytics Framework] 元件適度公開的 SSL 屬性中，於 [!DNL Silverlight] 內取得預設反向連結的例外狀況。

## 版本 1.4 {#section_2F4ADA4628EC43B480177C3DDB3D1CFA}

發行日期: **2013 年 2 月**

* 新增傳送長度超過 255 個位元組之 URL 的支援，進而在 Adobe Data Collection 伺服器中支援「頁面 URL」欄位的擴充。長度超過 255 個位元組的頁面 URL 會被切割，前 255 個位元組出現在 `g=` 參數，其餘位元組出現在 `-g=` 查詢參數的查詢字串中。這麼一來，在瀏覽器切截字串的情況下，可以避免長 URL 佔據其他資料，但仍可擷取長 URL。

* 新增後援訪客識別方法。請參閱[識別獨特訪客](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html)。
* 新增可以在 `doPlugins` 內設定的新 `abort` 標幟。若將此標幟設為 true，會使得 [!DNL AppMeasurement] 庫不再繼續使用該追蹤呼叫。中止標幟皆會隨每個追蹤呼叫重設，因此若後續的追蹤呼叫也需要被中止，就必須在 `doPlugins` 中再次設定此標幟。

   ```js
   s.doPlugins = function(s) { 
        s.campaign = s.getQueryParam("cid"); 
        if ((!s.campaign) && (!s.events)) { 
             s.abort = true; 
        } 
   };
   ```

   這讓您可以集中邏輯，用於識別不想追蹤的活動，例如自訂連結或顯示廣告中的外部連結。

## 版本 1.3.8 {#section_03089199E2DE4199B32F6821DDAED7BD}

發行日期: **2012 年 9 月**

* 修正當使用自訂 `media.monitor` 方法來追蹤媒體關閉事件時，可能無法傳送視訊結束事件的問題。

   ```
   If(media.event=="CLOSE") { 
   … 
   } 
   ```

## 版本 1.3.7 {#section_32AA8AE0CED4495496D25BF9246AE8AB}

發行日期: **2012 年 4 月**

* 新增依區段劃分 [!DNL XBOX]。

## 版本 1.3.6 {#section_9F2738FA31CD48C4877AB92281EC67A9}

發行日期: **2012 年 2 月**

* [!DNL iOS] Phone 7: 修正 offlineThrottleDelay 無法正確套用的問題。
* 新增時間戳記至搭配光源追蹤呼叫 (trackLight) 的變數。

## 版本 1.3.5 {#section_28BBDE7D187547A4AACCA60E5154DCD2}

發行日期: **2012 年 1 月**

* 以新方式更新視訊追蹤，現可追蹤完整的視訊檢視次數。請參閱[在 Analytics 中測量影片](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/index.html)。

## 版本 1.3.4 {#section_43788EE6B57E4B2DBEED68BE6954D9CA}

* [!DNL iOS] Phone 平台的新支援與組建包含離線追蹤。
* 支援 doRequest 委派，以覆蓋送出要求進行資料追蹤的方式。
* 支援可提升伺服器端處理規則的 contextData (僅限 v15)。
* 支援輕伺服器呼叫 (目前測試中)。
* 支援將 1 以外的值指派給事件清單中的計數器事件。
* 支援使用轉換 eVars 和事件追蹤視訊的新方法 (目前測試中)。

