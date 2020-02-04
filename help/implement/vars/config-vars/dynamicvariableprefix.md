---
title: dynamicVariablePrefix
description: 可讓您自訂用以識別動態變數的字串。
translation-type: tm+mt
source-git-commit: 03a4c0d5e080219a7fd96dff33ce122669351ac3

---


# dynamicVariablePrefix

動態變數是可讓您將值從一個變數複製到另一個變數的速記概念。 它們對於長變數值非常有用，因為它們有助於縮短影像要求的URL長度。 如需 [此概念的詳細資訊](../page-vars/dynamic-variables.md) ，請參閱動態變數。

依預設，動態變數會使用首碼 `D=`。 變數 `dynamicVariablePrefix` 可讓您自訂識別動態變數的字串。 區分大小寫。

## Adobe Experience Platform Launch中的動態變數首碼

動態變數首碼是設定Adobe Analytics擴充功能時 [!UICONTROL 「全域變數] 」accordion下方的欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開全 [!UICONTROL 域變數] accordion，以顯示動 [!UICONTROL 態變數首碼欄位] 。

依預設，此欄 `D=` 位包含。 如果您想使用不同的動態變數首碼，可以變更值。 只要值與網站上的字元編碼相符，您就可以使用任何您想要的值。

## AppMeasurement和Launch自訂代碼編輯器中的s.dynamicVariablePrefix

變 `s.dynamicVariablePrefix` 數是可包含任何字元順序的字串。 如果未定義此變數，AppMeasurement預設會使 `D=` 用字串。

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
