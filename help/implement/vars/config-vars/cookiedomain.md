---
title: cookieDomain
description: cookieDomain變數可協助判斷要設定Cookie的網域。
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# cookieDomain

> [!IMPORTANT] 此變數已停用。 請改 `trackingServer` 用。

變 `cookieDomain` 數會決定AppMeasurement設定Cookie的網域。 您可以使用此變數來明確設定Cookie網域，而非使用變 `cookieDomainPeriods` 數。

只有在符合下列兩個條件 **時** ，才需要使用此變數：

* 如果您的實作使用第一方Cookie。 使用包含的值的實作不需要 `trackingServer` 此變數 `sc.omtrdc.net`。
* 如果您的網域的字尾有句號。 例如，可 `example.co.uk` 以使用變 `cookieDomain` 數明確指出Cookie網域為 `example.co.uk` 而非 `co.uk`。

只有少數實作可用於變數， `cookieDomain` 甚至可以改用替代變 `cookieDomainPeriods` 數，例如。

## Adobe Experience Platform Launch中的Cookie網域

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.cookieDomain

變 `cookieDomain` 數是字串，並設為您要儲存Cookie的網域。

```js
s.cookieDomain = "stats.example.com";
```
