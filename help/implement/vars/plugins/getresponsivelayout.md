---
title: getResponsiveLayout
description: 決定目前檢視的網站配置。
feature: Appmeasurement Implementation
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 86%

---

# Adobe 外掛程式：getResponsiveLayout

{{plug-in}}

`getResponsiveLayout` 外掛程式可讓您追蹤訪客目前正在檢視的回應式設計網站版本。如果您的網站使用回應式設計，而您想要追蹤訪客檢視的網站版本，Adobe 建議使用此外掛程式。如果您的網站並非使用回應式設計，就不需要此外掛程式。

## 使用網頁SDK或網頁SDK擴充功能安裝外掛程式

此外掛程式尚不支援在網頁SDK中使用。

## 使用Adobe Analytics擴充功能安裝外掛程式

Adobe提供擴充功能，可讓您搭配Adobe Analytics使用最常用的外掛程式。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 擴充功能]標記，然後按一下[!UICONTROL 「目錄」]按鈕
1. 安裝並發佈[!UICONTROL 常用 Analytics 外掛程式]擴充功能
1. 如果您尚未執行上述步驟，請使用下列設定建立標示為「初始化外掛程式」的規則：
   * 條件：無
   * 事件：核心 - 已載入資料庫 (頁面頂端)
1. 使用下列設定將動作新增至上述規則：
   * 擴充功能：常用 Analytics 外掛程式
   * 動作類型：初始化 getResponsiveLayout
1. 儲存並發佈規則的變更。

## 使用自訂程式碼編輯器安裝外掛程式

如果您不想使用常見Analytics外掛程式擴充功能，可以使用自訂程式碼編輯器。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]索引標籤，然後按一下 Adobe Analytics 擴充功能底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開[!UICONTROL 使用自訂程式碼設定追蹤]摺疊式功能表，便會顯示[!UICONTROL 「開啟編輯器」]按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式程式碼貼入編輯視窗中。
1. 儲存並發佈 Analytics 擴充功能的變更。

## 使用 AppMeasurement 安裝外掛程式

Analytics 追蹤物件實例化 (使用 [`s_gi`](../functions/s-gi.md)) 後，將下列程式碼複製並貼到 AppMeasurement 檔案中的任何位置。保留您實作中的程式碼備註和版本號碼，有助於 Adobe 疑難排解任何可能問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`getResponsiveLayout` 函數會使用以下引數：

* **`ppw`** (必要，整數)：頁面從手機直向配置切換為手機橫向配置之前，瀏覽器視窗的最大像素寬度
* **`plw`** (必要，整數)：頁面從手機橫向配置切換為平板電腦配置之前，瀏覽器視窗的最大像素寬度
* **`tw`** (必要，整數)：頁面從平板電腦版面切換為桌上型電腦版面之前，瀏覽器視窗的最大像素寬度

呼叫此函數所傳回的字串會包含冒號 (`:`) 分隔的兩個部分。 此字串的第一個部分包含下列其中一個值，視瀏覽器的寬度和上述引數而定：

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (適用於並非直向和橫向配置均具備的網站)
* `"tablet layout"`
* `"desktop layout"`

傳回字串的第二部分是瀏覽器的寬度和高度維度。例如：`"desktop layout:1243x700"`。

## 範例

```js
// A visitor accesses your site on their laptop. The browser window is maximized.
// * Your site switches from phone portrait mode to phone landscape mode when the browser width is greater than 500 pixels
// * Your site switches from phone landscape mode to tablet mode when the browser width is greater than 700 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1000 pixels
// Sets eVar10 to "desktop layout:1920x937".
s.eVar10 = getResponsiveLayout(500, 700, 1000);

// A visitor accesses your site on their phone.
// * Your site has only a phone mode, a tablet mode, and a desktop mode
// * Your site switches from phone mode to tablet mode when the browser width is greater than 800 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1,100 pixels
// Sets eVar10 to "phone portrait layout:720x1280"
s.eVar10 = getResponsiveLayout(800, 800, 1100);
```

## 版本記錄

### 1.1 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 1.0 (2018 年 5 月 2 日)

* 首次發行。
