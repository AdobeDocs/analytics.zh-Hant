---
title: trackDownloadLinks
description: 啟用或停用下載連結的自動連結追蹤。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackDownLoadLinks

Adobe offers the ability to track download links without manually setting the [`tl()`](../functions/tl-method.md) method for each download link. 如果您想要使用下載連結的自動連結追蹤功能，請啟用此變數。

啟用後，AppMeasurement 會將任何點按的連結 URL 與 [`linkDownloadFileTypes`](linkdownloadfiletypes.md) 中的值比較。如果有相符項目，下載連結追蹤呼叫就會自動引發。

## Adobe Experience Platform Launch 中的追蹤下載連結

「追蹤下載連結」是在設定 Adobe Analytics 擴充功能時，於[!UICONTROL 「連結追蹤」]設定追蹤器下方的核取方塊。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]設定追蹤器，如此可顯示[!UICONTROL 「追蹤下載連結」]核取方塊。

按一下核取方塊以啟用自動下載連結追蹤。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.trackDownloadLinks

`s.trackDownloadLinks` 是布林值，可啟用或停用自動下載連結追蹤。If you do not want to track download links, or would prefer to manually call the `tl()` method to track downloads, set this variable to `false`.

```js
s.trackDownloadLinks = true;
```
