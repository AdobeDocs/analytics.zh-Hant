---
title: dynamicVariablePrefix
description: 可讓您自訂用來辨識動態變數的字串。
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '211'
ht-degree: 100%

---

# dynamicVariablePrefix

動態變數是一種速記概念，可讓您將某個變數的值複製到另一個變數。它們有助於縮短影像要求的 URL 長度，因此對於較長的變數值非常有用。如需此概念的詳細資訊，請參閱[動態變數](../page-vars/dynamic-variables.md)。

依預設，動態變數會使用 `D=` 首碼。`dynamicVariablePrefix` 變數可讓您自訂用來辨識動態變數的字串。它會區分大小寫。

## 使用 Adobe Experience Platform 中的標記的動態變數首碼

「動態變數首碼」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL 全域變數]」摺疊式功能表下方的欄位。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「全域變數」]摺疊式功能表，如此可顯示[!UICONTROL 「動態變數首碼」]欄位。

依預設，此欄位包含 `D=`。如果您想使用不同的動態變數首碼，可以變更值。只要值與網站上的字元編碼相符，您就可以使用任何想要的值。

## AppMeasurement 和自訂程式碼編輯器中的 s.dynamicVariablePrefix

`s.dynamicVariablePrefix` 變數是可包含任何字元順序的字串。如果此變數未定義，AppMeasurement 預設會使用 `D=` 字串。

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
