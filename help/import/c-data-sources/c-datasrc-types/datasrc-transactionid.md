---
title: 交易ID資料來源
description: 瞭解使用交易ID資料來源的一般工作流程。
translation-type: tm+mt
source-git-commit: c54704bef49a2c3076caac6fe7dd3ec8d40596ef

---


# 交易ID資料來源

交易ID資料來源不僅可讓您並排檢視線上和離線資料，還可將資料連結在一起。 它需要在您的Analytics實作 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 中使用變數。

當您傳送包含值的線上點擊時， `transactionID` Adobe會對當時所有已設定或持續存在的變數進行「快照」。 如果找到透過Data Sources上傳的相符交易ID，則離線和線上資料會系結在一起。 首先看到哪個資料來源並不重要。

## 交易ID資料來源的整體工作流程

使用下列一般工作流程開始使用交易ID資料來源：

1. 建立資料來源(「一般」類別和「一般資料來源（交易ID）」類型)。
1. 依照資料饋送設定精靈的指示，取得FTP位置以上傳資料並下載資料來源範本檔案。
1. 更新您的實作以包含變 `transactionID` 數。
1. 使用檔案將資料來源檔案上傳至FTP `.fin` 網站。

## 上傳檔案與實作代碼範例

如果您上傳了下列資料來源檔案，並在您的網站上實作了下列程式碼，您會在報表中看到連結的資料。 資料來源檔案使用eVar1和event1，而線上實作則使用eVar2和event2。 由於交易ID符合，您可以看到eVar1的event2資料，以及eVar2的event1資料。

### 範例檔案

下載範本、更新值，然後將其上傳至資料來源的FTP位置：

| `# Generic Data Source (Transaction ID) template file (user: 0 ds_id: 1)` |  |  |  |
|---|---|---|---|
| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### 實作程式碼範例

如需交易ID的詳細說明，請參閱「實 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 作使用指南」。

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
