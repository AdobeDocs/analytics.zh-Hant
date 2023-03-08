---
title: getResponsiveLayout
description: 決定目前檢視的網站配置。
feature: Variables
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 100%

---

# Adobe 外掛程式：getResponsiveLayout

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`getResponsiveLayout` 外掛程式可讓您追蹤訪客目前正在檢視的回應式設計網站版本。如果您的網站使用回應式設計，而您想要追蹤訪客檢視的網站版本，Adobe 建議使用此外掛程式。如果您的網站並非使用回應式設計，就不需要此外掛程式。

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getResponsiveLayout
1. Save and publish the changes to the rule.-->

## 使用自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，可以使用自訂程式碼編輯器。

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
