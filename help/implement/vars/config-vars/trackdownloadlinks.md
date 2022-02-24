---
title: trackDownloadLinks
description: 啟用或停用下載連結的自動連結追蹤。
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '187'
ht-degree: 100%

---

# trackDownLoadLinks

Adobe 提供追蹤下載連結功能，使用者不需要手動設定每個下載連結的 [`tl()`](../functions/tl-method.md) 方法。如果您想要使用下載連結的自動連結追蹤功能，請啟用此變數。

啟用後，AppMeasurement 會將任何點按的連結 URL 與 [`linkDownloadFileTypes`](linkdownloadfiletypes.md) 中的值比較。如果有相符項目，下載連結追蹤呼叫就會自動引發。

## 使用 Adobe Experience Platform 中的標記追蹤下載連結

「追蹤下載連結」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL 連結追蹤]」摺疊式功能表下方的勾選方塊。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]摺疊式功能表，如此可顯示[!UICONTROL 「追蹤下載連結」]勾選方塊。

按一下勾選方塊以啟用自動下載連結追蹤。

## AppMeasurement 和自訂程式碼編輯器中的 s.trackDownloadLinks

`s.trackDownloadLinks` 是指示啟用或停用自動下載連結追蹤的布林值。 如果您不想追蹤下載連結，或想要手動呼叫 `tl()` 方法來追蹤下載內容，請將此變數設為 `false`。

```js
s.trackDownloadLinks = true;
```
