---
title: getPreviousValue
description: 取得最後一個傳遞至變數的值。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe外掛程式：getPreviousValue

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外 `getPreviousValue` 掛程式可讓您將變數設定為先前點擊上設定的值。 如果您的實作包含目前點擊中的所有所需值，則不需要此外掛程式。

## 使用Adobe Experience Platform Launch擴充功能安裝增效模組

Adobe提供擴充功能，讓您使用最常用的增效模組。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「目錄 [!UICONTROL 」按鈕]
1. 安裝和發佈 [!UICONTROL Common Analytics Plugins] extension
1. 對於您想要使用外掛程式的任何「啟動規則」，請新增具有下列設定的動作：
   * 擴充功能：常見Analytics外掛程式
   * 動作類型：初始化addProductEvar
1. 儲存並發佈規則的變更

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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `getPreviousValue` 法使用以下引數：

* **`v`**（字串，必要）:具有您要傳遞至下一個影像要求之值的變數。 用來擷取上`s.pageName`一頁值的通用變數。
* **`c`**（字串，選用）:儲存值的Cookie名稱。  如果未設定此引數，則預設為`"s_gpv"`。

當您呼叫此方法時，它會傳回Cookie中包含的字串值。 此外掛程式會重設Cookie有效期，並從引數指派變數 `v` 值。 未活動30分鐘後，Cookie即過期。

## 呼叫範例

### 範例#1

下列程式碼……

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* 首先，將s.prop7設定為先前影像要求中傳入s.pageName的值（即儲存在&quot;gpv_Page&quot; cookie中的值）
* 然後程式碼會重設&quot;gpv_Page&quot; Cookie，使其等於s.pageName的目前值
* 如果此程式碼執行時未設定s.pageName，則程式碼會重設Cookie目前值的有效期

### 範例#2

下列程式碼會將s.prop7設定為傳入s.pageName的最後一個值，但只有在s.events中也包含event1時（如在呼叫發生時透過inList外掛程式所判斷），才會設定。

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 範例#3

下列程式碼會將s.prop7設為傳入s.pageName的最後一個值，但僅當目前在頁面上同時設定s.pageName時。

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 範例#4

下列程式碼會將s.eVar10設定為等於先前影像要求中傳入s.eVar1的值。   先前的eVar1值原本會包含在&quot;s_gpv&quot; cookie中。  然後程式碼會將&quot;s_gpv&quot; cookie設定為s.eVar1的目前值。

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## 不太可能的怪癖

如果與v引數相關聯的變數設為新值，而getPreviousValue外掛程式會執行，但Analytics伺服器呼叫不會同時傳送，則新v引數值在下次外掛程式執行時仍會被視為「上一個值」。
例如，假設下列程式碼會在瀏覽的第一頁執行：

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

此程式碼會產生伺服器呼叫，其中pageName引數等於&quot;home&quot;，且p7(prop7)引數未設定。  但是，對s.getPreviousValue的呼叫會儲存s.pageName的值(即&quot;home&quot;)中指定的Cookie（亦即&quot;gpv_Page&quot; Cookie）。
現在，假設緊接著在同一頁上，會執行下列程式碼（因任何原因）:

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

由於s.t()函式未在此程式碼區塊中執行，因此將不會建立其他影像要求。  不過，當s.getPreviousValue()函式程式碼此時執行時，s.prop7會設定為等於s.pageName的先前值(即&quot;home&quot;)，然後將儲存s.pageName的新值(即&quot;happy value&quot;)。
假設訪客導覽至不同頁面，且此頁面上會執行下列程式碼：

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

當s.t()呼叫函式執行時，它會建立影像要求，其中s.pageName=&quot;page 2&quot;和s.prop7等於&quot;happy value&quot;，此為上次呼叫getPreviousValue時的s.pageName值。   即使「home」是傳入s.pageName的第一個值，任何實際影像要求中都從未包含「home」的s.prop7值。

## 版本記錄

### v2.0（2019年10月7日）

* 點數發行（完整邏輯重寫）。
