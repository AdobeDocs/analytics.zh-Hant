---
title: getValOnce
description: 防止 Analytics 變數連續設為相同值兩次。
feature: Variables
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 93%

---

# Adobe 外掛程式：getValOnce

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getValOnce` 外掛程式可防止變數多次設為等於相同值。Adobe 建議您在訪客重新整理頁面或多次造訪指定頁面時，使用此外掛程式來移除重複發生次數。如果您不擔心 Analysis Workspace 中的「發生次數」量度，就不需要此外掛程式。

## 使用Web SDK或Adobe Analytics擴展安裝插件

Adobe 提供一個擴充功能，可讓您使用最常用的外掛程式。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 前往[!UICONTROL 擴充功能]標記，然後按一下[!UICONTROL 「目錄」]按鈕
1. 安裝並發佈[!UICONTROL 常用 Analytics 外掛程式]擴充功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入資料庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 getValOnce
1. 儲存並發佈規則的變更。

## 使用自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 擴充功能底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實作中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getValOnce v3.0 (Requires AppMeasurement) */
function getValOnce(vtc,cn,et,ep){var e=vtc,k=cn,l=et,m=ep;if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.0"};var c=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,a;b<window.s_c_il.length;b++)if(a=window.s_c_il[b],a._c&&"s_c"===a._c)return a}();"undefined"!==typeof c&&(c.contextData.getValOnce="3.0");window.cookieWrite=window.cookieWrite||function(b,a,d){if("string"===typeof b){var h=window.location.hostname,c=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){c=2<c?
c:2;var f=h.lastIndexOf(".");if(0<=f){for(;0<=f&&1<c;)f=h.lastIndexOf(".",f-1),c--;f=0<f?h.substring(f):h}}g=f;a="undefined"!==typeof a?""+a:"";if(d||""===a)if(""===a&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return b&&(document.cookie=encodeURIComponent(b)+"="+encodeURIComponent(a)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(b)===a:!1}};window.cookieRead=window.cookieRead||function(b){if("string"===
typeof b)b=encodeURIComponent(b);else return"";var a=" "+document.cookie,d=a.indexOf(" "+b+"="),c=0>d?d:a.indexOf(";",d);return(b=0>d?"":decodeURIComponent(a.substring(d+2+b.length,0>c?a.length:c)))?b:""};return e&&(k=k||"s_gvo",l=l||0,m="m"===m?6E4:864E5,e!==this.c_r(k))?(c=new Date,c.setTime(c.getTime()+l*m),cookieWrite(k,e,0===l?0:m),e):""};
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

### 3.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 2.01

* 已修正關於寫入 Cookie 的問題。

### 2.0

* 單點發行 (重新編譯，程式碼大小較小)。

### 1.1

* 新增選項，可透過 `t` 參數選擇有效期的分鐘數或天數。
* 修正用來限制 `k` 變數僅限外掛程式使用的範圍。這項變更可防止干擾頁面上的其他程式碼。
