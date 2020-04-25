---
title: linkName
description: 設定自訂連結點擊的名稱。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkName

Use the `linkName` variable to determine the dimension value of custom links, download links, or exit links when running the next [`tl()`](../functions/tl-method.md) method.

如果此變數為空白，AppMeasurement 會回復成 [`linkURL`](linkurl.md) 變數。

## Adobe Experience Platform Launch 中的連結名稱

在設定傳送信標的規則時，您可以設定連結名稱欄位。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下「+」圖示
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為「傳送信標」。
6. 按一下 `s.tl()` 選擇鈕顯示[!UICONTROL 「連結名稱」]欄位。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.linkName

`s.linkName` 變數是字串，可決定自訂連結、下載連結或退出連結的維度值 (視 [`s.linkType`](linktype.md) 的情況而定)。它最多可容納 100 個位元組。

>[!TIP] 此變數是方法的第三個 `tl()` 參數，通常不需要設為獨立變數。 However, you can use the `linkName` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkName = "Example custom link";
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
