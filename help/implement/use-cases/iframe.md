---
title: 搭配 iframe 使用 AppMeasurement
description: 在 iframe 內時，存取 iframe 或上層頁面內的 Adobe Analytics 變數。
feature: Implementation Basics
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 100%

---

# 搭配 iframe 使用 AppMeasurement

您可以參照來自下層和上層 iframe 的 AppMeasurement 變數。 您必須在 AppMeasurement 資料庫存在的相同位置定義所有變數。 以下範例說明如何在 iframe 內外設定基本 AppMeasurement 變數和方法。

如果您使用 Adobe Experience Platform 中的標記，請確定追蹤器物件可在全域範圍存取。 請參閱「[Adobe Analytics 擴充功能概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html)」。

>[!CAUTION]
>
>避免同時在上層頁面和 iframe 中包含 AppMeasurement 資料庫。 這樣做會帶來傳送多個影像要求、誇大報告及增加可計費伺服器呼叫的風險。

## 存取位在 iframe 內的 AppMeasurement

您可以透過 iframe 物件來存取 AppMeasurement 變數。 這些範例會使用參照 iframe 物件的兩個不同方式來設定 [pageName](../vars/page-vars/pagename.md) 及呼叫 [t() 方法](../vars/functions/t-method.md)。

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## 存 iframe 內存取 AppMeasurement

您可以從 iframe 內存取上層頁面上的 AppMeasurement 變數。 此範例會使用 [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp) 屬性設定 [pageName](../vars/page-vars/pagename.md) 及呼叫 [t() 方法](../vars/functions/t-method.md)。

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## 使用 `postMessage` 和事件接聽程式

另外，您也可以使用 `postMessage` 和事件接聽程式來設定變數。 此方法不需要直接參照 iframe。

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

* 就像其他 JavaScript 程式碼一樣，iframe 只能在網域和通訊協定相符時通訊。 如果 iframe 內容位在與上層不同的網域中，這些範例就沒有作用。
* 如果 AppMeasurement 位在 iframe 內，則 [`referrer`](../vars/page-vars/referrer.md) 變數會設定為上層 URL，而不是實際參照的 URL。 您可以手動設定 `referrer` 變數來解決此問題。
* [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) 無法辨識在 iframe 內觸發的影像要求。
* Activity Map 不會在 iframe 內點擊的連結上方顯示熱度圖。 而是會標示整個 iframe。
