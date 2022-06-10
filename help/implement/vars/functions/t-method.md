---
title: t
description: 傳送頁面瀏覽數追蹤呼叫給 Adobe。
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 52%

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

## 使用Web SDK擴展發送事件

使用「操作」配置將XDM事件資料發送到Adobe。 資料流接收此資料，應用任何配置的映射，如果資料是該資料流的附加服務，則將資料轉發到Adobe Analytics。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 前往[!UICONTROL 規則]標記，然後按一下所需的規則 (或建立規則)。
1. 下 [!UICONTROL 操作]，按一下所需的「操作」(Action)，或按一下 **&#39;+&#39;** 表徵圖以添加操作。
1. 設定 [!UICONTROL 擴展] 下拉清單 **[!UICONTROL Adobe Experience PlatformWeb SDK]** 和 [!UICONTROL 操作類型] 至 **[!UICONTROL 發送事件]**。

## 手動發送事件以實現Web SDK

使用 `sendEvent` 命令將資料發送到Adobe。 資料流接收此資料，應用任何配置的映射，如果資料是該資料流的附加服務，則將資料轉發到Adobe Analytics。

```js
alloy("sendEvent", {
  "xdm": {}
});
```

請參閱 [跟蹤事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=zh-Hant) 的子菜單。

## 使用Adobe Analytics分機的頁面視圖跟蹤呼叫

Adobe Experience Platform資料收集中的Adobe Analytics分機具有專用位置集頁面視圖跟蹤調用。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 前往[!UICONTROL 規則]標記，然後按一下所需的規則 (或建立規則)。
1. 下 [!UICONTROL 操作]，按一下所需的操作，或按一下 **&#39;+&#39;** 表徵圖以添加操作。
1. 設定 [!UICONTROL 擴展] 下拉清單 **[!UICONTROL Adobe Analytics]**&#x200B;的 [!UICONTROL 操作類型] 至 **[!UICONTROL 發送信標]**。
1. 按一下 `s.t()` 選擇鈕。

## s.t()方法和AppMeasurement和Analytics擴展自定義代碼編輯器

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
