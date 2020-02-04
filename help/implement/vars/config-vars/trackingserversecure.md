---
title: trackingServerSecure
description: 確定在HTTPS頁面上傳送的位置影像要求。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServerSecure

Adobe會接收訪客產生的影像要求，以收集您網站上的資料。 變 `trackingServerSecure` 數會決定透過HTTPS傳送影像要求的位置。 它也會決定訪客Cookie的儲存位置。 如果此變數未正確定義，您的實作可能會遭遇資料遺失。

> [!IMPORTANT] 變更此值會讓AppMeasurement尋找不同位置的Cookie。 獨特訪客計數會隨著訪客Cookie設定在新位置，在報告中暫時尖峰。

## Adobe Experience Platform Launch中的SSL追蹤伺服器

[!UICONTROL SSL追蹤伺服器] 是設定Adobe Analytics擴充功能時，「 [!UICONTROL 一般] 」accordion下方的欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開「 [!UICONTROL 一般] 」accordion，以顯示 [!UICONTROL SSL追蹤伺服器欄位] 。

如果此欄位留空，則預設為變數中的 `trackingServer` 值。

## AppMeasurement中的s.trackingServerSecure和Launch自訂代碼編輯器

變 `s.trackingServerSecure` 數是包含傳送影像要求之位置的字串。 它幾乎永遠是您網站的子網域。 瀏覽器中的現代隱私權實務通常會使協力廠商Cookie不可靠。 如果此變數為空白，則會使用變數中的 `s.trackingServer` 值。

此變數的值幾乎一律為第一方網域，例如 `data.example.com`。 如需 [有關第一方Cookie程式的詳細資訊，請參閱核心服務使用指南中](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) 「Experience cloud中的第一方Cookie」。

最初設定第一方Cookie實作的個人也會定義使用的網域和子網域。 例如:

```js
s.trackingServerSecure = "data.example.com";
```

CNAME記錄通常指向上的子網域 `ssl.d1.sc.omtrdc.net`。
