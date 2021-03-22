---
title: getNewRepeat
description: 追蹤新訪客與重複訪客的活動。
translation-type: tm+mt
source-git-commit: 9d44226202cd690d069f9c0c85c8af2ef8fd0106
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 99%

---


# Adobe 外掛程式：getNewRepeat

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getNewRepeat` 外掛程式可讓您判斷網站訪客是新訪客還是在指定天數內回訪的重複訪客。如果您想要使用自訂天數將訪客識別為「new」，Adobe 建議使用此外掛程式。如果 Analysis Workspace 中的「新增/重複」訪客維度符合您組織的需求，就不需要此外掛程式。

## 使用 Adobe Experience Platform Launch 擴充功能安裝外掛程式

Adobe 提供一個擴充功能，可讓您使用最常用的外掛程式。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下[!UICONTROL 「目錄」]按鈕
1. 安裝並發佈[!UICONTROL 常用 Analytics 外掛程式]擴充功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入程式庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 getNewRepeat
1. 儲存並發佈規則的變更。

## 使用 Launch 自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 擴充功能底下的[!UICONTROL 「設定」]按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實施中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getNewRepeat` 方法使用以下引數：

* **`d`** (整數，選用)：將訪客重設回 `"New"` 的訪客距離上次造訪需間隔的最小天數。如果未設定此引數，其預設值為 30 天。

如果外掛程式設定的 Cookie 不存在或已過期，此方法會傳回 `"New"` 值。如果外掛程式設定的 Cookie 存在，且自目前點擊以來的時間量及 Cookie 中設定的時間超過 30 分鐘，則會傳回 `"Repeat"` 值。此方法會為整個造訪傳回相同值。

此外掛程式使用 `"s_nr[LENGTH]"` Cookie，其中的 `[LENGTH]` 等於 `d` 引數。Cookie 包含代表訪客 (`"New"` 或 `"Repeat"`) 目前時間和狀態的 Unix 時間戳記。

## 呼叫範例

### 範例 #1

下列程式碼會為新訪客將 s.eVar1 設為等於「New」值，並在訪客造訪網站的其餘時間內，持續將 s.eVar1 設為等於「New」值 (每次新呼叫)。

```js
s.eVar1=s.getNewRepeat();
```

### 範例 #2

如果訪客自上次呼叫 s.getNewRepeat() 以來的 31 分鐘到 30 天內回訪，下列程式碼會在訪客造訪網站的其餘時間內，將 s.eVar1 設為等於「Repeat」值，並繼續將 s.eVar1 設為等於「Repeat」的值 (每次新呼叫)。

```js
s.eVar1=s.getNewRepeat();
```

### 範例 #3

如果訪客自上次呼叫 s.getNewRepeat() 以來至少 30 天未造訪網站，下列程式碼會在訪客造訪網站的其餘時間內，將 s.eVar1 設為等於「New」值，並持續將 s.eVar1 設為等於「New」值 (每次新呼叫)。

```js
s.eVar1=s.getNewRepeat();
```

### 範例 #4

如果訪客自上次呼叫 s.getNewRepeat() 以來的 31 分鐘到 365 天 (即 1 年) 內回訪，下列程式碼會在訪客造訪網站的其餘時間內，將 s.eVar1 設為等於「Repeat」值，並繼續將 s.eVar1 設為等於「Repeat」的值 (每次新呼叫)。

```js
s.eVar1=s.getNewRepeat(365);
```

### 範例 #5

如果訪客自上次呼叫 s.getNewRepeat() 以來至少 365 天 (即 1 年) 未造訪網站，下列程式碼會在訪客造訪網站的其餘時間內，將 s.eVar1 設為等於「New」值，並持續將 s.eVar1 設為等於「New」值 (每次新呼叫)。

```js
s.eVar1=s.getNewRepeat(365);
```

## 版本記錄

### 3.0（2021年3月19日）

* 已新增版本號碼作為內容資料。

### 2.1 (2019 年 9 月 30 日)

* 重新排列 JavaScript 邏輯以縮小外掛程式大小

### 2.0 (2018 年 4 月 16 日)

* 以較小的程式碼大小重新編譯
* 移除為 Cookie 命名以儲存造訪資訊的功能。外掛程式現在會根據傳入 `d` 引數的值，以動態方式為 Cookie 命名。
