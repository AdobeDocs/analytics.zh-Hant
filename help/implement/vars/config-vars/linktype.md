---
title: linkType
description: 使用 linkType 變數來判斷點擊所屬的連結追蹤維度。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '239'
ht-degree: 100%

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
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下「+」圖示
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為「傳送信標」。
6. 按一下 `s.tl()` 選擇鈕顯示[!UICONTROL 「連結類型」]下拉式清單。

您可以將此下拉式清單設定為[!UICONTROL 「自訂連結」]、[!UICONTROL 「下載連結」]或[!UICONTROL 「退出連結」]。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.linkType

`s.linkType` 變數是字串，能接受 `o`、`d` 或 `e` 等三個單一字元值的其中之一。如果您在呼叫 `tl()` 方法時未使用連結類型，預設值為自訂連結。

* `o` - 自訂連結
* `d` - 下載連結
* `e` - 退出連結

>[!TIP]
>
> 此變數是 `tl()` 方法的第二個參數，通常不需要設為獨立變數。但是，如果您不想在 `linkType` 方法中設定引數形式的值，可以使用 `tl()` 變數。

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
