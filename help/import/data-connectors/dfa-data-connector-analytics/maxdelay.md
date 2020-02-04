---
title: maxDelay
description: 確定AppMeasurement在傳送影像要求前等待DFA回應的最長時間。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# maxDelay

The `s.maxDelay` variable is used in the DFA data connector to determine the timeout period in contacting the DFA host. 如果Adobe未在此變數中設定的指定期間內收到DFA伺服器的回應，連線即會中斷，資料會正常處理。 如果您擔心DFA在每個頁面上的回應時間，請在您的實作中加入此變數。 Adobe建議您嘗試使用此值，以判斷最佳逾時期。

此變數僅用於使用DFA資料連接器的實作。 即使是使用DFA的實作，此變數也是選用的。

## Adobe Experience Platform Launch的最大延遲

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.maxDelay

變 `s.maxDelay` 數是一個整數，代表AppMeasurement等待DFA回應的毫秒數。 如果AppMeasurement未及時收到DFA的回應，則會在沒有DFA資料的情況下將影像要求傳送至Adobe。

```js
s.maxDelay = 750;
```

## 屬性

* 增加等待時間可以收集到較多 DFA 資料，但也會提高 Analytics 點擊資料的遺失風險。Losing Analytics hit data happens when the user navigates away from the page during the `s.maxDelay` period.
* 縮短等待時間可降低遺失Analytics點擊資料的風險，但可降低隨點擊資料傳送的DFA資料量。
* Losing DFA integration data happens when the `s.maxDelay` period does not accommodate enough time for the DFA host to respond.

> [!NOTE]Adobe 無法控制 DFA 的回應時間。如果您在將最大延遲期提高至合理的時間範圍後仍發現一致的問題，請洽詢您組織的DFA帳戶管理員。
