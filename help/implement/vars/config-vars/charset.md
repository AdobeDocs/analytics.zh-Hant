---
title: charSet
description: charSet 變數決定了 Adobe 用來剖析影像要求的編碼。
translation-type: ht
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

Adobe 會使用 charSet 變數將傳入的資料轉換為 UTF-8，以便供 Analytics 儲存和列入報表。如果您的網站使用 UTF-8 以外的 charSet，此變數可讓 Adobe 正確編碼您的資料。如果您的網站在不同頁面上使用不同的編碼，可逐頁設定此變數。

## Adobe Experience Platform Launch 中的字元集

「字元集」是設定 Adobe Analytics 擴充功能時[!UICONTROL 一般]摺疊式功能表底下的欄位。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 一般]摺疊式功能表，便會顯示[!UICONTROL 字元集]欄位。

您可使用預設字元集或自訂字元集。此值應與您網站上的字元編碼相符。大部分網站都使用 `UTF-8`。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.charSet

`charSet` 變數為字串。將此變數設為與網站上的 `<meta charset="">` HTML 標籤相同的值。

```js
s.charSet = "UTF-8";
```
