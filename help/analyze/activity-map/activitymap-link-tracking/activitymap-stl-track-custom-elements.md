---
description: 您可使用 s.tl() 函數來追蹤自訂元素以及設定動態內容的覆蓋圖演算。
title: 使用 s.tl() 函數
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用 s.tl() 函數

您可使用 s.tl() 函數來追蹤自訂元素以及設定動態內容的覆蓋圖演算。

## 追蹤自訂元素 {#section_5D6688DFFFC241718249A9A0C632E465}

在 Activity Map AppMeasurement 模組中使用 [s.tl() 函數](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html)，可讓您在物件不是錨記或影像元素時，仍能追蹤被點按的物件。使用 s.tl，可以追蹤不會產生頁面載入的任何自訂元素。

在 s.tl 函數中，目前用於識別退出連結、自訂連結等的 linkName 參數，也將用來識別 Activity Map 變數的連結 ID。

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

換句話說，如果您使用 s.tl 追蹤自訂元素，則會從 s.tl() 函數的第三個參數 (linkName) 傳遞的值提取連結 ID。無法從 Activity Map [預設追蹤](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md)所用的標準連結追蹤演算法提取這個值。

## 動態內容的覆蓋圖演算 {#section_FD24B61A732149C7B58BA957DD84A5E7}

從 HTML 元素的點按事件直接呼叫 s.tl() 函數時，Activity Map 可以在載入網頁時顯示該元素的覆蓋圖。範例:

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

如果在初始頁面載入後新增任何網頁內容至頁面，都將間接呼叫 s.tl() 函數，且將無法顯示該新內容的覆蓋圖，除非明確地啟動/按下該新內容。之後會從 Activity Map 觸發新的連結收集程序。

如果不是從 HTML 元素的點按事件直接呼叫 s.tl() 函數，Activity Map 必須等到使用者點按該元素後，才能顯示覆蓋圖。以下是間接呼叫 s.tl() 函數的範例:

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

Activity Map 覆蓋動態內容連結的最佳方式是具備自訂的 ActivityMap.link 函數設定，藉此呼叫其傳回值已傳遞至 s.tl. 的相同函數。範例如下:

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

此處，在呼叫時，我們已覆寫 ActivityMap.link 函數，以執行下列三個事項其中之一:

1. 若傳遞的是 linkName，ActivityMap.link 會由 s.tl() 呼叫，因此僅傳回 s.tl 以 linkName 傳遞的內容。
1. 此為 Activity Map 於報告時間所呼叫的項目，所以 linkName 未曾傳遞成功，因此採用連結元素呼叫 makeLinkName()。此為非常重要的步驟 –「makeLinkName(element)」呼叫應與 `<button>` 標記中 s.tl 呼叫的第 3 引數相同。這表示當系統呼叫 s.tl 時，我們會追蹤由 makeLinkName 傳回的字串。當 Activity Map 報告在頁面上的連結時，會使用相同的呼叫產生連結。
1. 最終解決方案是僅傳回預設 ActivityMap 連結函數的原始傳回值。在預設情況下，保留此參考備用以便呼叫，可協助您僅需覆寫或寫入 makeLinkName 的自訂代碼，而不需針對頁面上所有連結提出連結傳回值。
