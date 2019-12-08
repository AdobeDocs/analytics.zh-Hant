---
description: 系統會根據「JavaScript 適用的 AppMeasurement」檔案所設定的參數，自動追蹤檔案下載和退出連結。
keywords: Analytics Implementation
subtopic: Link tracking
title: s.tl() 函數 - 連結追蹤
topic: Developer and implementation
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# s.tl() 函數 - 連結追蹤

如果您的組織想對要追蹤的連結及其行為有更多的控制權，建議使用手動連結追蹤。使用 s.tl() 函數，手動傳送具有想要的確切內容之連結追蹤影像要求。如果您只需要基本連結追蹤，請參閱[設定變數](c-variables/configuration-variables.md)底下的 `s.trackDownloadLinks` 和 `s.trackExternalLinks`。無法自動追蹤自訂連結。

> [!NOTE]連結追蹤程式碼通常非常取決於您的特定網站和報表需求。Adobe 建議您採取先前的實施經驗或洽詢實施顧問，瞭解如何根據您的商業需求使用此功能。

## 語法和範例

基本語法:

`s.tl(`**`this`**`,`**`linkType`**`,`**`linkName`**`,`**`variableOverrides`**`,`**`doneAction`**`);`

機本範例:

```HTML
<!-- Basic HTML link example-->
<a href="example.html" onClick="s.tl(this,'o','Example link');">Click here</a>
```

```JavaScript
// Basic JavaScript link example
s.tl(this,'o','Example Link');
```

### this/true (必要)

第一個引數決定在離開頁面進行導覽前，瀏覽器是否最多等候 500 毫秒。如果影像要求在 500 毫秒內傳送，頁面會立即導覽至點按的連結。

* `this`: 等候最多 500 毫秒，讓 AppMeasurement 有時間傳送影像要求。預設值。
* `true`: 請勿等候。如果連結離開頁面進行導覽，有可能不會傳送影像要求。

只有在連結離開頁面時才需要延遲。

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType (必要)

視您要擷取的連結類型而定，第二個引數有三個有效值。這會決定影像要求要填入 Adobe Analytics 中的哪個維度。

* `d`: 檔案下載
* `e`: 退出連結
* `o`: 自訂連結

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName (必要)

此引數可為任何自訂值 (最多 100 個位元組)。這會決定報表中的維度值。

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides (選用)

可讓您變更單一呼叫的變數值。如果您使用 doneAction 引數且沒有變數覆寫，請使用 `null`。

### doneAction (選用)

指定在追蹤連結呼叫完成後要執行的導覽動作。需要使用 `s.useForcedLinkTracking` 和 `s.forcedLinkTrackingTimeout`。doneAction 變數可以是字串 `navigate`，該字串會使方法將 `document.location` 設為 `linkObject` 的 href 屬性。doneAction 變數也可以是允許進階自訂的函數。

若在錨記 事件中提供 `onClick``false`doneAction 的值，您必須在 `s.tl` 呼叫之後傳回 ，以防止進行預設瀏覽器導覽。若要反映預設行為並遵循 href 屬性所指定的 URL，請提供字串 `navigate` 做為 doneAction。您可以視需要選擇傳入自己的函數作為 doneAction，將此函數用於處理導覽事件。

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## 將 JavaScript 函數與連結追蹤搭配使用

您可以將連結追蹤程式碼併入頁面上或連結 JavaScript 檔案中所定義的獨立 JavaScript 函數。接著，即可在每個連結的 onClick 函數中發出呼叫。

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

在連結通常會被自動檔案下載或退出連結追蹤擷取的情形之下，該連結可能會被重複計數。例如，如果您正在自動追蹤 PDF 下載，`s.tl` 呼叫會造成重複下載計數:

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
