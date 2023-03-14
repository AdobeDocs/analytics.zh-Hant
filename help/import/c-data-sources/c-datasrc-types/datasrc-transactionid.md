---
title: 交易 ID 資料來源
description: 了解使用交易 ID 資料來源的一般工作流程。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 100%

---

# 交易 ID 資料來源

交易 ID 資料來源不僅可讓您並排檢視線上和離線資料，還可將資料關聯在一起。若要使用此功能，請在 Analytics 實作中使用 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 變數。

當您傳送包含 `transactionID` 值的線上點擊時，Adobe 會對當時所有已設定或持續存在的變數拍攝「快照」。如果找到透過資料來源上傳的相符交易 ID，離線和線上資料就會繫結在一起。

在使用交易時，必須先傳入及處理具有交易 ID 的線上點擊，然後才能傳入具有該交易 ID 的任何交易資料來源資料。 唯一點擊包含變數 (eVar 等) 但不包含事件 (這些位在與交易 ID 資訊一起儲存的線上點擊)。

當傳入交易資料來源點擊時，資料來源交易點擊上的交易 ID 會尋找與包含該交易 ID 的原始線上點擊相關的變數等，而不是事件。 如果資料來源交易點擊上傳入的變數沒有值，它會使用資料來源交易點擊上的這些變數。

## 範例

如果傳入了具有交易 ID 1256 的線上點擊，並在其上設定了 `evar1=blue`、`evar2=water` 和 `event1`，則會儲存交易 ID 1256 的交易資料，但不包含 `evar1=blue`、`evar2=water`。 不會將任何事件值儲存為交易資訊的一部分。

現在，讓我們假設之後透過包含交易 ID 1256 且設定了 `evar1=yellow`、`evar3=mountain` 和 `event2` 的系統來傳遞資料來源交易點擊。 此系統會尋找儲存的交易資料，並在資料來源交易點擊中設定 `evar2=water` (因為這是在原始點擊上所設定的項目)。 它不會設定 `evar1=blue` (因為它位在原始點擊上) 因為已在資料來源交易點擊上設定的 `evar1` (黃色) 已經有值。 所以資料來源交易點擊結果會擁有 `evar1=yellow`、`evar2=water` (來自原始線上點擊) 和 `evar3=mountain`。 這 3 個 eVar 值已設定 `event2` - 來自資料來源交易點擊的事件。

在處理資料來源交易點擊時，資料來源交易點擊中不會有任何值設定 `event1`。

## 交易 ID 資料來源的整體工作流程

使用以下一般工作流程開始使用交易 ID 資料來源：

1. 建立資料來源 (「一般」類別和「一般資料來源 (交易 ID)」類型)。
1. 請依照資料摘要設定精靈的指示取得 FTP 位置，以上傳資料並下載資料來源範本檔案。
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
