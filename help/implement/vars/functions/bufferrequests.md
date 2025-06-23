---
title: bufferRequests
description: 針對立即解除安裝頁面的瀏覽器，提高擷取連結追蹤要求的可靠性。
feature: Appmeasurement Implementation
exl-id: f103deb4-f449-4325-b1a0-23e58a3c9ba0
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 6%

---

# bufferRequests

`bufferRequests()`方法可讓您快取目前頁面上的影像要求，而非傳送至Adobe。 在瀏覽器不支援[`navigator.sendBeacon()`](https://developer.mozilla.org/zh-TW/docs/Web/API/Navigator/sendBeacon)或頁面解除安裝時取消影像要求的情況下，觸發此方法相當實用。 許多版本的WebKit瀏覽器（例如Safari）通常會在按一下連結時顯示停止影像要求的行為。 `bufferRequests()`方法適用於AppMeasurement v2.25.0或更新版本的所有版本。

當您在相同瀏覽器工作階段的後續頁面上呼叫[`t()`](t-method.md)或[`tl()`](tl-method.md)，且尚未在該頁面上呼叫`bufferRequests()`時，除了該頁面的影像要求之外，還會傳送所有緩衝要求。 緩衝要求會以正確順序傳送，而目前頁面的影像要求會於最後傳送。

>[!TIP]
>
>緩衝要求的時間戳記會與傳送資料的頁面共用。 如果您想要在記錄緩衝要求的確切秒數內達到更高的精確度，您可以在緩衝要求之前設定[`timestamp`](../page-vars/timestamp.md)頁面變數。 如果您使用此變數，請確定已啟用[可選時間戳記](/help/technotes/timestamps-optional.md) — 如果未啟用，所有時間戳記點選都會永久遺失！

## 限制

呼叫`bufferRequests()`方法時，請記住下列限制。 由於此方法使用[`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)，因此適用許多相同的限制：

* 目的地連結必須位於相同的網域和子網域上。 即使兩者具有相同的Adobe Analytics實施，緩衝的請求也不會跨網域或子網域運作。 此限制也表示您無法使用緩衝的請求來追蹤退出連結。
* 目的地連結必須使用與目前頁面相同的通訊協定。 您無法在HTTP與HTTPS之間傳送緩衝要求。
* 儲存緩衝的要求，直到您呼叫`t()`或`tl()`而未先呼叫`bufferRequests()`為止，或直到瀏覽器或索引標籤關閉為止。 如果瀏覽器工作階段在您傳送該資料至Adobe之前結束，未傳送的緩衝要求會永久遺失。
* 如果瀏覽器不支援[網頁儲存API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)或[JSON API](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)，則會輸出警告至瀏覽器主控台，而AppMeasurement會嘗試使用`t()`方法立即傳送影像要求。

## 網路SDK中的緩衝請求

Web SDK目前不提供緩衝要求的功能。

## 使用Adobe Analytics擴充功能的緩衝請求

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.bufferRequests()

呼叫`bufferRequests()`方法，然後再呼叫`t()`或`tl()`。 呼叫`bufferRequests()`時，後續追蹤呼叫會寫入工作階段存放區，而非傳送至Adobe資料收集伺服器。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Flag the request to be buffered
s.bufferRequests();

// The t() or tl() method then writes the data to session storage instead of sending it to Adobe
s.tl(true,"o","Example link click");

// On a subsequent page, the tracking call sends both the above link tracking call and the page view call
s.t();
```
