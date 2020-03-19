---
title: tl
description: 傳送連結追蹤呼叫給Adobe。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# tl

方 `tl()` 法是Adobe Analytics的重要核心元件。 它會將頁面上定義的所有Analytics變數匯入影像請求，然後將該資料傳送至Adobe資料收集伺服器。 它的運作方式與方 [`t()`](t-method.md) 法類似，但此方法不會增加頁面檢視。 它對於追蹤連結和其他不會視為完整頁面載入的元素非常有用。

如果 [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) 啟用 [`trackExternalLinks`](../config-vars/trackexternallinks.md) 或已啟用，AppMeasurement會自動呼叫方法， `tl()` 以傳送下載連結和退出連結追蹤資料。 如果您的組織想要對要追蹤的連結及其行為擁有更多控制權，則可以手動呼叫 `tl()` 方法。 自訂連結只能手動追蹤。

## Adobe Experience Platform Launch中的連結追蹤呼叫

Launch有專用位置設定連結追蹤呼叫。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往標籤 [!UICONTROL Rules] ，然後按一下所要的規則（或建立規則）。
1. 在下 [!UICONTROL Actions]方，按一下「+」圖示
1. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為傳送信標。
1. Click the `s.tl()` radio button.

您不能在Launch中設定任何可選引數。

## s.tl()方法（在AppMeasurement和Launch自訂代碼編輯器中）

當您想 `s.tl()` 要傳送追蹤呼叫至Adobe時，請呼叫方法。

```js
s.tl();
```

（可選）此方法接受多個引數：

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### 連結物件

連結物件引數會決定瀏覽器在離開頁面前是否等待500毫秒。 如果影像要求在 500 毫秒內傳送，頁面會立即導覽至點按的連結。

> [!NOTE] AppMeasurement會自動啟用退 [`useBeacon`](../config-vars/usebeacon.md) 出連結的變數，使此引數在現代瀏覽器中不再需要。 此引數在舊版AppMeasurement中更常使用。

* `this`: 等候最多 500 毫秒，讓 AppMeasurement 有時間傳送影像要求。預設值。
* `true`: 請勿等候。

```JavaScript
// Include a 500ms delay
s.tl(this);

// Do not include a 500ms delay
s.tl(true);
```

### 連結類型

連結類型引數是單字母字串，可決定連結追蹤呼叫的類型。 它與設定變數相 [`linkType`](../config-vars/linktype.md) 同。

```js
// Send a custom link
s.tl(true,"o");

// Send a download link
s.tl(true,"d");

// Send an exit link
s.tl(true,"e");
```

### 連結名稱

連結名稱引數是決定連結追蹤維度值的字串。 它與設定變數相 [`linkName`](../config-vars/linkname.md) 同。

```js
s.tl(true,"d","Example download link");
```

### 變數覆寫

可讓您變更單一呼叫的變數值。如需詳 [細資訊](../../js/overrides.md) ，請參閱變數覆寫。

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## 範例和使用案例

直接在HTML連結內傳送基本連結追蹤呼叫：

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

### 在自訂函式中進行連結追蹤呼叫

您可以將連結追蹤程式碼併入頁面上或連結 JavaScript 檔案中所定義的獨立 JavaScript 函數。接著，即可在每個連結的 onClick 函數中發出呼叫。在JavaScript檔案中設定下列項目：

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

然後，只要您想追蹤指定連結，就可呼叫函式：

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

### 避免追蹤重複的連結

如果 `trackDownloadLinks` 啟用 `trackExternalLinks` 或已啟用，AppMeasurement會在正確的篩選條件符合時自動進行連結追蹤呼叫。 如果您也手動呼叫這 `s.tl()` 些連結點按次數，則可傳送重複資料至Adobe。 重複資料會增加報表編號，使其不精確。

例如，下列函式會針對相同的連結點按傳送兩個連結追蹤呼叫（手動和自動下載連結）:

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

您可以使用下列修改的函式，協助防止重複的連結追蹤呼叫。 它會先檢查連結物件是否存在，並僅在連結物件為空字串時傳送手動連結追蹤呼叫。

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
