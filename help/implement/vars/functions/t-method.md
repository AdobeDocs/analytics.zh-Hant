---
title: t
description: 傳送頁面瀏覽數追蹤呼叫給 Adobe。
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 58%

---

# t()

`t()` 方法是 Adobe Analytics 的重要核心元件。它會使用頁面上定義的所有 Analytics 變數、編譯成影像要求，然後將該資料傳送至 Adobe 資料收集伺服器。

例如，請考慮下列 JavaScript 程式碼：

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

執行 `t()` 方法需要使用所有定義的 Analytics 變數，以及根據這些變數制訂 URL。有些 Analytics 變數決定影像的 URL，有些變數則決定查詢字串參數值。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe 會接收影像要求，然後分析要求標題、URL 和查詢字串參數。接下來，資料收集伺服器會傳回透明的 1x1 像素影像，利用不可見的方式顯示在您的網站上。

## 使用Web SDK擴充功能傳送事件

使用動作來設定傳送XDM事件資料至Adobe。 Datastream會接收此資料、套用任何已設定的對應，以及如果該資料是該Datastream的新增服務，則將該資料轉送至Adobe Analytics。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
1. 在 [!UICONTROL 動作]，按一下所需的動作，或按一下 **&#39;+&#39;** 圖示以新增動作。
1. 設定 [!UICONTROL 擴充功能] 下拉式清單 **[!UICONTROL Adobe Experience Platform Web SDK]** 和 [!UICONTROL 動作類型] to **[!UICONTROL 傳送事件]**.

## 手動實作Web SDK的傳送事件

使用 `sendEvent` 命令將資料發送到Adobe。 Datastream會接收此資料、套用任何已設定的對應，以及如果該資料是該Datastream的新增服務，則將該資料轉送至Adobe Analytics。

```js
alloy("sendEvent", {
  "xdm": {}
});
```

請參閱 [追蹤事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=zh-Hant) 如需詳細資訊，請參閱網頁SDK檔案。

## 使用Adobe Analytics擴充功能的頁面檢視追蹤呼叫

Adobe Experience Platform Data Collection中的Adobe Analytics擴充功能有設定頁面檢視追蹤呼叫的專用位置。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
1. 在 [!UICONTROL 動作]，按一下所需的動作，或按一下 **&#39;+&#39;** 圖示以新增動作。
1. 設定 [!UICONTROL 擴充功能] 下拉式清單 **[!UICONTROL Adobe Analytics]**，和 [!UICONTROL 動作類型] to **[!UICONTROL 傳送信標]**.
1. 按一下 `s.t()` 選擇鈕。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.t()方法

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

>[!NOTE]
>
>舊版 AppMeasurement 會使用數行程式碼來呼叫此函數。其他程式碼過去會針對不同的瀏覽器提供解決方法。現代瀏覽器的標準化和最佳做法不再需要這個程式碼區塊。現在只需要方法呼叫 `s.t()` 。
