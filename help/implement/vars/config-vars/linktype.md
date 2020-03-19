---
title: linkType
description: 使用linkType變數來判斷點擊所屬的連結追蹤維度。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkType

連結追蹤點擊可填入三個維度之一：

* 自訂連結
* 退出連結
* 下載連結

使用變 `linkType` 數可決定在執行下一個函式時要填入的 [`tl()`](../functions/tl-method.md) 維度。

## Adobe Experience Platform Launch中的連結類型

設定規則以傳送信標時的連結類型。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Rules] ，然後按一下所要的規則（或建立規則）。
4. 在下 [!UICONTROL Actions]方，按一下「+」圖示
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為傳送信標。
6. 按一下顯 `s.tl()` 示下拉式清單的選項 [!UICONTROL Link Type] 按鈕。

您可以將此下拉式清單設 [!UICONTROL Custom Link]定為 [!UICONTROL Download Link]、或 [!UICONTROL Exit Link]。

## s.linkType（在AppMeasurement和Launch自訂代碼編輯器中）

變 `s.linkType` 數是接受三個單字元值之一的字串： `o`、 `d`或 `e`。 如果呼叫 `tl()` 的方法沒有連結類型，則預設為自訂連結。

* `o` - 自訂連結
* `d` -下載連結
* `e` -退出連結

> [!TIP] 此變數是方法的第二個 `tl()` 參數，通常不需要設為獨立變數。 但是，如果您不 `linkType` 想在方法中將值設為參數，則可使用變 `tl()` 數。

```js
s.linkType = "e";
```

## 範例

以下兩個範例連結追蹤呼叫的功能完全相同。 它們是完成相同連結追蹤點擊的不同方法。

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
