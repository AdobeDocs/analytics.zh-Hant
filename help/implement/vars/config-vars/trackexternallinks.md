---
title: trackExternalLinks
description: 啟用或停用退出連結的自動連結追蹤。
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackExternalLinks

Adobe提供追蹤出站連結的功能，而不需手動設定每 `tl()` 個退出連結的函式。 如果您想要對退出連結使用自動連結追蹤，請啟用此變數。

啟用後，AppMeasurement會將任何點按的連結URL與和中的值 `linkInternalFilters` 進行比 `linkExternalFilters`較。 如果有相符項目，會自動觸發退出連結追蹤呼叫。

## 在Adobe Experience Platform Launch中追蹤對外連結

設定Adobe Analytics擴充功能時，「連結追蹤」 [!UICONTROL accordion下方的核取方塊] ，即可追蹤對外連結。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開「 [!UICONTROL 連結追蹤] 」accordion，顯示「追蹤 [!UICONTROL 出站連結」核取方塊] 。

按一下核取方塊以啟用自動退出連結追蹤。

## AppMeasurement和Launch自訂代碼編輯器中的s.trackExternalLinks

此為 `s.trackExternalLinks` 布林值，可啟用或停用自動退出連結追蹤。 如果您不想追蹤對外連結，或想要手動呼叫函式以追蹤 `tl()` 退出連結，請將此變數設為 `false`。

```js
s.trackDownloadLinks = true;
```
