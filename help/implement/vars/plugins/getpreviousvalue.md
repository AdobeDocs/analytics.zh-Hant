---
title: getPreviousValue
description: 取得最後一個傳至變數的值。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe 外掛程式：getPreviousValue

>[!IMPORTANT] 此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getPreviousValue` 外掛程式可讓您將變數設定為先前點擊上設定的值。如果您的實施包含目前點擊中的所有所需值，就不需要此外掛程式。

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
   * 動作類型：初始化 getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getPreviousValue` 方法使用以下引數：

* **`v`** (字串，必要)：具有您要傳遞至下一個影像要求之值的變數。用來擷取上一頁值的通用變數為 `s.pageName`。
* **`c`** (字串，選用)：儲存值的 Cookie 名稱。如果未設定此引數，其預設值為 `"s_gpv"`。

呼叫此方法時，它會傳回 Cookie 中包含的字串值。此外掛程式會重設 Cookie 有效期，並從 `v` 引數指派變數值。閒置 30 分鐘後，Cookie 便會到期。

## 呼叫範例

### 範例 #1

下列程式碼...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* 首先，將 s.prop7 設為等於先前影像要求中傳入 s.pageName 的值 (即儲存在「gpv_Page」Cookie 中的值)
* 然後程式碼會重設「gpv_Page」Cookie，使其等於 s.pageName 的目前值
* 如果此程式碼執行時未設定 s.pageName，則程式碼會重設 Cookie 目前值的有效期

### 範例 #2

下列程式碼會將 s.prop7 設為等於傳入 s.pageName 的最後一個值，但僅限於 s.events 中也包含 event1 時的情況下 (呼叫發生時透過 inList 外掛程式所判斷)。

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 範例 #3

下列程式碼會將 s.prop7 設為等於傳入 s.pageName 的最後一個值，但僅限於目前同時在頁面上設定 s.pageName 的情況下。

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 範例 #4

下列程式碼會將 s.eVar10 設為等於先前影像要求中傳入 s.eVar1 的值。先前的 eVar1 值原本包含在「s_gpv」Cookie 中。然後程式碼會將「s_gpv」Cookie 設為等於 s.eVar1 的目前值。

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## 不太可能發生的巧合情況

如果將與 v 引數相關聯的變數設為新值，且 getPreviousValue 外掛程式執行中，但 Analytics 伺服器呼叫沒有同時傳送，則下次外掛程式執行時新的 v 引數值仍會被視為「上一個值」。例如，假設下列程式碼會在造訪的第一頁上執行：

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

此程式碼會產生一個伺服器呼叫，其中 pageName 引數等於「home」，且 p7 (prop7) 引數未設定。但是，對 s.getPreviousValue 發出的呼叫會儲存 s.pageName 的值 (即「home」) 中指定的 Cookie (亦即「gpv_Page」Cookie)。現在，假設緊接著在同一頁上執行下列程式碼 (基於任何原因)：

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

由於 s.t() 函數沒有在此程式碼區塊中執行，因此將不會建立其他影像要求。不過，這次 s.getPreviousValue() 函數程式碼執行時，s.prop7 會設為等於 s.pageName 的先前值 (即「home」)，然後儲存 s.pageName 的新值 (即「happy value」)。假設訪客導覽至不同頁面，且在此頁面上執行下列程式碼：

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

s.t() 呼叫函數執行時會建立影像要求，要求中 s.pageName =&quot;page 2&quot; 而 s.prop7 等於 &quot;happy value&quot;，這是上次呼叫 getPreviousValue 時的 s.pageName 值。雖然 &quot;home&quot;是傳入 s.pageName 的第一個值，但任何實際影像要求中都未曾包含 &quot;home&quot; 的 s.prop7 值。

## 版本記錄

### v2.0 (2019 年 10 月 7 日)

* 單點發行 (全面邏輯重寫)。
