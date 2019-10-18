---
description: 您可使用 s.tl() 函數來追蹤自訂元素以及設定動態內容的覆蓋圖演算。
seo-description: 您可使用 s.tl() 函數來追蹤自訂元素以及設定動態內容的覆蓋圖演算。
seo-title: 使用 s.tl() 函數
solution: Analytics
title: 使用 s.tl() 函數
topic: Activity Map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# 使用 s.tl() 函數

您可使用 s.tl() 函數來追蹤自訂元素以及設定動態內容的覆蓋圖演算。

## Tracking custom elements {#section_5D6688DFFFC241718249A9A0C632E465}

在 AppMeasurement 模組中使用 [s.tl() 函數](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html)，可讓您在物件不是錨記或影像元素時，仍能追蹤被點按的物件。[!DNL Activity Map]使用 s.tl，可以追蹤不會產生頁面載入的任何自訂元素。

在 s.tl 函數中，目前用於識別退出連結、自訂連結等的 linkName 參數，is now also used to identify the Link ID for the [!DNL Activity Map] variable.

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

換句話說，如果您使用 s.tl 追蹤自訂元素，則會從 s.tl() 函數的第三個參數 (linkName) 傳遞的值提取連結 ID。It is not pulled from the standard link tracking algorithm that is used for [default tracking](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) in [!DNL Activity Map].

## Overlay rendering for dynamic content {#section_FD24B61A732149C7B58BA957DD84A5E7}

When the s.tl() function is called directly from the HTML element’s on-click event, [!DNL Activity Map] can display an overlay for that element when the web page is loaded. 範例:

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

如果在初始頁面載入後新增任何網頁內容至頁面，都將間接呼叫 s.tl() 函數，且將無法顯示該新內容的覆蓋圖，除非明確地啟動/按下該新內容。Then a new link collection process is triggered from [!DNL Activity Map].

When the s.tl() function is not called directly from the HTML element’s on-click event, [!DNL Activity Map] can only display overlay once that element has been clicked by the user. 以下是間接呼叫 s.tl() 函數的範例:

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

The best way for [!DNL Activity Map] to overlay dynamic content links is to have a customized ActivityMap.link function set up to call the same function whose return value is passed to s.tl. 以下是範例:

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type=”button” onclick=”s.tl(this,’o’,makeLinkName(this)”>Add To Cart</button>
```

此處，在呼叫時，我們已覆寫 ActivityMap.link 函數，以執行下列三個事項其中之一:

1. 若傳遞的是 linkName，ActivityMap.link 會由 s.tl() 呼叫，因此僅傳回 s.tl 以 linkName 傳遞的內容。
1. This is called by [!DNL Activity Map] at reporting time, so a linkName is never passed, and so call makeLinkName() with the link element. This is the crucial step here - the “makeLinkName(element)” call should be the same at the s.tl call’s 3rd argument in the `<button>` tag. 這表示當系統呼叫 s.tl 時，我們會追蹤由 makeLinkName 傳回的字串。When [!DNL Activity Map] reports on the links on the page, is uses the same call to make a link.
1. 最終解決方案是僅傳回預設 ActivityMap 連結函數的原始傳回值。在預設情況下，保留此參考備用以便呼叫，可協助您僅需覆寫或寫入 makeLinkName 的自訂代碼，而不需針對頁面上所有連結提出連結傳回值。
