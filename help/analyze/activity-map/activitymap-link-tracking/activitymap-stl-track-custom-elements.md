---
description: 您可以使用s.tl()方法來追蹤自訂元素，並設定動態內容的覆蓋圖演算。
title: 使用s.tl()方法
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 290526ecc1b040f93d0734a5deaf2d79ab1bde10

---


# 使用方 `tl` 法

You can use the `tl` method to track custom elements and to configure overlay rendering for dynamic content.

## 追蹤自訂元素 {#section_5D6688DFFFC241718249A9A0C632E465}

Using the [`tl` method](/help/implement/vars/functions/tl-method.md) as part of the Activity Map AppMeasurement module lets you track any object that is clicked on, even objects that are not anchor tags or image elements. 使用 s.tl，可以追蹤不會產生頁面載入的任何自訂元素。

In the `tl` method, the `linkName` parameter that is currently used to identify the exit links, custom links, etc. 也將用來識別 Activity Map 變數的連結 ID。

```js
s.tl(this,linkType,linkName,variableOverrides)
```

In other words, if you use `s.tl` to track your custom elements, the link ID is pulled from the value passed as the third parameter (linkName) in the `s.tl` method. 無法從 Activity Map [預設追蹤](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md)所用的標準連結追蹤演算法提取這個值。

## 動態內容的覆蓋圖演算 {#section_FD24B61A732149C7B58BA957DD84A5E7}

從 HTML 元素的點按事件直接呼叫 s.tl() 函數時，Activity Map 可以在載入網頁時顯示該元素的覆蓋圖。範例:

```html
<div onclick="s.tl(this,'o','Example custom link')">Example link text</a>
```

Whenever any web page content is added to the page after the initial page load, the `tl` method is called indirectly and we cannot display overlays for that new content unless it is expressly activated/clicked. 之後會從 Activity Map 觸發新的連結收集程序。

When the `tl` method is not called directly from the HTML element&#39;s on-click event, Activity Map can only display overlay once that element has been clicked by the user. Here is an example where the `tl` method is called indirectly:

```html
<div onclick="someFn(event)"></div>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

The best way for Activity Map to overlay dynamic content links is to have a customized ActivityMap.link function set up to call the same function whose return value is passed to `s.tl`. 例如:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName) {
    return linkName ||      // if this is a s.tl call, just return string passed
        makeLinkName(element) || // this is ActivityMap reporting time
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

此處，在呼叫時，我們已覆寫 ActivityMap.link 函數，以執行下列三個事項其中之一:

1. 若傳遞的是 linkName，ActivityMap.link 會由 s.tl() 呼叫，因此僅傳回 s.tl 以 linkName 傳遞的內容。
2. 此為 Activity Map 於報告時間所呼叫的項目，所以 linkName 未曾傳遞成功，因此採用連結元素呼叫 makeLinkName()。此為非常重要的步驟 –「makeLinkName(element)」呼叫應與 `<button>` 標記中 s.tl 呼叫的第 3 引數相同。這表示當系統呼叫 s.tl 時，我們會追蹤由 makeLinkName 傳回的字串。當 Activity Map 報告在頁面上的連結時，會使用相同的呼叫產生連結。
3. 最終解決方案是僅傳回預設 ActivityMap 連結函數的原始傳回值。在預設情況下，保留此參考備用以便呼叫，可協助您僅需覆寫或寫入 makeLinkName 的自訂代碼，而不需針對頁面上所有連結提出連結傳回值。
