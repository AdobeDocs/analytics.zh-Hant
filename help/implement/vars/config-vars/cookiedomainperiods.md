---
title: cookieDomainPeriods
description: 如果您的網域尾碼有句號，AppMeasurement 便可瞭解要儲存 Cookie 的網域。
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 100%

---

# cookie域句點

AppMeasurement 會查看網域和網域尾碼來判斷其 Cookie 位置。針對類似 `example.com` 的網域，AppMeasurement 會將 Cookie 設定在正確的位置。不過，若為其他網域，以 `example.co.uk` 為例，AppMeasurement 可能會錯誤地在 `co.uk` 上設定 Cookie。大部分的瀏覽器會拒絕在此無效網域上設定的 Cookie，造成訪客識別問題。

`cookieDomainPeriods` 變數可協助 AppMeasurement 判斷 Analytics Cookie 的設定位置，方法是對外呼叫網域尾碼有一個額外的句號。此變數可讓 AppMeasurement 在網域尾碼中容納額外的句號，並在正確的位置設定 Cookie。

* 針對 `example.com` 或 `www.example.com` 這類網域，不需要設定此變數。如有需要，您可將此變數設為 `"2"`。
* 針對 `example.co.uk` 或 `www.example.co.jp` 這類網域，請將此變數設為 `"3"`。

>[!IMPORTANT]
>
> 使用此變數時請勿將子網域列入考量。例如，請勿在範例 URL `store.toys.example.com` 上設定 `cookieDomainPeriods`。依預設，AppMeasurement 會辨識 Cookie 應儲存在 `example.com` 上，即使在具有許多子網域的 URL 上亦然。

## 使用 Adobe Experience Platform 中的標記的網域週期

「網域週期」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL Cookie]」摺疊式功能表下方的欄位。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
1. 展開 [!UICONTROL Cookies] 摺疊式功能表，便會顯示[!UICONTROL 網域句號]欄位。

僅針對尾碼中包含句號的網域將此欄位設為 `3`。其他網域可將此欄位保留空白。

## AppMeasurement 和自訂程式碼編輯器中的 s.cookieDomainPeriods

`cookieDomainPeriods` 變數為字串，通常僅針對尾碼中包含句號的網域設為 `"3"`。其預設值為 `"2"`，適用於大部分網域。

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
