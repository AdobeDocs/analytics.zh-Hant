---
title: fpcookieDomainPeriods
description: 如果您的網域尾碼有句號，AppMeasurement 便可瞭解要儲存 Cookie 的網域。
feature: Appmeasurement Implementation
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 86%

---

# fpCookieDomainPeriods

`fpCookieDomainPeriods` 變數可協助 AppMeasurement 判斷 Analytics Cookie 的設定位置，方法是對外呼叫網域尾碼有一個額外的句號。此變數可讓 AppMeasurement 在網域尾碼中容納額外的句號，並在正確的位置設定 Cookie。它會繼承 [`cookieDomainPeriods`](cookiedomainperiods.md) 的值，但若您使用第一方 Cookie 實施，設定仍是最佳作法。

* 針對 `example.com` 或 `www.example.com` 這類網域，不需要設定此變數。如有需要，您可將此變數設為 `"2"`。
* 針對 `example.co.uk` 或 `www.example.co.jp` 這類網域，請將此變數設為 `"3"`。

>[!IMPORTANT]
>
> 使用此變數時請勿將子網域列入考量。例如，請勿在範例 URL `store.toys.example.com` 上設定 `fpCookieDomainPeriods`。依預設，AppMeasurement 會辨識 Cookie 應儲存在 `example.com` 上，即使在具有許多子網域的 URL 上亦然。

## 使用網頁SDK的第一方網域週期

若無此變數，Web SDK便可決定正確的Cookie儲存網域。

## 使用Adobe Analytics擴充功能的第一方網域週期

「第一方網域週期」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL Cookie]」摺疊式功能表下方的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「Cookie」]摺疊式功能表，如此可顯示[!UICONTROL 「第一方網域週期」]欄位。

僅針對尾碼中包含句號的網域將此欄位設為 `3`。其他網域可將此欄位保留空白。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.fpCookieDomainPeriods

`fpCookieDomainPeriods` 變數為字串，通常僅針對尾碼中包含句號的網域設為 `"3"`。其預設值為 `"2"`，適用於大部分網域。

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
