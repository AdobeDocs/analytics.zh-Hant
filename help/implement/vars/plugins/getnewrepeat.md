---
title: getNewRepeat
description: 追蹤新訪客與重複訪客的活動。
feature: Variables
exl-id: 8f64e176-1926-4cb1-bfae-09d7e2c015ae
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 100%

---

# Adobe 外掛程式：getNewRepeat

{{plug-in}}

`getNewRepeat` 外掛程式可讓您判斷網站訪客是新訪客還是在指定天數內回訪的重複訪客。如果您想要使用自訂天數將訪客識別為「new」，Adobe 建議使用此外掛程式。如果 Analysis Workspace 中的「新增/重複」訪客維度符合您組織的需求，就不需要此外掛程式。

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
    * Action Type: Initialize getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getNewRepeat` 函數會使用以下引數：

* **`d`** (整數，選用)：將訪客重設回 `"New"` 的訪客距離上次造訪需間隔的最小天數。如果未設定此引數，其預設值為 30 天。

如果外掛程式設定的 Cookie 不存在或已過期，此函數會傳回 `"New"` 值。 如果外掛程式設定的 Cookie 存在，且自目前點擊以來的時間量及 Cookie 中設定的時間超過 30 分鐘，則會傳回 `"Repeat"` 值。 此函數會為整個造訪傳回相同的值。

此外掛程式使用 `"s_nr[LENGTH]"` Cookie，其中的 `[LENGTH]` 等於 `d` 引數。Cookie 包含代表訪客 (`"New"` 或 `"Repeat"`) 目前時間和狀態的 Unix 時間戳記。

## 範例

```js
// Sets eVar1 to "New" if it is the visitor's first visit to the site, or they have not visited in at least 30 days. Otherwise, sets eVar1 to "Repeat".
s.eVar1 = getNewRepeat();

// Sets eVar2 to "New" if it is the visitor's first visit to the site, or they have not visited in at least a year (365 days). Otherwise, sets eVar2 to "Repeat".
s.eVar2 = getNewRepeat(365);
```

## 版本記錄

### 3.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 2.1 (2019 年 9 月 30 日)

* 重新排列 JavaScript 邏輯以縮小外掛程式大小

### 2.0 (2018 年 4 月 16 日)

* 以較小的程式碼大小重新編譯
* 移除為 Cookie 命名以儲存造訪資訊的功能。外掛程式現在會根據傳入 `d` 引數的值，以動態方式為 Cookie 命名。
