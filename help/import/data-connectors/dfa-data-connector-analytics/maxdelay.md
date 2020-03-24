---
title: maxDelay
description: 決定 AppMeasurement 在傳送影像要求之前，等待 DFA 回應的時間上限。
translation-type: ht
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# maxDelay

`s.maxDelay` 變數用於 DFA Data Connector，用以決定聯絡 DFA 主機時的逾時期間。若 Adobe 未在此變數中設定的指定期間內接收到來自 DFA 伺服器的回應，連線即會中斷，而資料會正常處理。若您對 DFA 各頁面的回應時間有所顧慮，請在您的實施中包含此變數。Adobe 建議您先以此值進行測試，以找出最理想的逾時期間。

此變數僅用於使用 DFA Data Connector 的實施。即使是使用 DFA 的實施，此變數也是選用的。

## 在 Adobe Experience Platform Launch 中的最大延遲

Launch 中沒有專用欄位可使用此變數。依照 AppMeasurement 語法，使用自訂代碼編輯器。

## AppMeasurement 和 Launch 自訂代碼編輯器中的 s.maxDelay

`s.maxDelay` 變數是一個整數，代表 AppMeasurement 等待 DFA 回應的毫秒數。如果 AppMeasurement 未及時收到 DFA 的回應，則會在沒有 DFA 資料的情況下，將影像要求傳送至 Adobe。

```js
s.maxDelay = 750;
```

## 屬性

* 增加等待時間可以收集到較多 DFA 資料，但也會提高 Analytics 點擊資料的遺失風險。遺失 Analytics 點擊資料的情形，會在使用者於 `s.maxDelay` 期間離開頁面進行導覽時發生。
* 減少等待時間可降低 Analytics 點擊資料的遺失風險，但也可能減少隨點擊資料傳送的 DFA 資料量。
* 遺失 DFA 整合資料的情形，會在 `s.maxDelay` 期間無法容納足夠的時間讓 DFA 主機回應時發生。

> [!NOTE]Adobe 無法控制 DFA 的回應時間。若在最大延遲時段已提高至合理的時間長度後仍持續出現問題，請洽詢組織的 DFA 帳戶管理員。
