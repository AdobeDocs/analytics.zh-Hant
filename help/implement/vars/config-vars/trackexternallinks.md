---
title: trackExternalLinks
description: 啟用或停用退出連結的自動連結追蹤。
translation-type: tm+mt
source-git-commit: 94218548dc4e3efd57df95c992003e94640e4330

---


# trackExternalLinks

Adobe offers the ability to track outbound links without manually setting the [`tl()`](../functions/tl-method.md) method for each exit link. 如果您想要使用退出連結的自動連結追蹤功能，請啟用此變數。

啟用後，AppMeasurement 會將任何點按的連結 URL 與 [`linkInternalFilters`](linkinternalfilters.md) 和 [`linkExternalFilters`](linkexternalfilters.md) 中的值比較。如果有相符項目，退出連結追蹤呼叫就會自動引發。

## Adobe Experience Platform Launch 中的追蹤對外連結

「追蹤對外連結」是在設定 Adobe Analytics 擴充功能時，於[!UICONTROL 「連結追蹤」]設定追蹤器下方的核取方塊。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]設定追蹤器，如此可顯示[!UICONTROL 「追蹤對外連結」]核取方塊。

按一下核取方塊以啟用自動退出連結追蹤。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.trackExternalLinks

`s.trackExternalLinks` 是布林值，可啟用或停用自動退出連結追蹤。If you do not want to track outbound links, or would prefer to manually call the `tl()` method to track exit links, set this variable to `false`.

```js
s.trackExternalLinks = true;
```
