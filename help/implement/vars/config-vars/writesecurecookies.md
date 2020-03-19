---
title: writeSecureCookies
description: 允許AppMeasurement以「保全」屬性設定Cookie。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# writeSecureCookies

此變 `writeSecureCookies` 數可讓AppMeasurement設定 [Analytics的Secure Cookie](https://en.wikipedia.org/wiki/Secure_cookie) 。 此設定會套用至AppMeasurement所設定的訪客ID Cookie，以及您使用方法設定的 `Util.CookieWrite()` Cookie。 它需要AppMeasurement 2.18.0或更新版本。

> [!IMPORTANT] 如果您啟用 `writeSecureCookies` 變數，請確定網站上的所有內容都是透過HTTPS安全提供。 如果此變數已啟用，而您的頁面上有不安全的內容，AppMeasurement將無法運作。

## 在Adobe Experience Platform Launch中編寫安全Cookie

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.writeSecureCookie

此變 `s.writeSecureCookies` 數是布林值，可判斷AppMeasurement在建立Cookie時是否設定「保全」屬性。 Its default value is `false`. 若您網站上的 `true` 所有內容都是安全的，且您希望AppMeasurement設定的Cookie具有「安全」屬性，請將此變數設為。

```js
s.writeSecureCookies = true;
```
