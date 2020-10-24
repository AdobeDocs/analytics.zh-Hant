---
description: 您可使用 s.tl() 方法追蹤自訂元素，並設定動態內容的覆蓋圖演算作業。
title: 使用 s.tl() 方法
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3
workflow-type: ht
source-wordcount: '491'
ht-degree: 100%

---


# 使用 `tl()` 方法

您可使用 `tl()` 方法追蹤自訂元素，並設定動態內容的覆蓋圖演算作業。

## 追蹤自訂元素 {#section_5D6688DFFFC241718249A9A0C632E465}

在 Activity Map AppMeasurement 模組中使用這個[`tl()`方法](/help/implement/vars/functions/tl-method.md)，即可在物件不是錨記或影像元素時，仍能追蹤使用者點選的任何物件。s.tl 可追蹤不會產生頁面載入的任何自訂元素。

此 `tl()` 方法中，目前識別退出連結、自訂連結等作業所使用的 `linkName` 參數，也將用於識別 Activity Map 變數的連結 ID。

```js
s.tl(this,linkType,linkName,variableOverrides)
```

換句話說，如果您使用 `s.tl()` 追蹤自訂元素，則會從 `s.tl()` 方法第三個參數 (linkName) 傳遞的值提取連結 ID。無法從 Activity Map [預設追蹤](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md)所用的標準連結追蹤演算法提取這個值。

## 動態內容的覆蓋圖演算 {#section_FD24B61A732149C7B58BA957DD84A5E7}

從 HTML 元素的點按事件直接呼叫 s.tl() 函數時，Activity Map 可以在載入網頁時顯示該元素的覆蓋圖。範例：

```html
<div onclick="s.tl(this,'o','Example custom link')">Example link text</a>
```

如果在初始頁面載入後新增任何網頁內容，都將間接呼叫 `tl()` 方法，且除非使用者明確啟動/按下該新內容，否則系統無法顯示該內容的覆蓋圖。之後會從 Activity Map 觸發新的連結收集程序。

如果不是從 HTML 元素的點擊事件直接呼叫 `tl()` 方法，Activity Map 必須等到使用者點選該元素後，才能顯示覆蓋圖。間接呼叫 `tl()` 方法的範例如下：

```html
<div onclick="someFn(event)"></div>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Activity Map 覆蓋動態內容連結的最佳方式是設定自訂的 ActivityMap.link 函數，藉此呼叫傳回值會傳遞至 `s.tl` 的相同函數。例如：

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

此處，在呼叫時，我們已覆寫 ActivityMap.link 函數，以執行下列三個事項其中之一：

1. 若傳遞的是 linkName，ActivityMap.link 會由 s.tl() 呼叫，因此僅傳回 s.tl 以 linkName 傳遞的內容。
2. 此為 Activity Map 於報告時間所呼叫的項目，所以 linkName 未曾傳遞成功，因此採用連結元素呼叫 makeLinkName()。此為非常重要的步驟 –「makeLinkName(element)」呼叫應與 `<button>` 標記中 s.tl 呼叫的第 3 引數相同。這表示當系統呼叫 s.tl 時，我們會追蹤由 makeLinkName 傳回的字串。當 Activity Map 報告在頁面上的連結時，會使用相同的呼叫產生連結。
3. 最終解決方案是僅傳回預設 ActivityMap 連結函數的原始傳回值。在預設情況下，保留此參考備用以便呼叫，可協助您僅需覆寫或寫入 makeLinkName 的自訂代碼，而不需針對頁面上所有連結提出連結傳回值。
