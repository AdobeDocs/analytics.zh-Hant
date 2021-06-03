---
title: 交易 ID 資料來源
description: 了解使用交易 ID 資料來源的一般工作流程。
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 1ee6a1e69a277f0d3c0ffd1defca0d4cb098cc6c
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 92%

---

# 交易 ID 資料來源

交易 ID 資料來源不僅可讓您並排檢視線上和離線資料，還可將資料關聯在一起。若要使用此功能，請在 Analytics 實作中使用 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 變數。

當您傳送包含 `transactionID` 值的線上點擊時，Adobe 會對當時所有已設定或持續存在的變數拍攝「快照」。如果找到透過 Data Sources 上傳的相符交易 ID，離線和線上資料就會繫結在一起。先看到哪個資料來源並不重要。

## 交易 ID 資料來源的整體工作流程

使用以下一般工作流程開始使用交易 ID 資料來源：

1. 建立資料來源 (「一般」類別和「一般資料來源 (交易 ID)」類型)。
1. 請依照資料來源設定精靈的指示取得FTP位置，以上傳資料和下載資料來源範本檔案。
1. 更新您的實作，加入 `transactionID` 變數。
1. 使用 `.fin` 檔案將資料來源檔案上傳至 FTP 站台。

## 上傳檔案和實作程式碼範例

如果您上傳以下資料來源檔案，並在站台上實作以下程式碼，報表中就會顯示連結的資料。資料來源檔案使用 eVar1 和 event1，線上實作則使用 eVar2 和 event2。由於交易 ID 相符，您可以看到 eVar1 的 event2 資料，以及 eVar2 的 event1 資料。

### 範例檔

下載範本、更新值，然後將其上傳至資料來源 FTP 位置：

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### 實作程式碼範例

如需交易 ID 的詳細說明，請參閱實作使用者指南中的 [`transactionID`](/help/implement/vars/page-vars/transactionid.md)。

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
