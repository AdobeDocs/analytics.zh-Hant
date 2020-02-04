---
title: visitorID
description: 使用自訂訪客ID。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorID

Adobe使用數種不同的方法來識別您網站上的訪客。 變數 `visitorID` 會覆寫所有其他訪客識別方法。

> [!IMPORTANT] Adobe建議您不要使用此變數。 請改 [用Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) 。

## Adobe Experience Platform Launch中的訪客ID

[!UICONTROL 訪客ID] 是設定Adobe Analytics擴充功能時 [!UICONTROL Cookie] accordion下方的欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開 [!UICONTROL Cookies accordion] ，以顯示 [!UICONTROL 訪客ID] 欄位。

將此欄位指派給包含自訂訪客ID的資料元素。 請勿將此欄位設為靜態值。

## AppMeasurement和Launch自訂代碼編輯器中的s.visitorID

變 `s.visitorID` 數是包含訪客自訂唯一識別碼的字串。 有效值包括最多100個位元組的英數字元。 請避免在此變數中使用虛線、空格、底線或符號。

> [!WARNING] 如果您在瀏覽中 `visitorID` 設定變數部分，資料會產生兩個不同的獨特訪客。

```js
s.visitorID = "abc123";
```
