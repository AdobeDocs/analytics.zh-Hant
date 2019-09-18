---
description: 系統會根據「JavaScript 適用的 AppMeasurement」檔案所設定的參數，自動追蹤檔案下載和退出連結。
keywords: Analytics 實作
seo-description: 系統會根據「JavaScript 適用的 AppMeasurement」檔案所設定的參數，自動追蹤檔案下載和退出連結。
seo-title: s.tl() 函數 - 連結追蹤
solution: Analytics
subtopic: 連結追蹤
title: s.tl() 函數 - 連結追蹤
topic: 開發人員和實作
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 1ed1c6cd3fd6d29fa156cd4b2c4bdfe9120b3c61

---


# s.tl() 函數 - 連結追蹤

如果您的組織想要對要追蹤的連結及其行為擁有更多控制權，建議使用手動連結追蹤。 使用s.tl()函式，以手動方式傳送具有所需確切內容的連結追蹤影像要求。 如果基本連結追蹤是所需的，請參閱「設定變 `s.trackDownloadLinks` 數」 `s.trackExitLinks` 下 [方的資訊](c-variables/configuration-variables.md)。 自訂連結無法自動追蹤。

> [!NOTE] 連結追蹤程式碼通常會非常符合您的網站和報告需求。 Adobe建議您先前有實作經驗，或是建議實作顧問瞭解如何根據您的業務需求使用此功能。

## 語法與範例

基本語法：

`s.tl(`**`this`**`,`**`linkType`**`,`**`linkName`**`,`**`variableOverrides`**`,`**`doneAction`**`);`

基本範例：

```HTML
<!-- Basic HTML link example-->
<a href="example.html" onClick="s.tl(this,'o','Example link');">Click here</a>
```

```JavaScript
// Basic JavaScript link example
s.tl(this,'o','Example Link');
```

### this/true（必要）

第一個引數會決定瀏覽器在離開頁面前是否等待500毫秒。 如果影像要求在500毫秒之前傳送，頁面會立即導覽至點按的連結。

* `this`:等待最多500毫秒，讓AppMeasurement有時間傳送影像要求。 預設值。
* `true`:別等。 如果連結從頁面導覽出去，則可能不會傳送影像要求。

只有在連結離開頁面時，才需要延遲。

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType（必要）

第二個引數有三個有效值，這取決於您要擷取的連結類型。 它會決定影像要求填入的Adobe Analytics維度。

* `d`: 檔案下載
* `e`: 退出連結
* `o`:自訂連結

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName（必要）

此引數可以是任何自訂值，最多100位元組。 它會決定報表中的維度值。

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides（可選）

可讓您變更單一呼叫的變數值。 如果您使用doneAction引數且沒有變數覆寫，請使用 `null`。

### doneAction（選用）

指定在追蹤連結呼叫完成後要執行的導覽動作。 需要使用和 `s.useForcedLinkTracking``s.forcedLinkTrackingTimeout`。 The doneAction variable can be the string `navigate`, which causes the method to set `document.location` to the href attribute of `linkObject`. doneAction 變數也可以是允許進階自訂的函數。

若在錨記 事件中提供 `onClick``false`doneAction 的值，您必須在 `s.tl` 呼叫之後傳回 ，以防止進行預設瀏覽器導覽。To mirror the default behavior and follow the URL specified by the href attribute, provide a string of `navigate` as the doneAction. 您可以視需要選擇傳入自己的函數作為 doneAction，將此函數用於處理導覽事件。

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## 使用JavaScript函式與連結追蹤

您可以將連結追蹤程式碼整合為頁面上或連結JavaScript檔案中定義的獨立JavaScript函式。 然後，可在每個連結的onClick函式中進行呼叫。

```JavaScript
// Set in AppMeasurement file or page code
function trackClickInteraction(name){
    s.linkTrackVars='eVar16,eVar17';
    s.eVar16 = name;
    s.eVar17 = s.pageName;
    s.tl(true,'o',name);
}
```

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

## 避免重複連結計數 {#section_9C3F73DE758F4727943439DED110543C}

在連結通常是透過自動檔案下載或退出連結追蹤來擷取的情況下，連結可能會重複計數。 For example, if you are tracking PDF downloads automatically, an `s.tl` call results in a duplicate download count:

```JavaScript
function trackDownload(obj) {}
    s.tl(obj,'d','PDF Document');
}
```

若要確保不發生重複計數，請使用下列已修改的 JavaScript 函數:

```JavaScript
function linkCode(obj) {
    var lt = obj.href != null ? s.lt(obj.href) : "";
    if (lt=="") {
        s.tl(obj,'d','PDF Document');
    }
}
```
