---
title: linkTrackVars
description: 指定要包含在連結追蹤影像要求中的變數。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkTrackVars

有些實作不想將所有變數納入所有連結追蹤影像要求。 使用和 `linkTrackVars` 變數 [`linkTrackEvents`](linktrackevents.md) ，在呼叫中選擇性地包含維度和 [`tl()`](../functions/tl-method.md) 量度。

此變數不用於頁面檢視呼叫(`t()` 方法)。

## 使用Adobe Experience Platform Launch進行連結追蹤呼叫的變數

Launch會根據介面中設定的變數，自動在後端填入此變數，因此一律會在使用Launch的實作中設定。

> [!IMPORTANT] 如果您使用自訂程式碼編輯器在Launch中設定變數，則也必須在使用自訂程式碼時 `linkTrackVars` 加入變數。

## AppMeasurement和Launch自訂代碼編輯器中的s.linkTrackVars

變 `s.linkTrackVars` 數是一個字串，包含您要納入連結追蹤影像要求（方法）的逗號分隔變`tl()` 數清單。 必須符合下列兩個標準，才能在連結追蹤點擊中包含維度：

* 設定所需的變數值。 例如, `s.eVar1 = "Example value";`。
* 在變數中設定所需的 `linkTrackVars` 變數。 例如, `s.linkTrackEvents = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

此變數的預設值為空字串。 不過，Adobe在「代碼管理員」中提供AppMeasurement代碼，此變數設為 `"None"`。 有效值是任何填入維度的頁面層級變數。

* 如果此變數未定義或設為空字串，則所有變 *數都會包含* 在連結追蹤影像要求中。
* 如果此變數設為 `"None"`, *連結追蹤影像請求中不* 會包含任何變數。

> [!TIP] 在此變數中指定變數時，請`s.`避免使用Analytics物件識別碼()。 例如， `s.linkTrackVars = "eVar1";` 正確，但 `s.linkTrackVars = "s.eVar1";` 不正確。

## 範例

下列連結追蹤功能僅包含 `eVar1` (非 `eVar2`)傳送至Adobe的影像要求：

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
