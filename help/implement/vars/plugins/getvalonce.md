---
title: getValOnce
description: 防止 Analytics 變數連續設為相同值兩次。
feature: Variables
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 98%

---

# Adobe 外掛程式：getValOnce

{{plug-in}}

`getValOnce` 外掛程式可防止變數多次設為等於相同值。Adobe 建議您在訪客重新整理頁面或多次造訪指定頁面時，使用此外掛程式來移除重複發生次數。如果您不擔心 Analysis Workspace 中的「發生次數」量度，就不需要此外掛程式。

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getValOnce
1. Save and publish the changes to the rule.-->

## 使用自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]索引標籤，然後按一下 Adobe Analytics 擴充功能底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實作中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getValOnce v3.1 */
function getValOnce(vtc,cn,et,ep){var e=vtc,i=cn,t=et,n=ep;  if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.1"};var o=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();if(void 0!==o&&(o.contextData.getValOnce="3.1"),window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){var n=window.location.hostname,o=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){o=2<o?o:2;var r=n.lastIndexOf(".");if(0<=r){for(;0<=r&&1<o;)r=n.lastIndexOf(".",r-1),o--;r=0<r?n.substring(r):n}}if(g=r,i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var f=new Date;f.setTime(f.getTime()+6e4*t)}else f=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!=typeof cookieRead)&&cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),n=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>n?i.length:n)))?e:""},e){var i=i||"s_gvo",t=t||0,n="m"===n?6e4:864e5;if(e!==cookieRead(i)){var r=new Date;return r.setTime(r.getTime()+t*n),cookieWrite(i,e,0===t?0:r),e}}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getValOnce` 函數會使用以下引數：

* **`vtc`** (必要，字串)：要檢查的變數，查看它之前是否設為相同值
* **`cn`** (選用，字串)：包含要檢查之值的 Cookie 名稱。預設為 `"s_gvo"`
* **`et`** (選用，整數)：Cookie 的有效期，單位為天 (或分鐘，視 `ep` 引數而定)。預設為 `0`，在瀏覽器作業階段結束時到期
* **`ep`** (選用，字串)：只有在也設定了 `et` 引數時才設定此引數。如果您希望 `et` 引數在幾分鐘內而不是幾天內到期，請將此引數設為 `"m"`。預設為 `"d"`，以天為單位設定 `et` 引數。

如果 `vtc` 引數與 Cookie 值相符，此函數會傳回空字串。 如果 `vtc` 引數與 Cookie 值不符，此函數會將 `vtc` 引數傳回為字串。

## 範例

```js
// Prevent the same value from being passed in to the campaign variable more than once in a row for next 30 days
s.campaign = getValOnce(s.campaign,"s_campaign",30);

// Prevent the same value from being passed in to eVar2 more than once in a row for the browser session
s.eVar2 = getValOnce(s.eVar2,"s_ev2");

// Prevent the same value from being passed in to eVar8 more than once in a row for 10 minutes
s.eVar8 = getValOnce(s.eVar8,"s_ev8",10,"m");
```

## 版本記錄

### 3.1（2022年9月22日）

* 修正過期錯誤

### 3.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 2.01

* 已修正關於寫入 Cookie 的問題。

### 2.0

* 單點發行 (重新編譯，程式碼大小較小)。

### 1.1

* 新增選項，可透過 `t` 參數選擇有效期的分鐘數或天數。
* 修正用來限制 `k` 變數僅限外掛程式使用的範圍。這項變更可防止干擾頁面上的其他程式碼。
