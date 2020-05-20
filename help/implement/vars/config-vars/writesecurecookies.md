---
title: writeSecureCookies
description: 允許 AppMeasurement 以 Secure 屬性設定 Cookie。
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# writeSecureCookies

`writeSecureCookies` 變數可讓 AppMeasurement 為 Analytics 設定 [Secure Cookie](https://en.wikipedia.org/wiki/Secure_cookie)。此設定會套用至 AppMeasurement 設定的訪客 ID Cookie，以及您使用 `Util.CookieWrite()` 方法設定的 Cookie。它需要 AppMeasurement 2.18.0 或更新版本。

>[!IMPORTANT] 如果您啟用 `writeSecureCookies` 變數，請確認網站上的所有內容都是安全地透過 HTTPS 提供。如果啟用此變數，而您的頁面上有不安全的內容，AppMeasurement 就不會運作。

## 在 Adobe Experience Platform Launch 中撰寫 Secure Cookie

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.writeSecureCookies

`s.writeSecureCookies` 變數是布林值，可判斷 AppMeasurement 在建立 Cookie 時是否設定 Secure 屬性。其預設值為 `false`。如果您網站上的所有內容都安全，且您希望 AppMeasurement 設定的 Cookie 有 Secure 屬性，請將此變數設為 `true`。

```js
s.writeSecureCookies = true;
```
