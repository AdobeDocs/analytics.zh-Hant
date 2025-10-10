---
title: 實作常見問答
description: 實作的相關常見問答，以及可提供更多資訊的連結。
feature: Implementation Basics
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
role: Admin, Developer, Leader, User
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 100%

---

# Analytics 實作常見問答

實作的相關常見問答，以及可提供更多資訊的連結。

## Experience Cloud 訪客 ID 與 Analytics 訪客 ID 有何不同？

身分識別服務會指派不重複的持續性識別碼，以便在 Experience Cloud 的其他解決方案之間共用。Analytics 訪客 ID 僅供 Analytics 使用。Adobe 建議您在實作中使用 Experience Cloud 訪客 ID 服務。

## 如何實施心率視訊追蹤？

請參閱[在 Adobe Analytics 測量音訊和視訊](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html)。

## Adobe 的服務中斷是否會影響效能？

否。 JavaScript 檔案並非由 Adobe 伺服器託管，所以 Adobe 中斷不會影響 AppMeasurement 資料庫。如果您使用 Adobe Experience Platform 中的標記，則 JavaScript 檔案會由 Akamai 代管，或是在貴組織決定的伺服器位置上代管。

## 從瀏覽器傳送資料給 Adobe 服務會降低效能嗎？

AppMeasurement 會在 HTML 頁面內部建立影像物件，接著瀏覽器再向 Adobe 資料收集伺服器要求該影像物件。如果資料收集伺服器效能緩慢或無反應，處理該要求的執行緒會延遲，直到傳回影像或逾時。因為瀏覽器使用多個執行緒來處理影像，Adobe 中斷對頁面載入時間的影響極小，最多只會佔用一個執行緒，而其他執行緒仍持續運作。

## 如何使 Analytics 實作無效或加以移除？

有時組織會因為合約過期，或是需減少伺服器呼叫數而想要移除實作。

* **使用 Adobe Experience Platform Data Collection 進行實作**：在[!UICONTROL 擴充功能]索引標籤停用或是解除安裝適用的 Adobe Analytics、Web SDK 或 Mobile SDK 擴充功能，然後發佈。
* **舊版 AppMeasurement 實作**：使用下列程式碼行取代 `s_code.js` 檔案的整個內容：

```js
var s = new Object();
```

>[!WARNING]
>
>請勿：
>
>* 將報表套裝變更為無效值，因為這會在 Adobe 伺服器上造成不必要的負載。
>* 完全移除 `s_code.js` 檔案，除非您同時移除每個頁面上該檔案的所有參照。
>* 變更 `trackingServer` 變數以遠離 Adobe。AppMeasurement 仍會傳送影像要求，而要求會傳回 404 錯誤。

## 我透過程式碼分析器執行了 AppMeasurement，而且它將 `Math.random()` 的使用標記為可能有安全性風險。 `Math.random()` 是否會與任何敏感資料一起使用？

否。 使用 `Math.random()` 的數字不會用於遮蔽、傳送或接收任何敏感資料。 傳送給 Adobe 資料收集伺服器的資料仰賴基本 HTTPS 連線的安全性。 <!-- AN-173590 -->

AppMeasurement 會在三個主要方面使用 `Math.random()`：

* **取樣**：根據您的實作，可能只會針對您網站的一小部分訪客收集某些資訊。 `Math.random()` 是用來判斷特定訪客是否應該傳送資料。 大多數實作不使用取樣。
* **遞補訪客 ID**：如果無法從 Cookie 中擷取訪客 ID，則會產生隨機訪客 ID。 這部分的 AppMeasurement 會使用兩個 `Math.random()` 呼叫。
* **防止快取**：將一個隨機數字新增到影像要求 URL 的結尾，以防止瀏覽器快取。
