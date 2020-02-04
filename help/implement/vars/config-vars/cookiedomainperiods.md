---
title: cookieDomainPeriods
description: 如果您的網域的字尾有句號，AppMeasurement會瞭解儲存Cookie的網域。
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# cookieDomainPeriods

AppMeasurement會查看網域和網域尾碼，以決定其Cookie位置。 對於類似網 `example.com`域，AppMeasurement會將Cookie設定在正確的位置。 不過，對於其他網域(如 `example.co.uk`此),AppMeasurement可能會錯誤地在上設定Cookie `co.uk`。 大部分的瀏覽器會拒絕在此無效網域上設定的Cookie，造成訪客識別問題。

此變 `cookieDomainPeriods` 數可協助AppMeasurement判斷Analytics cookie的設定位置，方法是呼叫網域字尾加上一個句號。 此變數可讓AppMeasurement在網域字尾中容納額外的句點，並在正確的位置設定Cookie。

* 對於或 `example.com` 等網 `www.example.com`域，此變數不需要設定。 如有需要，您可將此變數設為 `"2"`。
* 對於或等網 `example.co.uk` 域， `www.example.co.jp`請將此變數設為 `"3"`。

> [!IMPORTANT] 請勿將此變數納入子網域。 例如，請勿在範例 `cookieDomainPeriods` URL上設定 `store.toys.example.com`。 AppMeasurement依預設會辨識Cookie應儲存在 `example.com`上，即使在具有許多子網域的URL上亦然。

## Adobe Experience Platform Launch中的網域句點

「網域句點」是設定Adobe Analytics [!UICONTROL 擴充功能時] ,Cookies accordion下方的欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開 [!UICONTROL Cookies accordion] ，此欄位會顯 [!UICONTROL 示網域句點] 。

將此欄位設 `3` 為僅在尾碼中包含句點的網域上。 否則，此欄位可保留為空白。

## AppMeasurement和啟動自訂代碼編輯器中的s.cookieDomainPeriods

變 `cookieDomainPeriods` 數是一個字串，通常設為， `"3"`僅限在其尾碼中包含句號的網域。 其預設值為 `"2"`，可容納大部分網域。

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
