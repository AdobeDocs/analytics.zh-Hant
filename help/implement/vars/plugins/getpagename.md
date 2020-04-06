---
title: getPageName
description: 從目前的網站路徑建立易讀的 pageName。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：getPageName

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getPageName` 外掛程式可為目前的 URL 建立易讀、好記的格式化版本。如果您想要在報表中輕鬆設定且理解的 [`pageName`](../page-vars/pagename.md) 值，Adobe 建議使用此外掛程式。如果您已有 `pageName` 變數的命名結構 (例如透過資料層)，就不需要此外掛程式。若您沒有其他解決方案可設定 `pageName` 變數，最好使用此外掛程式。

## 使用 Adobe Experience Platform Launch 擴充功能安裝外掛程式

Adobe 提供一個擴充功能，可讓您使用最常用的外掛程式。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. 安裝並發佈擴充 [!UICONTROL Common Analytics Plugins] 功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入程式庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 getPageName
1. 儲存並發佈規則的變更。

## 使用 Launch 自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. 展開accordion [!UICONTROL Configure tracking using custom code] ，以顯示按 [!UICONTROL Open Editor] 鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實施中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getPageName` 方法使用以下引數：

* **`si`** (選用，字串)：在代表網站 ID 的字串開頭插入的 ID。此值可以是數值 ID 或好記的名稱。未設定時，其預設值為目前的網域。
* **`qv`** (選用，字串)：以逗號分隔的查詢字串參數清單，若在 URL 中找到，便會新增至字串
* **`hv`** (選用，字串)：在 URL 雜湊中找到的逗號分隔參數清單，若在 URL 中找到，則會新增至字串
* **`de`** (選用，字串)：分割字串個別部分的分隔字元。預設為縱線字元 (`|`)。

此方法會傳回包含易記格式化版 URL 的字串。此字串通常會指派給 `pageName` 變數，但也可用於其他變數。

## 呼叫範例

### 範例 #1

如果目前的 URL 是...

```js
https://mail.google.com/mail/u/0/#inbox
```

...且下列程式碼執行...

```js
s.pageName = getPageName()
```

...s.pageName 的最終值將為：

```js
s.pageName = "mail.google.com|mail|u|0";
```

### 範例 #2

如果目前的 URL 是...

```js
https://mail.google.com/mail/u/0/#inbox
```

...且下列程式碼執行...

```js
s.pageName = getPageName("gmail")
```

...s.pageName 的最終值將為：

```js
s.pageName = "gmail|mail|u|0";
```

### 範例 #3

如果目前的 URL 是...

```js
https://www.google.com/
```

...且下列程式碼執行...

```js
s.pageName = getPageName()
```

...s.pageName 的最終值將為：

```js
s.pageName = "www.google.com|home"
```

**注意**：程式碼在不含路徑的 URL 上執行時，一律會將 &quot;home&quot; 值新增至傳回值的結尾

### 範例 #4

如果目前的 URL 是...

```js
https://www.google.com/
```

...且下列程式碼執行...

```js
s.pageName = getPageName("google","","","|")
```

...s.pageName 的最終值將為：

```js
s.pageName = "google|home"
```

### 範例 #5

如果目前的 URL 是...

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...且下列程式碼執行...

```js
s.pageName = getPageName()
```

...s.pageName 的最終值將為：

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

不過，如果改成下列程式碼執行...

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...s.pageName 的最終值將為：

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## 從舊版升級

getPageName 外掛程式的 4.0+ 版不依存於要執行的 Adobe Analytics AppMeasurement 物件 (即「s」物件) 之存在。如果您選擇升級為此版本，請務必移除呼叫中「s」物件的任何例項，以變更呼叫該外掛程式的程式碼。例如，請變更下列項目：

```js
s.pageName = s.getPageName();
```

...變更為這個:

```js
s.pageName = getPageName();
```

## 版本記錄

### 4.1 (2019 年 9 月 17 日)

* 將預設分隔字元值變更為縱線字元 (原為冒號 + 空格)。

### 4.0 (2018 年 5 月 22 日)

* 外掛程式全面重新分析/重寫
