---
title: cookieDomainPeriods
description: 如果您的網域的字尾有句號，AppMeasurement會瞭解儲存Cookie的網域。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# fpCookieDomainPeriods

此變 `fpCookieDomainPeriods` 數可協助AppMeasurement判斷Analytics Cookie的設定位置，方法是呼叫網域字尾加上一個句號。 此變數可讓AppMeasurement在網域字尾中容納額外的句點，並在正確的位置設定Cookie。 它會繼承的值 [`cookieDomainPeriods`](cookiedomainperiods.md)，但若您使用第一方Cookie實作，仍是您設定的最佳實務。

* 對於或 `example.com` 等網 `www.example.com`域，此變數不需要設定。 如有需要，您可將此變數設為 `"2"`。
* 對於或等網 `example.co.uk` 域， `www.example.co.jp`請將此變數設為 `"3"`。

> [!IMPORTANT] 請勿將此變數納入子網域。 例如，請勿在範例 `fpCookieDomainPeriods` URL上設定 `store.toys.example.com`。 AppMeasurement依預設會辨識Cookie應儲存在 `example.com`上，即使在具有許多子網域的URL上亦然。

## Adobe Experience Platform Launch中的第一方網域句點

第一方網域句號是設定Adobe Analytics擴充功能 [!UICONTROL Cookies] 時accordion下方的欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Extensions] ，然後按一下「Adobe Analytics [!UICONTROL Configure] 」下的按鈕。
4. 展開accordion [!UICONTROL Cookies] ，以顯示欄 [!UICONTROL First-party Domain Periods] 位。

將此欄位設 `3` 為僅在尾碼中包含句點的網域上。 否則，此欄位可保留為空白。

## AppMeasurement和啟動自訂代碼編輯器中的s.fpCookieDomainPeriods

變 `fpCookieDomainPeriods` 數是一個字串，通常設為， `"3"`僅限在其尾碼中包含句號的網域。 其預設值為 `"2"`，可容納大部分網域。

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
