---
title: 交易 ID 資料來源
description: 了解使用交易 ID 資料來源的一般工作流程。
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 4497ca252c4ee05175141e58d784ca2df215cb94
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 45%

---

# 交易 ID 資料來源

交易 ID 資料來源不僅可讓您並排檢視線上和離線資料，還可將資料關聯在一起。若要使用此功能，請在 Analytics 實作中使用 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 變數。

當您傳送包含 `transactionID` 值的線上點擊時，Adobe 會對當時所有已設定或持續存在的變數拍攝「快照」。如果找到透過 Data Sources 上傳的相符交易 ID，離線和線上資料就會繫結在一起。

若要使用交易，必須先傳送具有交易ID的線上點擊，然後再傳送具有該交易ID的任何交易資料來源資料至該交易ID。 線上點擊包含的變數（eVar等），但不包含隨交易ID資訊儲存的線上點擊上的事件。

傳入交易資料來源點擊時，資料來源交易點擊上的交易ID會查找變數等。 與原始線上點擊相關聯的（非事件）。 如果資料來源交易點擊上沒有傳入變數的值，則會在資料來源交易點擊上使用這些變數。

## 範例

如果傳入具有交易ID 1256的線上點擊，並在其上`evar1=blue`、`evar2=water`和`event1`設定，則交易ID 1256的交易資料將以`evar1=blue`、`evar2=water`保存。 不會將任何事件值儲存為交易資訊的一部分。

現在，假設接著資料源事務點擊傳入系統，並設定了事務ID 1256和`evar1=yellow`、`evar3=mountain`和`event2`。 系統會找到儲存的交易資料，並在資料源交易點擊集`evar2=water`中（因為這是原始點擊上設定的）。 它未設定`evar1=blue`（如同在原始點擊上），因為資料來源交易點擊上已設定`evar1`（黃色）的值。  因此，資料源事務點擊會導致`evar1=yellow`、`evar2=water`（來自原始線上點擊）和`evar3=mountain`。 這3個eVar值已設定`event2` — 來自資料來源交易點擊的事件。

處理資料來源交易點擊時，系統不會設定資料來源交易點擊的值`event1`。

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
