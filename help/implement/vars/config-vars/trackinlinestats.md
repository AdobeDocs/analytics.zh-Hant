---
title: trackInlineStats
description: 在您的實施中啟用或停用 Activity Map。
translation-type: ht
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackInlineStats

Activity Map 是 Adobe Analytics 中的功能，可收集有關訪客點按位置及點按內容的資料。您可以在 Analytics 報表中檢視這些資料，或使用瀏覽器擴充功能覆蓋來檢視。如果您想要使用 Activity Map 功能，請啟用此變數。

啟用後，AppMeasurement 會收集連結的相關資訊，並在下一個影像要求中傳送該資料。每次點按的資訊會儲存在標示為 `s_sq` 的 Cookie中。

## Adobe Experience Platform Launch 中的啟用 Clickmap

[!UICONTROL 「啟用 Clickmap」]是在設定 Adobe Analytics 擴充功能時，於[!UICONTROL 「連結追蹤」]設定追蹤器下方的核取方塊。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]設定追蹤器，如此可顯示[!UICONTROL 「啟用 Clickmap」]核取方塊。

按一下核取方塊以啟用 Activity Map 追蹤。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.trackInlineStats

`s.trackInlineStats` 是布林值，可啟用或停用 Activity Map 追蹤。其預設值為 `false`。如果您要啟用Activity Map 資料收集，請將此值設為 `true`。

```js
s.trackInlineStats = true;
```
