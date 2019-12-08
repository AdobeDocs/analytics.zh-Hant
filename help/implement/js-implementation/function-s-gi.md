---
description: s_gi() 函數可用來建立或根據報表套裝 ID 尋找 AppMeasurement 例項。AppMeasurement 可在內部追蹤已建立的所有例項，而 s_gi() 會傳回報表套裝的現有例項 (若存在)。如果例項不存在，則會建立並傳回新的例項。
keywords: Analytics Implementation
title: s_gi() 函數
topic: Developer and implementation
uuid: a77de90e-c60e-4946-90cf-deaf8aa3d755
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# s_gi() 函數

s_gi() 函數可用來建立或根據報表套裝 ID 尋找 AppMeasurement 例項。AppMeasurement 可在內部追蹤已建立的所有例項，而 s_gi() 會傳回報表套裝的現有例項 (若存在)。如果例項不存在，則會建立並傳回新的例項。

建議您先在整個頁面程式碼中呼叫 `s_gi()`，然後再設定變數以及進行追蹤呼叫。如此可在不小心覆寫 s 變數時，確保使用正確的物件來進行追蹤呼叫。

## 使用多個報表套裝 {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

傳回的物件不一定，取決於所傳遞的報表套裝 ID。例如，如果您對 `s_gi()` () 進行下列初始呼叫:

```
var s=s_gi('rsid1,rsid2')
```

下表概述後續呼叫傳回的項目:

| **對 s_gi 的後續呼叫** | **傳回物件的說明** |
|---|---|
| `s=s_gi('rsid1,rsid2')` | 稍早參考的相同物件。 |
| `s=s_gi('rsid1')` | 稍早建立的物件複本，但不是原始物件。 |
| `s=s_gi('rsid1,rsid3')` | 稍早建立的物件複本，但不是原始物件。 |
| `s=s_gi('rsid3')` | 新的空白物件，未設定組態變數 (例如 linkTrackVars 空白，因為是 linkDownloadFileTypes)。 |
