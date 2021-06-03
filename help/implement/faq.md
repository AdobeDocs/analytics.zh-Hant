---
title: 實作常見問題集
description: 實施的相關常見問題，以及可提供更多資訊的連結。
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 71%

---

# Analytics 實施常見問題集

實施的相關常見問題，以及可提供更多資訊的連結。

## Experience Cloud 訪客 ID 與 Analytics 訪客 ID 有何不同？

Identity Service 會指派不重複的持續性識別碼，以便在 Experience Cloud 的其他解決方案之間共用。Analytics 訪客 ID 僅供 Analytics 使用。Adobe 建議您在實施中使用 Experience Cloud 訪客 ID 服務。

## 如何實施心率視訊追蹤？

請參閱[在 Adobe Analytics 測量音訊和視訊](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html)。

## Adobe 的服務中斷會影響效能嗎？

不可以。JavaScript 檔案並非由 Adobe 伺服器託管，所以 Adobe 中斷不會影響 AppMeasurement 程式庫。如果您使用 Adobe Experience Platform Launch，JavaScript 檔案會由 Akamai 託管，或於貴組織所決定的伺服器位置託管。

## 從瀏覽器傳送資料給 Adobe 服務會降低效能嗎？

AppMeasurement 會在 HTML 頁面內部建立影像物件，接著瀏覽器再向 Adobe 資料收集伺服器要求該影像物件。如果資料收集伺服器效能緩慢或無反應，處理該要求的執行緒會延遲，直到傳回影像或逾時。因為瀏覽器使用多個執行緒來處理影像，Adobe 中斷對頁面載入時間的影響極小，最多只會佔用一個執行緒，而其他執行緒仍持續運作。

## 如何使 Analytics 實作無效或加以移除？

有時組織會因為合約到期，或是需減少伺服器呼叫數而想要移除實作。

* **使用 Launch 的實作**：在[!UICONTROL 「擴充功能」]標籤中停用或解除安裝 Adobe Analytics 擴充功能，然後進行發佈。
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


## 我透過程式碼分析器執行AppMeasurement，並標示其使用`Math.random()`為潛在安全風險。 `Math.random()`是否用於任何敏感資料？

不可以，使用`Math.random()`的數字不用於掩碼、發送或接收任何敏感資料。 傳送至Adobe資料收集伺服器的資料需仰賴基礎HTTPS連線的安全性。<!-- AN-173590 -->

AppMeasurement在三個關鍵區域中使用`Math.random()` :

* **取樣**:根據您的實作，您只能為網站的一小部分訪客收集某些資訊。`Math.random()` 用來判斷特定訪客是否應該傳送資料。大部分實作都不使用取樣。
* **備援訪客ID**:如果無法從Cookie擷取訪客ID，則會產生隨機訪客ID。AppMeasurement的這部分會使用對`Math.random()`的兩個呼叫。
* **快取破壞**:影像要求URL的結尾會新增隨機數字，以協助防止瀏覽器快取。
