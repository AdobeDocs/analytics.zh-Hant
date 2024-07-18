---
title: getPreviousValue
description: 取得最後一個傳至變數的值。
feature: Variables
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 77%

---

# Adobe 外掛程式：getPreviousValue

{{plug-in}}

`getPreviousValue` 外掛程式可讓您將變數設定為先前點擊上設定的值。如果您的實施包含目前點擊中的所有所需值，就不需要此外掛程式。

## 使用Web SDK擴充功能安裝外掛程式

Adobe提供擴充功能，可讓您搭配Web SDK使用最常用的外掛程式。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下左側的&#x200B;**[!UICONTROL 標籤]**，然後按一下所需的標籤屬性。
1. 按一下左側的&#x200B;**[!UICONTROL 擴充功能]**，然後按一下&#x200B;**[!UICONTROL 目錄]**&#x200B;標籤
1. 尋找並安裝&#x200B;**[!UICONTROL 常用Web SDK外掛程式]**&#x200B;擴充功能。
1. 按一下左側的&#x200B;**[!UICONTROL 資料元素]**，然後按一下所需的資料元素。
1. 使用下列設定來設定所需的資料元素名稱：
   * 擴充功能：常見Web SDK外掛程式
   * 資料元素： `getPreviousValue`
1. 在右側設定所要的引數。
1. 儲存並發佈資料元素的變更。

## 手動實作Web SDK安裝外掛程式

此外掛程式尚不支援在Web SDK的手動實作中使用。

## 使用Adobe Analytics擴充功能安裝外掛程式

Adobe提供擴充功能，可讓您搭配Adobe Analytics使用最常用的外掛程式。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 擴充功能]標記，然後按一下[!UICONTROL 「目錄」]按鈕
1. 安裝並發佈[!UICONTROL 常用 Analytics 外掛程式]擴充功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入資料庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 getPreviousValue
1. 儲存並發佈規則的變更。

## 使用自訂程式碼編輯器安裝外掛程式

如果您不想使用常見Analytics外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]索引標籤，然後按一下 Adobe Analytics 擴充功能底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實作中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getPreviousValue` 函數會使用以下引數：

* **`v`** (字串，必要)：具有您要傳遞至下一個影像要求之值的變數。用來擷取上一頁值的通用變數為 `s.pageName`。
* **`c`** (字串，選用)：儲存值的 Cookie 名稱。如果未設定此引數，其預設值為 `"s_gpv"`。

當您呼叫此方法時，它會傳回 Cookie 中包含的字串值。 此外掛程式會重設 Cookie 有效期，並從 `v` 引數指派變數值。閒置 30 分鐘後，Cookie 便會到期。

## 範例

```js
// 1. Sets prop7 to the cookie value contained in gpv_Page
// 2. Resets the gpv_Page cookie value to the page variable
// 3. If the page variable is not set, reset the gpv_Page cookie expiration
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if event1 is in the events variable.
if(inList(s.events,"event1")) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if the page variable is currently set on the page
if(s.pageName) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets eVar10 equal to the cookie value contained in s_gpv, then sets the s_gpv cookie to the current value of eVar1.
s.eVar10 = getPreviousValue(s.eVar1);
```

## 不太可能發生的巧合

如果將與 `v` 引數相關聯的變數設為新值，且 `getPreviousValue` 外掛程式執行中，但未同時傳送 Analytics 伺服器呼叫，則下次外掛程式執行時，新的 `v` 引數值仍會被視為「上一個值」。
例如，假設下列程式碼會在造訪的第一頁上執行：

```js
s.pageName = "Home";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

此程式碼會產生伺服器呼叫，其中 `pageName` 為「Home」且未設定 prop7。 然而，`getPreviousValue` 的呼叫會將 `pageName` 的值儲存在 `gpv_Page` Cookie 中。 假設下列程式碼緊接著在相同頁面上執行：

```js
s.pageName = "New value";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
```

由於 `t()` 函數並未在此程式碼區塊中執行，因此不會傳送另一個影像要求。 然而，這次執行 `getPreviousValue` 函數程式碼時，`prop7` 設定為 `pageName` 的上一個值 (「Home」)，然後將 `pageName` 的新值 (「New value」) 儲存在 `gpv_Page` Cookie 中。 接下來，假設訪客導覽至另一個頁面，且在此頁面上執行下列程式碼：

```js
s.pageName = "Page 2";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

當 `t()` 函數執行時，它會建立影像要求，其中 `pageName` 為「Page 2」，且 `prop7` 為「New value」，也就是上次呼叫 `getPreviousValue` 時的 `pageName` 值。 雖然「Home」是傳遞給 `pageName` 的第一個值，但是影像要求中從未包含 `"Home"` 的 `prop7` 值。

## 版本記錄

### 3.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### v2.0 (2019 年 10 月 7 日)

* 單點發行 (全面邏輯重寫)。
