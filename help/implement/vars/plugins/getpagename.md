---
title: getPageName
description: 從目前的網站路徑建立容易閱讀的pageName。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe外掛程式：getPageName

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `getPageName` 程式可建立目前URL的易讀、好記的格式化版本。 如果您想要在報表中輕鬆設定和 `pageName` 瞭解的值，Adobe建議使用此外掛程式。 如果您已有變數的命名結構（例如透過資料層）, `pageName` 就不需要此外掛程式。 當您沒有其他解決方案來設定變數時，最好使用此變 `pageName` 數。

## 使用Adobe Experience Platform Launch擴充功能安裝增效模組

Adobe提供擴充功能，讓您使用最常用的增效模組。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「目錄 [!UICONTROL 」按鈕]
1. 安裝和發佈 [!UICONTROL Common Analytics Plugins] extension
1. 如果您尚未建立，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心——載入的程式庫（頁面頂端）
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常見Analytics外掛程式
   * 動作類型：初始化getPageName
1. 儲存並發佈規則的變更。

## 使用Launch自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，則可使用自訂程式碼編輯器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下 [!UICONTROL Adobe Analytics延伸模組下的「設定] 」按鈕。
1. 展開「使 [!UICONTROL 用自訂程式碼] accordion設定追蹤」，此會顯示 [!UICONTROL 「開啟編輯器] 」按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式碼貼入編輯視窗。
1. 儲存變更並發佈至Analytics擴充功能。

## 使用AppMeasurement安裝外掛程式

在Analytics追蹤物件實例化（使用）後，將下列程式碼複製並貼至AppMeasurement檔案中的任 `s_gi`何位置。 保留您實作中的程式碼注釋和版本號碼，有助於Adobe疑難排解任何潛在問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `getPageName` 法使用以下引數：

* **`si`**（可選，字串）:插入字串開頭的ID，代表網站的ID。 此值可以是數值ID或好記名稱。 未設定時，它預設為當前域。
* **`qv`**（可選，字串）:以逗號分隔的查詢字串參數清單，若在URL中找到，則會新增至字串
* **`hv`**（可選，字串）:在URL雜湊中找到的逗號分隔參數清單，若在URL中找到，則會新增至字串
* **`de`**（可選，字串）:分隔字元，以分割字串的個別部分。 預設為管道(`|`)。

方法會傳回包含易記格式化版URL的字串。 此字串通常指派給變 `pageName` 數，但也可用於其他變數。

## 呼叫範例

### 範例#1

如果目前的URL是……

```js
https://mail.google.com/mail/u/0/#inbox
```

...下列程式碼會執行……

```js
s.pageName = getPageName()
```

...s.pageName的最終值將為：

```js
s.pageName = "mail.google.com|mail|u|0";
```

### 範例#2

如果目前的URL是……

```js
https://mail.google.com/mail/u/0/#inbox
```

...下列程式碼會執行……

```js
s.pageName = getPageName("gmail")
```

...s.pageName的最終值將為：

```js
s.pageName = "gmail|mail|u|0";
```

### 範例#3

如果目前的URL是……

```js
https://www.google.com/
```

...下列程式碼會執行……

```js
s.pageName = getPageName()
```

...s.pageName的最終值將為：

```js
s.pageName = "www.google.com|home"
```

**注意**:當程式碼在不含路徑的URL上執行時，一律會將&quot;home&quot;值新增至傳回值的結尾

### 範例#4

如果目前的URL是……

```js
https://www.google.com/
```

...下列程式碼會執行……

```js
s.pageName = getPageName("google","","","|")
```

...s.pageName的最終值將為：

```js
s.pageName = "google|home"
```

### 範例#5

如果目前的URL是……

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...下列程式碼會執行……

```js
s.pageName = getPageName()
```

...s.pageName的最終值將為：

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

不過，如果下列程式碼改為執行……

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...s.pageName的最終值將為：

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## 從舊版升級

getPageName外掛程式的4.0+版並不取決於要執行的Adobe Analytics的AppMeasurement物件（即「s」物件）是否存在。  如果您選擇升級至此版本，請務必從呼叫中移除&quot;s&quot;物件的任何例項，以變更呼叫外掛程式的程式碼。
例如，請變更下列項目：

```js
s.pageName = s.getPageName();
```

...變更為這個:

```js
s.pageName = getPageName();
```

## 版本記錄

### 4.1（2019年9月17日）

* 將預設分隔字元值變更為垂直號字元（從冒號+空格）。

### 4.0（2018年5月22日）

* 外掛程式的完整重新分析／重寫
