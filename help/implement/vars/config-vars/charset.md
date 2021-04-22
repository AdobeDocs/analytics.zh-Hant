---
title: charSet
description: charSet 變數決定了 Adobe 用來剖析影像要求的編碼。
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '196'
ht-degree: 100%

---

# charSet

Adobe 會使用 charSet 變數將傳入的資料轉換為 UTF-8，以便供 Analytics 儲存和列入報表。大多數網站不需要設定此變數。

只有在報告中看到亂碼值 ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) 時，才設定此變數。如果您的網站在不同頁面上使用不同的編碼，您可以逐頁設定此變數。

## Adobe Experience Platform Launch 中的字元集

「字元集」是設定 Adobe Analytics 擴充功能時[!UICONTROL 一般]摺疊式功能表底下的欄位。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 一般]摺疊式功能表，便會顯示[!UICONTROL 字元集]欄位。

您可使用預設字元集或自訂字元集。避免變更 `UTF-8` 的數值，除非在報告中看到亂碼值。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.charSet

`charSet` 變數為字串。如果您的 Adobe Analytics 中有亂碼值，請將此變數設定為與網站上的 `<meta charset="">` HTML 標籤相同的數值。

```js
s.charSet = "UTF-8";
```
