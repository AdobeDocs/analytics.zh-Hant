---
title: 移轉至 JavaScript 適用的 AppMeasurement
description: 決定將實作從 H 程式碼移出時所需的項目。
feature: Implementation Basics
exl-id: ed606ab4-bd7d-4871-baa1-77e30fdd419e
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 91%

---

# 移轉至 JavaScript 適用的 AppMeasurement

如果您的實作仍使用 H 程式碼，Adobe 強烈建議您移轉至最新版的 AppMeasurement。我們建議您透過 [Adobe Experience Platform 中的標記](../launch/overview.md)實作 Analytics，不過也可以使用更新的 JavaScript 實作。

與 H 程式碼相比，AppMeasurement 有下列顯著變更：

* 較 H 程式碼快 3 到 7 倍。
* 較 H 程式碼輕巧 - 未壓縮 21kb；H 程式碼則是未壓縮為 33kb。
* 資料庫和頁面代碼可部署在 `<head>` 標記中。
* 現有的頁面層級 H 程式碼與 AppMeasurement 相容。
* 資料庫提供原生公用程式，用以取得查詢參數、讀取和寫入 Cookie，以及執行進階連結追蹤。
* 資料庫不支援動態帳戶設定變數 (包括 `dynamicAccountSelection`、`dynamicAccountMatch` 和 `dynamicAccountList`)。

下列步驟概觀典型的移轉工作流程。

1. **下載新的 AppMeasurement 檔案**：登入 Adobe Analytics，然後導覽至「管理員 > 代碼管理器」存取新檔案。 下載的壓縮檔包含精簡的 `AppMeasurement.js` 檔案，以及媒體和整合模組。
1. **將您的 `s_code.js` 自訂內容複製到`AppMeasurement.js`**：將 `s_code.js` 中 `DO NOT ALTER ANYTHING BELOW THIS LINE` 區段之前的所有程式碼複製到 `AppMeasurement.js` 的開頭。
1. **更新所有外掛程式**：請務必使用`s_code.js`檔案中所列之每個外掛程式的最新版本。 此步驟包含媒體和整合模組。
1. **部署 AppMeasurement.js 檔案**：將 `AppMeasurement.js` 檔案上傳至網頁伺服器。
1. **更新指令碼參考以指向`AppMeasurement.js`**：確認所有頁面都參考 `AppMeasurement.js`，而非 `s_code.js`。

## 範例 Appmeasurement 程式碼

典型的 `AppMeasurement.js` 檔案。請務必將設定變數設定在 `doPlugins` 函數上方。

```js
// Initialize AppMeasurement
var s = s_gi("examplersid");

/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/;
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE");

/************************** CONFIG SECTION **************************/;
/* You may add or alter any code config here. */
s.trackDownloadLinks = true;
s.trackExternalLinks = true;
s.trackInlineStats = true;
s.linkDownloadFileTypes = "exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx";
s.linkInternalFilters = "javascript:,example.com";

s.usePlugins = true;
function s_doPlugins(s) {

// Use implementation plug-ins that are defined below in this section

}
s.doPlugins = s_doPlugins;

/* WARNING: Changing any of the below variables will cause drastic
changes to how your visitor data is collected.  Changes should only be
made when instructed to do so by your Adobe Account Team.*/
s.trackingServer="example.data.adobedc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */
```

## 範例頁面代碼

在每個頁面上載入的典型程式碼。

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

也務必在每一頁上加入對 `AppMeasurement.js` 和 `VisitorAPI.js` 的參考。如需詳細資訊，請參閱 [JavaScript 實作](/help/implement/js/overview.md)。
