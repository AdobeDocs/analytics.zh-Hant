---
title: linkType
description: 使用linkType變數來判斷點擊所屬的連結追蹤維度。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkType

連結追蹤點擊可填入三個維度之一：

* 自訂連結
* 退出連結
* 下載連結

使用變 `linkType` 數可決定在執行下一個函式時要填入的 `tl()` 維度。

## Adobe Experience Platform Launch中的連結類型

設定規則以傳送信標時的連結類型。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下，按一下「+」圖示
5. 將「延 [!UICONTROL 伸功能] 」下拉式清單設定為Adobe Analytics，並設定 [!UICONTROL 「傳送信標的動作類型] 」。
6. 按一下顯 `s.tl()` 示「連結類型」下拉式清 [!UICONTROL 單的選項按鈕] 。

您可以將此下拉式清單設 [!UICONTROL 定為「自訂連結]」、「 [!UICONTROL 下載連結]」或「 [!UICONTROL 退出連結」]。

## s.linkType（在AppMeasurement和Launch自訂代碼編輯器中）

變 `s.linkType` 數是接受三個單字元值之一的字串： `o`、 `d`或 `e`。 如果呼叫 `tl()` 的函式沒有連結類型，則預設為自訂連結。

* `o` - 自訂連結
* `d` -下載連結
* `e` -退出連結

> [!TIP] 此變數是函式的第二個 `tl()` 參數，通常不需要設定為獨立變數。 但是，如果您不 `linkType` 想在函式中將值設為引數，則可使用變 `tl()` 數。

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
