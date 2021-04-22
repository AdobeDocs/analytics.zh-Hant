---
title: linkTrackVars
description: 指定要將哪些變數納入連結追蹤影像要求中。
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '271'
ht-degree: 100%

---

# linkTrackVars

有些實施不希望將所有變數納入每個連結追蹤影像要求中。請使用 `linkTrackVars` 和 [`linkTrackEvents`](linktrackevents.md) 變數，在 [`tl()`](../functions/tl-method.md) 呼叫中選擇性地納入維度和量度。

此變數不適用於頁面檢視呼叫 ([`t()`](../functions/t-method.md) 方法)。

## 使用 Adobe Experience Platform Launch 時連結追蹤呼叫中的變數

Launch 會根據介面中設定的變數在後端自動填入此變數，因此在使用 Launch 的實施中一律會設定。

>[!IMPORTANT]
>
>如果您使用自訂程式碼編輯器在 Launch 中設定變數，也必須使用自訂程式碼在 `linkTrackVars` 中納入變數。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.linkTrackVars

`s.linkTrackVars` 變數是字串，其中包含您要納入連結追蹤影像要求 (`tl()` 方法) 中的逗號分隔變數清單。若要在連結追蹤點擊中納入維度，以下兩個條件必須滿足：

* 設定所需的變數值。例如：`s.eVar1 = "Example value";`。
* 在 `linkTrackVars` 變數中設定所要的變數。例如：`s.linkTrackVars = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

此變數的預設值為空字串。不過，在「代碼管理器」內由 Adobe 提供的 AppMeasurement 程式碼中，此變數設為 `"None"`。有效值是任何填入維度的頁面層級變數。

* 如果此變數未定義或設為空字串，*所有*&#x200B;變數都會納入連結追蹤影像要求中。
* 如果此變數設為 `"None"`，*不會*&#x200B;有任何變數納入連結追蹤影像要求中。

>[!TIP]
>
>在此變數中指定變數時，請避免使用 Analytics 物件識別碼 (`s.`)。例如，`s.linkTrackVars = "eVar1";` 正確，而 `s.linkTrackVars = "s.eVar1";` 不正確。

## 範例

以下連結追蹤函數只會在傳送給 Adobe 的影像要求中納入 `eVar1` (不會納入 `eVar2`)：

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
