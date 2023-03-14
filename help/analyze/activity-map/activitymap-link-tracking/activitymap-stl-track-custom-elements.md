---
title: 使用tl()方法並搭配Activity Map
description: 您可以使用tl()方法追蹤自訂元素，並設定動態內容的覆蓋圖演算作業。
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 43%

---

# 使用 `tl()` 具有Activity Map的方法

您可使用 `tl()` 方法追蹤自訂元素，並設定動態內容的覆蓋圖演算作業。

## 追蹤自訂元素

在 Activity Map AppMeasurement 模組中使用這個[`tl()`方法](/help/implement/vars/functions/tl-method.md)，即可在物件不是錨記或影像元素時，仍能追蹤使用者點選的任何物件。使用 `tl()`，您可以追蹤不會產生頁面載入的任何自訂元素。

此 `tl()` 方法中，目前識別退出連結、自訂連結等作業所使用的 `linkName` 參數，也將用於識別 Activity Map 變數的連結 ID。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

換句話說，如果您使用 `tl()` 若要追蹤自訂元素，系統會從 `tl()` 方法。 無法從 Activity Map [預設追蹤](activitymap-link-tracking-methodology.md)所用的標準連結追蹤演算法提取這個值。

## 動態內容的覆蓋圖演算

當 `tl()` 方法是從HTML元素的點按上事件直接呼叫，Activity Map可在載入網頁時顯示該元素的覆蓋圖。 範例:

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

如果在初始頁面載入後新增任何網頁內容，都將間接呼叫 `tl()` 方法，且除非使用者明確啟動/按下該新內容，否則系統無法顯示該內容的覆蓋圖。之後會從 Activity Map 觸發新的連結收集程序。

如果不是從 HTML 元素的點擊事件直接呼叫 `tl()` 方法，Activity Map 必須等到使用者點選該元素後，才能顯示覆蓋圖。間接呼叫 `tl()` 方法的範例如下：

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Activity Map覆蓋動態內容連結的最佳方式是自訂內容 `ActivityMap.link` 函式設定，以呼叫傳回值會傳遞至的相同函式 `tl()`. 例如：

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName)
{
    // if this is a s.tl call, just return string passed
    return linkName ||      
    // this is ActivityMap reporting time
    makeLinkName(element) ||
    // our custom function didn't return anything, so just return the default ActivityMap Link
    originalLinkFunction(element,linkName);
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

在此，我們已覆寫 `ActivityMap.link` 函式，在呼叫時執行下列三項之一：

1. 若 `linkName` 傳遞，則呼叫者為 `tl()`所以，只要傳回 `tl()` 以 `linkName`.
2. 當Activity Map在報告時呼叫時， `linkName` 從未傳遞，因此呼叫 `makeLinkName()` 連結元素。 這是關鍵的一步 —  `makeLinkName(element)` 呼叫應與 `tl()` 呼叫的第3個引數 `<button>` 標籤。 這表示當 `tl()` 稱為，我們會追蹤傳回的字串 `makeLinkName()`. 當Activity Map報告頁面上的連結時，會使用相同的呼叫來建立連結。
3. 最終解決方案是僅傳回預設 ActivityMap 連結函數的原始傳回值。在預設情況下，保留此參考以呼叫，可協助您只需覆寫或撰寫 `makeLinkName()` 而且不必為頁面上的所有連結提供連結傳回值。
