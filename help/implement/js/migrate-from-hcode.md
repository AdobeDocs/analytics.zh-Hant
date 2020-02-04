---
title: 移轉至 JavaScript 適用的 AppMeasurement
description: 確定從H代碼移轉實施所需的項目。
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# 移轉至 JavaScript 適用的 AppMeasurement

如果您的實作仍使用H程式碼，Adobe強烈建議移轉至最新版的AppMeasurement。 建議透過 [Adobe Experience Platform Launch實作Analytics](../launch/overview.md) ，但可使用更新的JavaScript實作。

與H代碼相比，AppMeasurement中會出現下列顯著變更：

* 比H代碼快3-7倍。
* 輕於H代碼- 21kb的未壓縮比H代碼（未壓縮為33kb）。
* 程式庫和頁面程式碼可部署在 `<head>` 標籤中。
* 現有的頁面層級H程式碼與AppMeasurement相容。
* 程式庫提供原生公用程式，用以取得查詢參數、讀取和寫入 Cookie，以及執行進階連結追蹤。
* 程式庫不支援動態帳戶設定變數( `dynamicAccountSelection`包括 `dynamicAccountMatch`、 `dynamicAccountList`和)。
* 「調查」模組不受支援。

下列步驟概述了典型的遷移工作流。

1. **下載新的AppMeasurement檔案**:登入Adobe Analytics，然後導覽至「管理員>代碼管理器」，以存取新檔案。 下載的壓縮檔包含精簡檔 `AppMeasurement.js` 案，以及媒體和整合模組。
1. **將您的自`s_code.js`訂內容複製至`AppMeasurement.js`**:將中節之前的所`DO NOT ALTER ANYTHING BELOW THIS LINE`有代碼`s_code.js`移至開頭`AppMeasurement.js`。
1. **更新所有外掛程式**:請確定您使用的是檔案中所列每個外掛程式的最新版本 `s_code.js` 。 這包括媒體和整合模組。
1. **部署AppMeasurement.js檔案**:將檔案 `AppMeasurement.js` 上傳至網頁伺服器。
1. **更新指令碼參考以指向`AppMeasurement.js`**:請確定所有頁面都參`AppMeasurement.js`考，而非`s_code.js`。

## 範例Appmeasurement程式碼

典型的 `AppMeasurement.js` 檔案。 請確定設定變數設定在函式上 `doPlugins` 方。

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
made when instructed to do so by your account manager.*/
s.trackingServer="example.sc.omtrdc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */
```

## 頁面代碼範例

載入每個頁面的典型程式碼。

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

也務必在每一頁上加入對 `AppMeasurement.js` 和 `VisitorAPI.js` 的參考。如需詳 [細資訊，請參閱](/help/implement/js/overview.md) 「JavaScript實作」。
