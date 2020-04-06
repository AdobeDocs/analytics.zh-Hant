---
title: tl
description: 傳送連結追蹤呼叫給 Adobe。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# tl

`tl()` 方法是 Adobe Analytics 的重要核心元件。它會使用頁面上定義的所有 Analytics 變數、編譯成影像要求，然後將該資料傳送至 Adobe 資料收集伺服器。它的作用與 [`t()`](t-method.md) 方法類似，不過此方法不會增加頁面檢視。若要追蹤連結和其他不視為完整頁面載入的元素，這個方法非常有用。

如果 [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) 或 [`trackExternalLinks`](../config-vars/trackexternallinks.md) 已啟用，AppMeasurement 會自動呼叫 `tl()` 方法，以便傳送下載連結和退出連結追蹤資料。如果您的組織想進一步控制要追蹤的連結與其行為，可以手動呼叫 `tl()` 方法。自訂連結只能手動追蹤。

## Adobe Experience Platform Launch 中的連結追蹤呼叫

Launch 有設定連結追蹤呼叫的專用位置。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
1. 按一下所需的屬性。
1. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
1. Under [!UICONTROL Actions], click the &#39;+&#39; icon
1. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
1. 按一下 `s.tl()` 選擇鈕。

您不能在 Launch 中設定任何選用引數。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.tl() 方法

當您想要傳送追蹤呼叫至 Adobe 時，請呼叫 `s.tl()` 方法。

```js
s.tl();
```

此方法可選擇性地接受多個引數：

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### 連結物件

連結物件引數決定在離開頁面進行導覽前，瀏覽器是否最多等候 500 毫秒。如果影像要求在 500 毫秒內傳送，頁面會立即導覽至點按的連結。

>[!NOTE] AppMeasurement 會自動針對退出連結啟用 [`useBeacon`](../config-vars/usebeacon.md) 變數，因此現代瀏覽器不再需要該引數。此引數在舊版 AppMeasurement 中較常使用。

* `this`：等候最多 500 毫秒，讓 AppMeasurement 有時間傳送影像要求。預設值。
* `true`：請勿等候。

```JavaScript
// Include a 500ms delay
s.tl(this);

// Do not include a 500ms delay
s.tl(true);
```

### 連結類型

連結類型引數是單字母字串，可決定連結追蹤呼叫的類型。它與設定 [`linkType`](../config-vars/linktype.md) 變數相同。

```js
// Send a custom link
s.tl(true,"o");

// Send a download link
s.tl(true,"d");

// Send an exit link
s.tl(true,"e");
```

### 連結名稱

連結名稱引數是決定連結追蹤維度值的字串。它與設定 [`linkName`](../config-vars/linkname.md) 變數相同。

```js
s.tl(true,"d","Example download link");
```

### 變數覆寫

可讓您變更單一呼叫的變數值。如需詳細資訊，請參閱[變數覆寫](../../js/overrides.md)。

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## 範例和使用案例

直接在 HTML 連結內傳送基本連結追蹤呼叫：

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

使用JavaScript使用方法引數進行基本連結追蹤呼叫：

```JavaScript
s.tl(true,"o","Example link");
```

使用JavaScript，使用個別變數進行相同的基本連結追蹤呼叫：

```js
s.linkType = "o";
s.linkName = "Example link";
s.tl();
```

### 在自訂函數中進行連結追蹤呼叫

您可以將連結追蹤程式碼併入頁面上或連結 JavaScript 檔案中所定義的獨立 JavaScript 函數。接著，即可在每個連結的 onClick 函數中發出呼叫。在 JavaScript 檔案中設定下列項目:

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

之後，每當想要追蹤指定連結時，就可以呼叫函數：

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

### 避免追蹤重複的連結

如果 `trackDownloadLinks` 或 `trackExternalLinks` 已啟用，而且如果正確的篩選器相符，AppMeasurement 就會自動進行連結追蹤呼叫。如果您也手動針對這些連結點擊呼叫 `s.tl()`，可以將重複資料傳送至 Adobe。重複資料會增加報表數量，降低精確度。

例如，以下函數會針對相同的連結點擊傳送兩個連結追蹤呼叫 (手動和自動下載連結)：

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

您可以使用以下經過修改的函數，協助預防重複的連結追蹤呼叫。它會先檢查連結物件是否存在，並僅在連結物件為空字串時傳送手動連結追蹤呼叫。

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
