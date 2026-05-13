---
title: cookieDomain
description: （已淘汰）協助判斷要設定Cookie的網域。
feature: Appmeasurement Implementation
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
TQID: https://experienceleague.adobe.com/z6occeGLpxezOj7go2DrwG-j-fc9yBuGyHSmZJK9RfQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 77%

---

# cookieDomain

>[!IMPORTANT]
>此變數已淘汰。 請改用 [`trackingServer`](trackingserver.md)。

`cookieDomain` 變數決定了 AppMeasurement 在哪個網域設定 Cookie。 您可以使用此變數來明確設定 Cookie 網域，而非使用 [`cookieDomainPeriods`](cookiedomainperiods.md) 變數。

只有在同時符合下列&#x200B;**兩個**&#x200B;條件時，才需要使用此變數：

* 如果您的實施使用第一方 Cookie。 若實施使用包含 `sc.adobedc.net` 的 [`trackingServer`](trackingserver.md) 值，則不需要此變數。
* 如果您的網域尾碼含有句號。 例如，`example.co.uk` 可以使用 `cookieDomain` 變數明確指出 Cookie 網域為 `example.co.uk` 而非 `co.uk`。

只有少數實施需要用到 `cookieDomain` 變數，即使發生此情況，也可改用 [`cookieDomainPeriods`](cookiedomainperiods.md) 這類變數替代。

## 使用網頁SDK的Cookie網域

若無此變數，Web SDK便可決定正確的Cookie儲存網域。

## 使用Adobe Analytics擴充功能的Cookie網域

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.cookieDomain

`cookieDomain` 變數為字串，設為您要儲存 Cookie 的網域。

```js
s.cookieDomain = "stats.example.com";
```
