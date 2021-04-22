---
title: writeSecureCookies
description: 允許 AppMeasurement 以 Secure 屬性設定 Cookie。
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '200'
ht-degree: 100%

---

# writeSecureCookies

`writeSecureCookies` 變數可讓 AppMeasurement 為 Analytics 設定 [Secure Cookie](https://en.wikipedia.org/wiki/Secure_cookie)。此設定會套用至 AppMeasurement 設定的訪客 ID Cookie，以及您使用 `Util.CookieWrite()` 方法設定的 Cookie。它需要 AppMeasurement 2.18.0 或更新版本。

>[!IMPORTANT]
>
> 如果您啟用 `writeSecureCookies` 變數，請確認網站上的所有內容都是安全地透過 HTTPS 提供。如果啟用此變數，而您的頁面上有不安全的內容，AppMeasurement 就不會運作。

## 在 Adobe Experience Platform Launch 中撰寫 Secure Cookie

「[!UICONTROL 撰寫 Secure Cookie]」是設定 Adobe Analytics 擴充功能時，在 [!UICONTROL Cookies] 摺疊式功能表底下的勾選方塊。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開 [!UICONTROL Cookies] 摺疊式功能表，會顯示 [!UICONTROL 撰寫 Secure Cookie] 勾選方塊。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.writeSecureCookies

`s.writeSecureCookies` 變數是布林值，可判斷 AppMeasurement 在建立 Cookie 時是否設定 Secure 屬性。其預設值為 `false`。如果您網站上的所有內容都安全，且您希望 AppMeasurement 設定的 Cookie 有 Secure 屬性，請將此變數設為 `true`。

```js
s.writeSecureCookies = true;
```
