---
title: trackExternalLinks
description: 啟用或停用退出連結的自動連結追蹤。
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---

# trackExternalLinks

Adobe 提供追蹤對外連結的功能，使用者不需要手動設定每個退出連結的 [`tl()`](../functions/tl-method.md) 方法。如果您想要使用退出連結的自動連結追蹤功能，請啟用此變數。

啟用後，AppMeasurement 會將任何點按的連結 URL 與 [`linkInternalFilters`](linkinternalfilters.md) 和 [`linkExternalFilters`](linkexternalfilters.md) 中的值比較。如果有相符項目，退出連結追蹤呼叫就會自動引發。

## Adobe Experience Platform Launch 中的追蹤對外連結

「追蹤對外連結」是在設定 Adobe Analytics 擴充功能時，於[!UICONTROL 「連結追蹤」]設定追蹤器下方的核取方塊。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]設定追蹤器，如此可顯示[!UICONTROL 「追蹤對外連結」]核取方塊。

按一下核取方塊以啟用自動退出連結追蹤。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.trackExternalLinks

`s.trackExternalLinks` 是布林值，可啟用或停用自動退出連結追蹤。如果您不想追蹤對外連結，或想要手動呼叫 `tl()` 方法來追蹤退出連結，請將此變數設為 `false`。

```js
s.trackExternalLinks = true;
```
