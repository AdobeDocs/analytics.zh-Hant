---
title: cookieDomain
description: cookieDomain 變數可協助判斷要設定 Cookie 的網域。
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '175'
ht-degree: 100%

---

# cookieDomain

>[!IMPORTANT]
>
>此變數已淘汰。請改用 [`trackingServer`](trackingserver.md)。

`cookieDomain` 變數決定了 AppMeasurement 在哪個網域設定 Cookie。您可以使用此變數來明確設定 Cookie 網域，而非使用 [`cookieDomainPeriods`](cookiedomainperiods.md) 變數。

只有在同時符合下列&#x200B;**兩個**&#x200B;條件時，才需要使用此變數：

* 如果您的實施使用第一方 Cookie。若實施使用包含 `sc.adobedc.net` 的 [`trackingServer`](trackingserver.md) 值，則不需要此變數。
* 如果您的網域尾碼含有句號。例如，`example.co.uk` 可以使用 `cookieDomain` 變數明確指出 Cookie 網域為 `example.co.uk` 而非 `co.uk`。

只有少數實施需要用到 `cookieDomain` 變數，即使發生此情況，也可改用 [`cookieDomainPeriods`](cookiedomainperiods.md) 這類變數替代。

## Adobe Experience Platform Launch 中的 Cookie 網域

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.cookieDomain

`cookieDomain` 變數為字串，設為您要儲存 Cookie 的網域。

```js
s.cookieDomain = "stats.example.com";
```
