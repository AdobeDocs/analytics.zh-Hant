---
title: linkName
description: 設定自訂連結點擊的名稱。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkName

使用變 `linkName` 數可決定執行下一個方法時自訂連結、下載連結或退出連結的維 [`tl()`](../functions/tl-method.md) 度值。

如果此變數為空白，AppMeasurement會回復至變 [`linkURL`](linkurl.md) 數。

## Adobe Experience Platform Launch中的連結名稱

您可以設定規則以傳送信標時的連結名稱欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Rules] ，然後按一下所要的規則（或建立規則）。
4. 在下 [!UICONTROL Actions]方，按一下「+」圖示
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為傳送信標。
6. 按一下顯 `s.tl()` 示欄位的選項按 [!UICONTROL Link Name] 鈕。

## AppMeasurement和Launch自訂代碼編輯器中的s.linkName

變 `s.linkName` 數是一個字串，可決定自訂連結、下載連結或退出連結的維度值(視 [`s.linkType`](linktype.md) 情況而定)。 它最多可容納100個位元組。

> [!TIP] 此變數是方法的第三個 `tl()` 參數，通常不需要設為獨立變數。 但是，如果您不 `linkName` 想在方法中將值設為參數，則可使用變 `tl()` 數。

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
