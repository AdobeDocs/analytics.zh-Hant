---
title: trackDownloadLinks
description: 啟用或停用下載連結的自動連結追蹤。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackDownLoadLinks

Adobe提供追蹤下載連結的功能，而不需手動設定每 [`tl()`](../functions/tl-method.md) 個下載連結的方法。 如果您想要使用下載連結的自動連結追蹤，請啟用此變數。

啟用後，AppMeasurement會將任何點按的連結URL與中的值進行比較 [`linkDownloadFileTypes`](linkdownloadfiletypes.md)。 如果有相符項目，則會自動觸發下載連結追蹤呼叫。

## 在Adobe Experience Platform Launch中追蹤下載連結

設定Adobe Analytics擴充功能時， [!UICONTROL Link Tracking] accordion下方會核取追蹤下載連結。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Extensions] ，然後按一下「Adobe Analytics [!UICONTROL Configure] 」下的按鈕。
4. 展開accordion [!UICONTROL Link Tracking] ，顯示核取方 [!UICONTROL Track download links] 塊。

按一下核取方塊以啟用自動下載連結追蹤。

## AppMeasurement和Launch自訂代碼編輯器中的s.trackDownloadLinks

此為 `s.trackDownloadLinks` 布林值，可啟用或停用自動下載連結追蹤。 如果您不想追蹤下載連結，或想要手動呼叫方法來追蹤 `tl()` 下載，請將此變數設為 `false`。

```js
s.trackDownloadLinks = true;
```
