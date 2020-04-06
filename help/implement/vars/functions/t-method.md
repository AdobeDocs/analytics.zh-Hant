---
title: t
description: 傳送頁面檢視追蹤呼叫給 Adobe。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# t()

`t()` 方法是 Adobe Analytics 的重要核心元件。它會使用頁面上定義的所有 Analytics 變數、編譯成影像要求，然後將該資料傳送至 Adobe 資料收集伺服器。

例如，請考慮下列 JavaScript 程式碼：

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension value";

// Compile the variables on the page into an image request to Adobe
s.t();
```

執行 `t()` 方法需要使用所有定義的 Analytics 變數，以及根據這些變數制訂 URL。有些 Analytics 變數決定影像的 URL，有些變數則決定查詢字串參數值。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe 會接收影像要求，然後分析要求標題、URL 和查詢字串參數。接下來，資料收集伺服器會傳回透明的 1x1 像素影像，利用不可見的方式顯示在您的網站上。

## Adobe Experience Platform Launch 中的頁面檢視追蹤呼叫

Launch 有設定頁面檢視追蹤呼叫的專用位置。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the &#39;+&#39; icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. 按一下 `s.t()` 選擇鈕。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.t() 方法

當您想要傳送追蹤呼叫至 Adobe 時，請呼叫 `s.t()` 方法。

```js
s.t();
```

或者，您也可以將物件當作引數來覆寫變數值。如需詳細資訊，請參閱[變數覆寫](../../js/overrides.md)。

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE] 舊版 AppMeasurement 會使用數行程式碼來呼叫此函數。其他程式碼過去會針對不同的瀏覽器提供解決方法。現代瀏覽器的標準化和最佳實務不再需要這個程式碼區塊。現在只需要方法呼叫 `s.t()` 。
