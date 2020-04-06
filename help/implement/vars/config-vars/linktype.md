---
title: linkType
description: 使用 linkType 變數來判斷點擊所屬的連結追蹤維度。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkType

連結追蹤點擊可填入三個維度的其中之一：

* 自訂連結
* 退出連結
* 下載連結

使用 `linkType` 變數可決定下次 [`tl()`](../functions/tl-method.md) 函數執行時要填入哪個維度。

## Adobe Experience Platform Launch 中的連結類型

在設定傳送信標的規則時，您可以設定連結類型。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the &#39;+&#39; icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Type] dropdown.

您可以將此下拉式清單設 [!UICONTROL Custom Link]定為 [!UICONTROL Download Link]、或 [!UICONTROL Exit Link]。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.linkType

`s.linkType` 變數是字串，能接受 `o`、`d` 或 `e` 等三個單一字元值的其中之一。If a `tl()` method is called without a link type, it defaults to Custom link.

* `o` - 自訂連結
* `d` - 下載連結
* `e` - 退出連結

>[!TIP] 此變數是方法的第二個 `tl()` 參數，通常不需要設為獨立變數。 However, you can use the `linkType` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkType = "e";
```

## 範例

以下兩個範例連結追蹤呼叫的功能完全相同。它們是完成相同連結追蹤點擊的不同方法。

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
