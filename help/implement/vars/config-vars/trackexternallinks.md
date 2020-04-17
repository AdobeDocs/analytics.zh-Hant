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

Track outbound links is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展開accordion [!UICONTROL Link Tracking] ，顯示核取方 [!UICONTROL Track outbound links] 塊。

按一下核取方塊以啟用自動退出連結追蹤。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.trackExternalLinks

`s.trackExternalLinks` 是布林值，可啟用或停用自動退出連結追蹤。If you do not want to track outbound links, or would prefer to manually call the `tl()` method to track exit links, set this variable to `false`.

```js
s.trackExternalLinks = true;
```
