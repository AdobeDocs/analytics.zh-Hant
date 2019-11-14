---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# propN

屬性 ([!UICONTROL prop]) 變數可用來建置[!UICONTROL 流量模組]內的自訂報表。

<!-- 

propN.xml

 -->

prop 變數可作為計數器 (用以計算頁面檢視的傳送次數)、用於路徑分析報表，或用於關聯報表中。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | c1 - c75 | 自訂流量 | "" |

**語法和可能的值** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

除了標準變數限制以外，[!UICONTROL 屬性]變數並無其他限制。

**範例** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**組態設定** {#section_25FDEB6ECA8242A2A44EE540C083078A}

請向 Adobe 客戶服務洽詢為 [!UICONTROL prop] 變數顯示[!UICONTROL 「瀏覽」]、[!UICONTROL 「訪客」]和[!UICONTROL 「路徑」]等度量的相關事宜。
