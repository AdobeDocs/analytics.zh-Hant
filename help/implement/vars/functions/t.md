---
title: t
description: 傳送頁面檢視追蹤呼叫給Adobe。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# t

方 `t` 法是Adobe Analytics的重要核心元件。 它會將頁面上定義的所有Analytics變數匯入影像請求，然後將該資料傳送至Adobe資料收集伺服器。

例如，請考慮下列JavaScript程式碼：

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension value";

// Compile the variables on the page into an image request to Adobe
s.t();
```

執行方 `t` 法會定義所有Analytics變數，並根據這些變數產生URL。 有些Analytics變數會決定影像的URL，而其他變數則會決定查詢字串參數值。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe會接收影像要求，然後分析要求標題、URL和查詢字串參數。 然後，資料收集伺服器會傳回透明的1x1像素影像，在您的網站上不可見顯示。

## Adobe Experience Platform Launch中的頁面檢視追蹤呼叫

Launch有專用位置設定頁面檢視追蹤呼叫。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下，按一下「+」圖示
5. 將「延 [!UICONTROL 伸功能] 」下拉式清單設定為Adobe Analytics，並設定 [!UICONTROL 「傳送信標的動作類型] 」。
6. Click the `s.t()` radio button.

## AppMeasurement和Launch自訂代碼編輯器中的s.t()方法

當您想 `s.t()` 要傳送追蹤呼叫至Adobe時，請呼叫方法。

```js
s.t();
```

或者，您可以使用物件作為引數來覆寫變數值。 如需詳 [細資訊](../../js/overrides.md) ，請參閱變數覆寫。

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

> [!NOTE] 舊版AppMeasurement使用數行程式碼來呼叫此函式。 其他程式碼過去會針對不同的瀏覽器提供解決方法。 現代瀏覽器的標準化和最佳實務不再需要此程式碼區塊。 現在只需要方 `s.t()` 法呼叫。
