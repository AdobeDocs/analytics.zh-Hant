---
title: writeSecureCookies
description: 允許 AppMeasurement 以 Secure 屬性設定 Cookie。
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 72%

---

# writeSecureCookie

`writeSecureCookies` 變數可讓 AppMeasurement 為 Analytics 設定 [Secure Cookie](https://en.wikipedia.org/wiki/Secure_cookie)。此設定會套用至 AppMeasurement 設定的訪客 ID Cookie，以及您使用 `Util.CookieWrite()` 方法設定的 Cookie。它需要 AppMeasurement 2.18.0 或更新版本。

`writeSecureCookies` 僅適用於由 AppMeasurement JavaScript 設定的 Cookie (`s_fid`, `s_cc` 和 `s_sq`)。`https` 回應所設定的 Cookie (`s_vi` 和 `s_ecid`) 可透過聯絡 Adobe 客戶服務以設為「安全」。

在[此處](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html)進一步了解有關 Analytics Cookie。

>[!WARNING]
>
> 如果您啟用 `writeSecureCookies` 變數，請確認網站上的所有內容都是安全地透過 HTTPS 提供。如果已啟用此變數，並且您的頁面上有不安全的內容，則資料收集無法正常工作。

## 將安全Cookie與Web SDK一起使用

如果您的站點使用HTTPS協定，則Web SDK設定的所有Cookie都將設定「安全」屬性。

## 使用Adobe Analytics擴展寫入安全Cookie

「[!UICONTROL 撰寫 Secure Cookie]」是設定 Adobe Analytics 擴充功能時，在 [!UICONTROL Cookies] 摺疊式功能表底下的勾選方塊。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開 [!UICONTROL Cookies] 摺疊式功能表，會顯示 [!UICONTROL 撰寫 Secure Cookie] 勾選方塊。

## AppMeasurement中的s.writeSecureCookie和Analytics擴展自定義代碼編輯器

`s.writeSecureCookies` 變數是布林值，可判斷 AppMeasurement 在建立 Cookie 時是否設定 Secure 屬性。其預設值為 `false`。如果您網站上的所有內容都安全，且您希望 AppMeasurement 設定的 Cookie 有 Secure 屬性，請將此變數設為 `true`。

```js
s.writeSecureCookies = true;
```
