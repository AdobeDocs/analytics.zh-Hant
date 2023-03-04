---
title: getPageName
description: 從目前的網站路徑建立易讀的 pageName。
feature: Variables
exl-id: a3aaeb5d-65cd-45c1-88bb-f3c0efaff110
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 100%

---

# Adobe 外掛程式：getPageName

{{plug-in}}

`getPageName` 外掛程式可為目前的 URL 建立易讀、好記的格式化版本。如果您想要在報表中輕鬆設定且理解的 [`pageName`](../page-vars/pagename.md) 值，Adobe 建議使用此外掛程式。如果您已有 `pageName` 變數的命名結構 (例如透過資料層)，就不需要此外掛程式。若您沒有其他解決方案可設定 `pageName` 變數，最好使用此外掛程式。

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
    * Action Type: Initialize getPageName
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
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getPageName` 函數會使用以下引數：

* **`si`** (選用，字串)：在代表網站 ID 的字串開頭插入的 ID。此值可以是數值 ID 或好記的名稱。未設定時，其預設值為目前的網域。
* **`qv`** (選用，字串)：以逗號分隔的查詢字串參數清單，若在 URL 中找到，便會新增至字串
* **`hv`** (選用，字串)：在 URL 雜湊中找到的逗號分隔參數清單，若在 URL 中找到，則會新增至字串
* **`de`** (選用，字串)：分割字串個別部分的分隔字元。預設為縱線字元 (`|`)。

此函數所傳回的字串會包含易用格式版本的 URL。 此字串通常會指派給 `pageName` 變數，但也可用於其他變數。

## 範例

```js
// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "mail.example.com|mail|u|0".
s.pageName = getPageName();

// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "example|mail|u|0".
s.pageName = getPageName("example");

// Given the URL https://www.example.com/, sets the page variable to "www.example.com|home".
// When the code runs on a URL that does not contain a path, it always adds the value of "home" to the end of the return value.
s.pageName = getPageName();

// Given the URL https://www.example.com/, sets the page variable to "example|home".
s.pageName = getPageName("example","","","|");

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "www.example.com|en|booking|room-booking.html".
s.pageName = getPageName();

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "example: en: booking: room-booking.html: cid=1235: arrive=05-26: numGuests=2"
s.pageName = getPageName("example","cid","arrive,numGuests",": ");
```

## 從舊版升級

`getPageName` 外掛程式的 4.0+ 版不取決於 Adobe Analytics AppMeasurement 物件 (即「`s`」物件) 的存在。 如果您升級至此版本，請務必移除呼叫中 `s` 物件的任何實例，以變更呼叫該外掛程式的程式碼。 例如，將 `s.getPageName();` 變更為 `getPageName();`。

## 版本記錄

### 4.2 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 4.1 (2019 年 9 月 17 日)

* 將預設分隔字元值變更為縱線字元 (原為冒號 + 空格)。

### 4.0 (2018 年 5 月 22 日)

* 外掛程式全面重新分析/重寫
