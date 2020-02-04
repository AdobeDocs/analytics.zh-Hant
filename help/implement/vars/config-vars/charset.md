---
title: charSet
description: charSet變數可決定Adobe用來剖析影像要求的編碼。
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

Adobe會使用charSet變數將傳入的資料轉換為UTF-8，以便Analytics儲存和報告。 如果您的網站使用UTF-8以外的charSet，此變數可讓Adobe正確編碼您的資料。 如果您的網站在不同頁面上使用不同的編碼，則可逐頁設定此變數。

## Adobe Experience Platform Launch中的字元集

字元集是設定Adobe Analytics擴充功能時， [!UICONTROL 「一般] 」accordion下方的欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開「 [!UICONTROL 一般] 」accordion，以顯示「字 [!UICONTROL 符集」欄位] 。

您可以使用預設字元集或自訂字元集。 此值應符合您網站上的字元編碼。 大部分網站都使 `UTF-8`用。

## s.charSet在AppMeasurement和Launch自訂代碼編輯器中

變 `charSet` 數是字串。 將此變數設為與網站上的 `<meta charset="">` HTML標籤相同的值。

```js
s.charSet = "UTF-8";
```
