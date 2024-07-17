---
title: tl
description: 傳送連結追蹤呼叫給 Adobe。
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
role: Admin, Developer
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 62%

---

# tl

`tl()` 方法是 Adobe Analytics 的重要核心元件。它會使用頁面上定義的所有 Analytics 變數、編譯成影像要求，然後將該資料傳送至 Adobe 資料收集伺服器。它的作用與 [`t()`](t-method.md) 方法類似，不過此方法不會增加頁面瀏覽數。若要追蹤連結和其他不視為完整頁面載入的元素，這個方法非常有用。

如果 [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) 或 [`trackExternalLinks`](../config-vars/trackexternallinks.md) 已啟用，AppMeasurement 會自動呼叫 `tl()` 方法，以便傳送下載連結和退出連結追蹤資料。如果您的組織想進一步控制要追蹤的連結與其行為，可以手動呼叫 `tl()` 方法。自訂連結只能手動追蹤。

## 使用Web SDK進行連結追蹤

Web SDK不會區分頁面檢視呼叫和連結追蹤呼叫；兩者都使用`sendEvent`命令。

如果您使用XDM物件，並希望Adobe Analytics將特定事件計算為連結追蹤呼叫，請確定您的XDM資料包括：

* 連結名稱：對應至`xdm.web.webInteraction.name`。
* 連結URL：對應至`xdm.web.webInteraction.URL`。
* 連結型別：對應至`xdm.web.webInteraction.type`。 有效值包括 `other` (自訂連結)、`download` (下載連結) 和 `exit` (退出連結)。

```js
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webInteraction": {
        "name": "My Custom Link",
        "URL": "https://example.com",
        "type": "other"
      }
    }
  }
});
```

如果您使用資料物件，且希望Adobe Analytics將特定事件計算為連結追蹤呼叫，請確定您的資料物件包含：

* 連結名稱：對應至`data.__adobe.analytics.linkName`。
* 連結URL：對應至`data.__adobe.analytics.linkURL`。
* 連結型別：對應至`data.__adobe.analytics.linkType`。 有效值包括 `o` (自訂連結)、`d` (下載連結) 和 `e` (退出連結)。

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "linkName": "My custom link",
        "linkURL": "https://example.com",
        "linkType": "o"
      }
    }
  }
});
```

## 使用Adobe Analytics擴充功能的連結追蹤

Adobe Analytics擴充功能有設定連結追蹤呼叫的專屬位置。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
1. 在[!UICONTROL 動作]底下，按一下所需的動作或按一下&#x200B;**&#39;+&#39;**&#x200B;圖示以新增動作。
1. 將[!UICONTROL 擴充功能]下拉式清單設定為&#x200B;**[!UICONTROL Adobe Analytics]**，並將[!UICONTROL 動作型別]設定為&#x200B;**[!UICONTROL 傳送信標]**。
1. 按一下 `s.tl()` 選擇鈕。

您無法在Analytics擴充功能中設定任何選用引數。

## AppMeasurement中的s.tl()方法和Analytics擴充功能自訂程式碼編輯器

當您想要傳送追蹤呼叫至 Adobe 時，請呼叫 `s.tl()` 方法。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### 連結物件 (必要)

連結物件引數決定在離開頁面進行導覽前，瀏覽器是否最多等候 500 毫秒。如果影像要求在 500 毫秒內傳送，頁面會立即導覽至點按的連結。

>[!NOTE]
>
>AppMeasurement 會自動針對退出連結啟用 [`useBeacon`](../config-vars/usebeacon.md) 變數，因此現代瀏覽器不再需要該引數。此引數在舊版 AppMeasurement 中較常使用。

* `this`：等候最多 500 毫秒，讓 AppMeasurement 有時間傳送影像要求。預設值。
* `true`：請勿等候。

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### 連結型別（必要）

連結類型引數是個單一字元的字串，用於判斷連結追蹤呼叫的類型。 有三個有效值。

* `o`：連結是[自訂連結](/help/components/dimensions/custom-link.md)。
* `d`：連結是[下載連結](/help/components/dimensions/download-link.md)。
* `e`：連結是[退出連結](/help/components/dimensions/exit-link.md)。

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### 連結名稱（建議）

連結名稱引數是決定連結追蹤維度項目的字串。在報告中使用[自訂連結](/help/components/dimensions/custom-link.md)、[下載連結](/help/components/dimensions/download-link.md)、或[退出連結](/help/components/dimensions/exit-link.md)維度時，該字串包含維度項目。如果此引數未經設定，則會使用 [linkURL](../config-vars/linkurl.md) 變數。

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### 變數覆寫（可選擇使用）

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

使用 JavaScript，以使用方法引數進行基本連結追蹤呼叫：

```JavaScript
s.tl(true,"o","Example link");
```

### 在自訂函數中進行連結追蹤呼叫

您可以將連結追蹤程式碼併入獨立的JavaScript函式中。 然後，即可在每個連結的`onClick`函式中進行呼叫。 在 JavaScript 檔案中設定下列項目：

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

>[!NOTE]
>間接呼叫`tl()`方法會降低Activity Map覆蓋報告的便利性。 您必須按一下每個連結，以使用連結元素註冊函式。 不過，Workspace中的Activity Map維度會以相同方式進行追蹤。

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

### 使用`tl()`方法搭配Activity Map

您可以使用`tl()`方法來追蹤自訂元素並設定動態內容的覆蓋圖演算。 `linkName`引數也可用來設定[Activity Map連結](/help/components/dimensions/activity-map-link.md)維度。

當從HTML元素的點選事件直接呼叫`tl()`方法時，Activity Map可以在載入網頁時顯示該元素的覆蓋圖。 例如：

```html
<a href="index.html" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

如果不是從HTML元素的點按事件直接呼叫`tl()`方法，則Activity Map只能在點按該元素後顯示覆蓋圖。 例如：

```html
<a href="index.html" onclick="someFn(event);">Example link text</a>
<script>
  function someFn (event) {
    s.tl(event.srcElement,'o','Example custom link');
  }
</script>
```
