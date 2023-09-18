---
title: Decodlinkparameters
description: 啟用或停用AppMeasurement雙重編碼連結追蹤變數。
exl-id: 7a4cea23-5ae6-4a8b-82a6-c68f9a1f9c49
feature: Variables
source-git-commit: 12d35a0f503ef79eabd55c169d9642c049542798
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 7%

---

# Decodlinkparameters

此 `decodeLinkParameters` 變數是布林值，可判斷連結追蹤變數是否會編碼一次(若設為 `true`)或兩次(若設為 `false`)。 它只會影響 `linkName` (屬於 [`tl()`](../functions/tl-method.md) 方法)和 [`linkURL`](linkurl.md). 它需要AppMeasurement v2.24.0或更高版本才能使用。 此變數的預設值為 `false`.

在v2.24.0之前的AppMeasurement版本中，連結追蹤變數一律會進行URL編碼兩次。 雖然這對通常仰賴單位元組字元的實作而言不是問題，但雙重編碼會導致報表中的多位元組字元編碼不正確。 將此變數設為 `true` 將連結追蹤值編碼一次，這通常是所需的行為。

* 如果您的實作使用多位元組字元，且連結追蹤變數經過URL解碼以位移AppMeasurement的雙重編碼，請將此變數設為 `false`. 此值會保留現有的AppMeasurement功能。
* 如果您的實施使用多位元組字元，而且您沒有URL解碼連結追蹤值，Adobe建議將此變數設為 `true`.
* 如果您的實施未使用多位元組字元，則不需要此變數。 不過，Adobe建議將此變數設為 `true` 在可能傳送多位元組字元的情況下。

## 使用Web SDK將連結引數雙重編碼

此變數專屬於AppMeasurement，且在任何型別的Web SDK實作中均不需要。

## 使用Adobe Analytics擴充功能將連結引數雙重編碼

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.decodeLinkParameters

此 `s.decodeLinkParameters` 變數是布林值，可判斷連結追蹤值是否會進行雙重編碼。 如果此變數未定義，其預設值為 `false` 以保留現有實作的功能。 Adobe建議將此值設為 `true` 適用於所有新的實作，尤其是當您在連結追蹤報表中看到URL編碼值時。

```js
s.decodeLinkParameters = true;
```
