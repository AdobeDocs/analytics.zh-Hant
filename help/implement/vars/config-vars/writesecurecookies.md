---
title: writeSecureCookies
description: 允許 AppMeasurement 以 Secure 屬性設定 Cookie。
feature: Appmeasurement Implementation
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 76%

---

# writeSecureCookies

`writeSecureCookies` 變數可讓 AppMeasurement 為 Analytics 設定 [Secure Cookie](https://en.wikipedia.org/wiki/Secure_cookie)。此設定會套用至 AppMeasurement 設定的訪客 ID Cookie，以及您使用 `Util.CookieWrite()` 方法設定的 Cookie。它需要 AppMeasurement 2.18.0 或更新版本。

`writeSecureCookies` 僅適用於由 AppMeasurement JavaScript 設定的 Cookie (`s_fid`, `s_cc` 和 `s_sq`)。`https` 回應所設定的 Cookie (`s_vi` 和 `s_ecid`) 可透過聯絡 Adobe 客戶服務以設為「安全」。

在[此處](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html)進一步了解有關 Analytics Cookie。

>[!WARNING]
>
> 如果您啟用 `writeSecureCookies` 變數，請確認網站上的所有內容都是安全地透過 HTTPS 提供。如果啟用此變數，而且您的頁面上有不安全的內容，資料收集就無法正常運作。

## 搭配使用Secure Cookie與Web SDK

如果您的網站使用HTTPS通訊協定，則會為網頁SDK設定的所有Cookie設定Secure屬性。

## 使用Adobe Analytics擴充功能撰寫Secure Cookie

「[!UICONTROL 撰寫 Secure Cookie]」是設定 Adobe Analytics 擴充功能時，在 [!UICONTROL Cookies] 摺疊式功能表底下的勾選方塊。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開 [!UICONTROL Cookies] 摺疊式功能表，會顯示 [!UICONTROL 撰寫 Secure Cookie] 勾選方塊。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.writeSecureCookies

`s.writeSecureCookies` 變數是布林值，可判斷 AppMeasurement 在建立 Cookie 時是否設定 Secure 屬性。其預設值為 `false`。如果您網站上的所有內容都安全，且您希望 AppMeasurement 設定的 Cookie 有 Secure 屬性，請將此變數設為 `true`。

```js
s.writeSecureCookies = true;
```
