---
title: trackExternalLinks
description: 啟用或停用退出連結的自動連結追蹤。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackExternalLinks

Adobe提供追蹤出站連結的功能，而不需手動設定每 [`tl()`](../functions/tl-method.md) 個退出連結的方法。 如果您想要對退出連結使用自動連結追蹤，請啟用此變數。

啟用後，AppMeasurement會將任何點按的連結URL與和中的值 [`linkInternalFilters`](linkinternalfilters.md) 進行比 [`linkExternalFilters`](linkexternalfilters.md)較。 如果有相符項目，會自動觸發退出連結追蹤呼叫。

## 在Adobe Experience Platform Launch中追蹤對外連結

設定Adobe Analytics擴充功能時， [!UICONTROL Link Tracking] accordion下方的核取方塊會追蹤對外連結。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Extensions] ，然後按一下「Adobe Analytics [!UICONTROL Configure] 」下的按鈕。
4. 展開accordion [!UICONTROL Link Tracking] ，顯示核取方 [!UICONTROL Track outbound links] 塊。

按一下核取方塊以啟用自動退出連結追蹤。

## AppMeasurement和Launch自訂代碼編輯器中的s.trackExternalLinks

此為 `s.trackExternalLinks` 布林值，可啟用或停用自動退出連結追蹤。 如果您不想追蹤對外連結，或想要手動呼叫方法來追蹤 `tl()` 退出連結，請將此變數設為 `false`。

```js
s.trackDownloadLinks = true;
```
