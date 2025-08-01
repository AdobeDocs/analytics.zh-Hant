---
title: charSet
description: charSet 變數決定了 Adobe 用來剖析影像要求的編碼。
feature: Appmeasurement Implementation
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 65%

---

# charSet

Adobe使用`charSet`變數將傳入的資料轉換為UTF-8，以便Analytics儲存和執行報表。 大多數網站不需要設定此變數。

只有在報告中看到亂碼值 ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) 時，才設定此變數。如果您的網站在不同頁面上使用不同的編碼，您可以逐頁設定此變數。

## 網頁SDK中的字元集

Web SDK目前僅支援UTF-8，不提供變更編碼的選項。

## Adobe Analytics擴充功能中的字元集

「字元集」是在Adobe Experience Platform Data Collection中設定Adobe Analytics擴充功能時，位於「[!UICONTROL 一般]」摺疊式功能表下方的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開[!UICONTROL 一般]摺疊式功能表，便會顯示[!UICONTROL 字元集]欄位。

您可使用預設字元集或自訂字元集。避免變更 `UTF-8` 的數值，除非在報告中看到亂碼值。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.charSet

`charSet` 變數為字串。 如果您的 Adobe Analytics 中有亂碼值，請將此變數設定為與網站上的 `<meta charset="">` HTML 標記相同的數值。

```js
s.charSet = "UTF-8";
```
