---
title: 搭配使用AppMeasurement和iframe
description: 在iframe中存取iframe內或父頁面的Adobe Analytics變數。
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
translation-type: tm+mt
source-git-commit: 40bf2bbb522a94a678d0da1a645d83a5121c93d0
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 6%

---

# 搭配使用AppMeasurement和iframe

您可以從子系和父系參照AppMeasurement變數。 您必須在AppMeasurement程式庫所在的相同位置定義所有變數。 下列範例說明如何在iframe內外設定基本的AppMeasurement變數和方法。

如果您使用Adobe Experience Platform Launch，請確定追蹤器物件是可全域存取的。 請參閱「啟動使用指南」中的[Adobe Analytics分機概述](https://docs.adobe.com/content/help/zh-Hant/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html)。

>[!CAUTION]
>
>請避免在父頁面和iframe上同時加入AppMeasurement程式庫。 這樣做會導致傳送多個影像要求、增加報告量以及增加計費伺服器呼叫的風險。

## 存取駐留在iframe中的AppMeasurement

您可以透過iframe物件存取AppMeasurement變數。 這些範例會設定[pageName](../vars/page-vars/pagename.md)，並使用兩種不同的方式呼叫[t()方法](../vars/functions/t-method.md)以參考iframe物件。

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## 從iframe中存取AppMeasurement

您可以從iframe中存取父頁面上的AppMeasurement變數。 此範例會設定[pageName](../vars/page-vars/pagename.md)，並使用[`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp)屬性呼叫[t()方法](../vars/functions/t-method.md)。

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## 使用`postMessage`和事件偵聽器

或者，您也可以使用`postMessage`和事件偵聽程式來設定變數。 此方法不需要直接參考iframe。

```js
// Place this code in your parent window
function listenMessage(e) {
    if(e.data == "Example page view call") {
        s.pageName = "Page name using postMessage";
        s.t();
    }
}
window.addEventListener("message", listenMessage, false);

// Place this code in the iframe
window.top.postMessage("Example page view call","https://example.com");
```

## 限制

* 和其他JavaScript程式碼一樣，iframe只能在網域和通訊協定相符時進行通訊。 如果iframe內容位於父項以外的不同網域，這些範例將無法運作。
* 如果AppMeasurement位於iframe中，[`referrer`](../vars/page-vars/referrer.md)變數會設為父URL，而非實際的反向連結URL。 您可以手動設定`referrer`變數來解決此問題。
* [Adobe Experience Cloud調試器](https://docs.adobe.com/content/help/zh-Hant/debugger/using/experience-cloud-debugger.html)無法識別在iframe中觸發的映像請求。
* Activity Map不會在iframe內點按的連結上顯示熱圖。 反之，會反白顯示整個iframe。
