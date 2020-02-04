---
title: linkName
description: 設定自訂連結點擊的名稱。
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkName

使用變 `linkName` 數可決定執行下一個函式時自訂連結、下載連結或退出連結的維度 `tl()` 值。

如果此變數為空白，AppMeasurement會回復至變 `linkURL` 數。

## Adobe Experience Platform Launch中的連結名稱

您可以設定規則以傳送信標時的連結名稱欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下，按一下「+」圖示
5. 將「延 [!UICONTROL 伸功能] 」下拉式清單設定為Adobe Analytics，並設定 [!UICONTROL 「傳送信標的動作類型] 」。
6. 按一下顯 `s.tl()` 示「連結名稱」欄位 [!UICONTROL 的選項按鈕] 。

## AppMeasurement和Launch自訂代碼編輯器中的s.linkName

變 `s.linkName` 數是一個字串，可決定自訂連結、下載連結或退出連結的維度值(視 `s.linkType` 情況而定)。 它最多可容納100個位元組。

> [!TIP] 此變數是函式的第三個參 `tl()` 數，通常不需要設定為獨立變數。 但是，如果您不 `linkName` 想在函式中將值設為引數，則可使用變 `tl()` 數。

```js
s.linkName = "Example custom link";
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
