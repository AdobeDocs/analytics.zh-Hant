---
title: getAndPersistValue
description: 儲存值以便稍後隨時擷取。
exl-id: b562f9ad-3844-4535-b729-bd3f63f6f0ae
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '934'
ht-degree: 100%

---

# Adobe 外掛程式：getAndPersistValue

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getAndPersistValue` 外掛程式可讓您將值儲存在 Cookie 中，以便稍後造訪時擷取。它的角色與 Adobe Experience Platform Launch 的[!UICONTROL 「儲存期間」]功能類似。設定變數後，如果您想在後續的點擊中自動讓 Analytics 變數保留相同的值，Adobe 建議您使用此外掛程式。如果 Launch 的[!UICONTROL 「儲存期間」]功能已足夠，或是您不需要在後續點擊中將變數設定及保留相同的值，則不需要使用此外掛程式。eVar 的內建永續性不需要使用此外掛程式，因為這些變數由 Adobe 保留在伺服器端。

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
   * 動作類型：初始化 getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getAndPersist` 方法使用以下引數：

* **`vtp`** (必要)：要在頁面之間保留的值
* **`cn`** (選用)：要儲存值的 Cookie 名稱。如果此引數未設定，系統會將 Cookie 命名為 `"s_gapv"`
* **`ex`** (選用)：Cookie 過期的天數。如果此引數為 `0` 或未設定，Cookie 會在造訪結束時過期 (閒置 30 分鐘)。

如果 `vtp` 引數中的變數已設定，外掛程式會設定 Cookie，然後傳回 Cookie 值。如果 `vtp` 引數中的變數未設定，外掛程式只會傳回 Cookie 值。

## 範例

### 範例 #1

下列程式碼會將 eVar21 設定為等於「hello」的值。接著，程式碼會將 ev21gapv Cookie (將於 28 天後過期) 設定為等於 eVar21 的值 (即「hello」)。最後，程式碼會將 eVar21 設定 (重設) 為等於 ev21gapv Cookie 的值。

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 範例 #2

假設 eVar21 尚未在目前頁面上設定，但是在過去 28 天內曾在先前的頁面上設定為等於「hello」的值。下列程式碼只會將 eVar21 設定為等於 ev21gapv Cookie 的值 (即「hello」)。它不會重設 ev21gapv Cookie，因為在呼叫函數之前，eVar21 尚未在目前頁面上設定。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 範例 #3

假設 eVar21 尚未在目前頁面上設定，但是在過去 28 天內曾在先前的頁面上設定為等於「hello」的值。下列程式碼只會將 prop35 設定為等於 ev21gapv Cookie 的值 (即「hello」)。它不會設定 eVar21。

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 範例 #4

下列程式碼會將 eVar21 設定為等於「howdy」的值。接著，程式碼會將 ev21gapv Cookie (將於 28 天後過期) 設定 (重設) 為等於 eVar21 的值 (即「howdy」)。最後，程式碼會將 prop35 設定為等於 ev21gapv Cookie 的值 (即「howdy」)。

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 範例 #5

假設 s.eVar21 在過去 28 天內未曾在任何頁面上設定。下列程式碼會將 s.eVar21 設定為無值，因為 ev21gapv Cookie 自從上次設定後已過期 28 天。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 範例 #6

下列程式碼會將 eVar30 設定為等於「shopping」的值。接著，代碼會將 s_gapv Cookie (將於瀏覽器工作階段結束後過期) 設定為等於 s.eVar30 的值 (即「shopping」)。最後，它會將 s.eVar30 設定為等於 s_gapv Cookie 的值 (也就是說 getAndPersistValue 呼叫會傳回 s_gapv Cookie的值，即此例中的「shopping」)。

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

在工作階段期間內，如果 s.eVar30 未於其他任何顯示的頁面上設定為明確的值，但是透過下列程式碼設定 (在 doPlugins 中)...

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30 將設為等於「shopping」的值 (即 s_gapv cookie 留存的值)

## 版本記錄

### 3.0 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 2.0 (2018 年 4 月 16 日)

* 單點發行 (程式碼大小較小)
* 將 0 傳入 `ex` 引數現在會強迫在閒置 30 分鐘後過期，而不是在瀏覽器工作階段結束後過期。

### 1.0 (2016 年 1 月 18 日)

* 首次發行。
