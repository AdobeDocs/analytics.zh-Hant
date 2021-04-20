---
title: 使用tl()方法與Activity Map
description: 您可以使用tl()方法來追蹤自訂元素，並設定動態內容的覆蓋呈現。
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 43%

---


# 使用`tl()`方法與Activity Map

您可使用 `tl()` 方法追蹤自訂元素，並設定動態內容的覆蓋圖演算作業。

## 追蹤自訂元素

在 Activity Map AppMeasurement 模組中使用這個[`tl()`方法](/help/implement/vars/functions/tl-method.md)，即可在物件不是錨記或影像元素時，仍能追蹤使用者點選的任何物件。使用`tl()`，您可以追蹤未導致頁面載入的任何自訂元素。

此 `tl()` 方法中，目前識別退出連結、自訂連結等作業所使用的 `linkName` 參數，也將用於識別 Activity Map 變數的連結 ID。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

換言之，如果您使用`tl()`來追蹤自訂元素，則會從`tl()`方法中作為第三個參數（連結名稱）傳遞的值提取連結ID。 無法從 Activity Map [預設追蹤](activitymap-link-tracking-methodology.md)所用的標準連結追蹤演算法提取這個值。

## 動態內容的覆蓋圖演算

當直接從HTML元素的點按上事件呼叫`tl()`方法時，載入網頁時，Activity Map可顯示該元素的覆蓋。 範例：

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

Activity Map覆蓋動態內容連結的最佳方式是設定自訂的`ActivityMap.link`函式，以呼叫傳回值至`tl()`的相同函式。 例如：

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

在此，我們覆寫了`ActivityMap.link`函式，以便在呼叫時執行下列三項之一：

1. 如果傳遞`linkName`，則此變數會由`tl()`呼叫，因此請傳回`tl()`作為`linkName`傳入的項目。
2. 在報告時由Activity Map呼叫時，不會傳遞`linkName`，因此會使用連結元素呼叫`makeLinkName()`。 這是關鍵步驟- `makeLinkName(element)`呼叫應與`<button>`標籤中`tl()`呼叫的第3個引數相同。 這表示呼叫`tl()`時，我們會追蹤`makeLinkName()`傳回的字串。 當Activity Map報告頁面上的連結時，會使用相同的呼叫來建立連結。
3. 最終解決方案是僅傳回預設 ActivityMap 連結函數的原始傳回值。在預設情況下，保留此參考以呼叫，可協助您只需覆寫或寫入`makeLinkName()`的自訂程式碼，而不需為頁面上的所有連結提供連結傳回值。
