---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# propN

屬性 (`prop`) 變數可用來建置流量模組內的自訂報表。


<!-- 

propN.xml

 -->

prop 變數可作為計數器 (用以計算頁面檢視的傳送次數)、用於路徑分析報表，或用於關聯報表中。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | c1 - c75 | 自訂流量 | "" |

**語法和可能的值**

```js
s.propN="value"
```

除了標準變數限制以外，[!UICONTROL 屬性]變數並無其他限制。

**範例**

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**組態設定**

請向 Adobe 客戶服務洽詢為 變數顯示「瀏覽」、「訪客」和`prop`「路徑」等度量的相關事宜。
