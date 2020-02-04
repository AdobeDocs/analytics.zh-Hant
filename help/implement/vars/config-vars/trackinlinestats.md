---
title: trackInlineStats
description: 在您的實作中啟用或停用Activity Map。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackInlineStats

Activity map是Adobe Analytics中的一項功能，可收集訪客點按位置及其點按內容的資料。 您可以在Analytics報表中檢視此資料，或使用瀏覽器延伸功能覆蓋來檢視。 如果您想要使用Activity map功能，請啟用此變數。

啟用後，AppMeasurement會收集連結的相關資訊，並在下次影像要求中傳送該資料。 每次點按的資訊會儲存在標示為Cookie中 `s_sq`。

## 在Adobe Experience Platform Launch中啟用Clickmap

[!UICONTROL 設定Adobe Analytics擴充功能時] ,「連結追蹤」 [!UICONTROL accordion下方的核取方塊會啟用Clickmap] 。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開「 [!UICONTROL 連結追蹤] 」accordion，顯示「啟用 [!UICONTROL Clickmap] 」核取方塊。

按一下核取方塊以啟用Activity map追蹤。

## AppMeasurement和Launch自訂代碼編輯器中的s.trackInlineStats

此為 `s.trackInlineStats` 布林值，可啟用或停用Activity map追蹤。 Its default value is `false`. 如果您要啟 `true` 用Activity map資料收集，請將此值設為。

```js
s.trackInlineStats = true;
```
