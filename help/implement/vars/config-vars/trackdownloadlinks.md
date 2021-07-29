---
title: trackDownloadLinks
description: 啟用或停用下載連結的自動連結追蹤。
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 87%

---

# trackDownLoadLinks

Adobe 提供追蹤下載連結功能，使用者不需要手動設定每個下載連結的 [`tl()`](../functions/tl-method.md) 方法。如果您想要使用下載連結的自動連結追蹤功能，請啟用此變數。

啟用後，AppMeasurement 會將任何點按的連結 URL 與 [`linkDownloadFileTypes`](linkdownloadfiletypes.md) 中的值比較。如果有相符項目，下載連結追蹤呼叫就會自動引發。

## 在Adobe Experience Platform中使用標籤來追蹤下載連結

「追蹤下載連結」是在設定 Adobe Analytics 擴充功能時，於[!UICONTROL 「連結追蹤」]設定追蹤器下方的核取方塊。

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]設定追蹤器，如此可顯示[!UICONTROL 「追蹤下載連結」]核取方塊。

按一下核取方塊以啟用自動下載連結追蹤。

## AppMeasurement 和 自訂程式碼編輯器中的 s.trackDownloadLinks

`s.trackDownloadLinks` 是布林值，可啟用或停用自動下載連結追蹤。如果您不想追蹤下載連結，或想要手動呼叫 `tl()` 方法來追蹤下載內容，請將此變數設為 `false`。

```js
s.trackDownloadLinks = true;
```
