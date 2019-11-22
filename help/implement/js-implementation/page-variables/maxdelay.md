---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# maxDelay

s.maxDelay 變數主要用於 Genesis DFA 整合，用以決定聯繫 DFA 主機時的逾時期間。若 Adobe 未在 變數中設定的指定期間內接收到來自 DFA 伺服器的回應，連線即會中斷，而資料會正常處理。若您對 DFA 各頁面的回應時間有所顧慮，請實施此變數。建議您先以此值進行測試，以找出最理想的逾時期間。


<!-- 

maxDelay.xml

 -->

**實施範例**

```
s.maxDelay="750";
```

**屬性**

* 此變數是會透過網站上實施的 JavaScript 而填入的選用事件度量。
* 若 DFA 主機未在指定的時間內回應，指定給「逾時」的事件即會執行 (透過 Genesis 整合精靈指派)。
* 此變數只能包含數值。
* 指定的時間長度以毫秒為單位。
* 增加等待時間可以收集到較多 DFA 資料，但也會提高 Analytics 點擊資料的遺失風險。

   遺失 Analytics 點擊資料的情形，會在使用者於 *`s.maxDelay`* 期間離開頁面進行導覽時發生。

* 減少等待時間可降低 Analytics 點擊資料的遺失風險，但也可能減少隨點擊資料傳送的 DFA 資料量。

   遺失 DFA 整合資料的情形，會在 *`s.maxDelay`* 期間無法容納足夠的時間讓 DFA 主機回應時發生。

> [!NOTE]Adobe 無法控制 DFA 的回應時間。若在最大延遲時段已提高至合理的時間長度後仍持續出現問題，請洽詢組織的 DFA 帳戶管理員。
