---
title: trackingServerSecure
description: 決定在 HTTPS 頁面上傳送影像要求的位置。
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 100%

---

# trackingServerSecure

Adobe 會接收訪客產生的影像要求，藉此收集您網站上的資料。`trackingServerSecure` 變數能決定透過 HTTPS 傳送影像要求的位置。它也能決定訪客 Cookie 的儲存位置。如果此變數未正確定義，您的實施可能會遭遇資料遺失。

>[!IMPORTANT]
>
>變更此值會導致 AppMeasurement 在不同位置尋找 Cookie。由於訪客 Cookie 會設定在新的位置，報表中的不重複訪客計數可能會暫時激增。

## Adobe Experience Platform Launch 中的 SSL 追蹤伺服器

[!UICONTROL 「SSL 追蹤伺服器」]是在設定 Adobe Analytics 擴充功能時，於[!UICONTROL 「一般」]設定追蹤器下方的欄位。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「一般」]設定追蹤器，如此可顯示[!UICONTROL 「SSL 追蹤伺服器」]欄位。

如果此欄位留空，其預設值為 [`trackingServer`](trackingserver.md) 變數中的值。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.trackingServerSecure

`s.trackingServerSecure` 變數是包含影像要求傳送位置的字串。它幾乎永遠是您網站的子網域。瀏覽器中的現代化隱私實務通常會使協力廠商 Cookie 變得不可靠。如果此變數留空，其會使用 `s.trackingServer` 變數中的值。

此變數的值幾乎永遠是第一方網域，例如 `data.example.com`。如需第一方 Cookie 處理的詳細資訊，請參閱「核心服務」使用指南中的 [Experience Cloud 中的第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=zh-Hant)。

最初設定第一方 Cookie 實施的個人，也會定義使用的網域和子網域。例如：

```js
s.trackingServerSecure = "data.example.com";
```

CNAME 記錄通常會指向 `data.adobedc.net`、`sc.adobedc.net` 或 `2o7.net` 上的子網域。
