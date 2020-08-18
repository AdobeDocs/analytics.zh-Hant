---
title: 實作常見問答集
description: 實施的相關常見問題，以及可提供更多資訊的連結。
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 67%

---


# Analytics 實施常見問題集

實施的相關常見問題，以及可提供更多資訊的連結。

## Experience Cloud 訪客 ID 與 Analytics 訪客 ID 有何不同？

Identity Service 會指派不重複的持續性識別碼，以便在 Experience Cloud 的其他解決方案之間共用。Analytics 訪客 ID 僅供 Analytics 使用。Adobe 建議您在實施中使用 Experience Cloud 訪客 ID 服務。

## 如何實施心率視訊追蹤？

請參閱[在 Adobe Analytics 測量音訊和視訊](https://docs.adobe.com/content/help/zh-Hant/media-analytics/using/media-overview.html)。

## Adobe 的服務中斷會影響效能嗎？

不可以。JavaScript 檔案並非由 Adobe 伺服器託管，所以 Adobe 中斷不會影響 AppMeasurement 程式庫。如果您使用 Adobe Experience Platform Launch，JavaScript 檔案會由 Akamai 託管，或於貴組織所決定的伺服器位置託管。

## 從瀏覽器傳送資料給 Adobe 服務會降低效能嗎？

AppMeasurement 會在 HTML 頁面內部建立影像物件，接著瀏覽器再向 Adobe 資料收集伺服器要求該影像物件。如果資料收集伺服器效能緩慢或無反應，處理該要求的執行緒會延遲，直到傳回影像或逾時。因為瀏覽器使用多個執行緒來處理影像，Adobe 中斷對頁面載入時間的影響極小，最多只會佔用一個執行緒，而其他執行緒仍持續運作。

## 如何使Analytics實作無效或移除？

有時，組織會因為合約到期而想要移除實施，或是減少伺服器呼叫數。

* **使用Launch的實作**:在「延伸功能」標籤中停用或解除安裝Adobe Analytics [!UICONTROL 延伸功能] ，然後發佈。
* **舊版AppMeasurement實作**:使用下列程式碼 `s_code.js` 行取代檔案的整個內容：

```js
var s = new Object();
```

>[!WARNING]
>
>不要：
>
>* 將報表套裝變更為無效值，因為這會在Adobe伺服器上造成不必要的載入。
>* 完全移 `s_code.js` 除檔案，除非您也移除每個頁面上檔案的所有參照。
>* 變更變 `trackingServer` 數以遠離Adobe。 AppMeasurement仍會傳送影像要求，傳回404個錯誤。

