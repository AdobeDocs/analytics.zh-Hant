---
title: rfl
description: 從字元分隔字串中移除特定值。
feature: Variables
exl-id: d66b757e-b39f-4b6e-9999-6fbde87505af
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 100%

---

# Adobe 外掛程式：rfl (從清單中刪除)

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的客戶經理。客戶經理可安排您與顧問會面以尋求協助。

`rfl` 外掛程式可讓您「安全地」從分隔字串中移除值，例如 [`events`](../page-vars/events/events-overview.md)、[`products`](../page-vars/products.md)、[`list`](../page-vars/list.md) 等。如果您想從分隔字串中移除特定值，而不想顧慮分隔字元，此外掛程式非常實用。其他多個外掛程式依賴此程式碼才能正確運作。如果您不需要一次對多個 Analytics 變數執行特定函數，或者您未使用任何相依外掛程式，就不需要此外掛程式。

此外掛程式使用下列邏輯：

* 如果您要移除的值存在，外掛程式會保留變數中除了待移除值以外的所有內容。
* 如果您要移除的值不存在，外掛程式會將原始字串維持原狀。

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
    * Action Type: Initialize RFP (Remove From List)
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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.1  */
function rfl(lv,vr,d1,d2,df){var b=lv,f=vr,e=d1,h=d2,g=df;if("-v"===b)return{plugin:"rfl",version:"2.1"};a:{if("undefined"!==typeof window.s_c_il){var c=0;for(var a;c<window.s_c_il.length;c++)if(a=window.s_c_il[c],a._c&&"s_c"===a._c){c=a;break a}}c=void 0}"undefined"!==typeof c&&(c.contextData.rfl="2.1");if(!b||!f)return"";c=[];a="";e=e||",";h=h||e;g=g||!1;b=b.split(e);e=b.length;for(var d=0;d<e;d++)-1<b[d].indexOf(":")&&(a=b[d].split(":"),a[1]=a[0]+":"+a[1],b[d]=a[0]),-1<b[d].indexOf("=")&&(a=b[d].split("="),a[1]=a[0]+"="+a[1],b[d]=a[0]),b[d]!==f&&a?c.push(a[1]):b[d]!==f?c.push(b[d]):b[d]===f&&g&&(a?c.push(a[1]):c.push(b[d]),g=!1),a="";return c.join(h)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

`rfl` 函數會使用以下引數：

* **`lv`** (必要，字串)：包含分隔值清單的變數 (或字串)
* **`vr`** (必要，字串)：您要從 `lv` 引數中移除的值。Adobe 建議您不要在 `rfl` 單一呼叫期間移除多個值。
* **`d1`** (選用，字串)：`lv` 引數使用的分隔字元。預設為逗號 (`,`)。
* **`d2`** (選用，字串)：您要讓傳回字串使用的分隔字元。預設為與 `d1` 引數相同的值。
* **`df`** (選用，布林值)：如果為 `true`，則僅強制從 `lv` 引數中複製 `vr` 引數的例項，而非所有例項。若未設定，則預設為 `false`。

呼叫此函數會傳回包含 `lv` 引數的修改字串，但字串中不包含 `vr` 引數中所指定值的任何實例 (或重複實例)。

## 呼叫範例

### 範例 #1

若...

```js
s.events = "event22,event24,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events,"event24");
```

...s.events 的最終值將為：

```js
s.events = "event22,event25";
```

### 範例 #2

若...

```js
s.events = "event22,event24,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events,"event26");
```

...s.events 的最終值將為：

```js
s.events = "event22,event24,event25";
```

在此範例中，rfl 呼叫沒有對 s.events 做任何變更，因為 s.events 中不包含「event26」

### 範例 #3

若...

```js
s.events = "event22,event24,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events);
```

...s.events 的最終值將為：

```js
s.events = "";
```

如果 `rfl` 呼叫中的 `lv` 引數或 `vr` 引數為空白，則外掛程式將不會傳回任何內容。

### 範例 #4

若...

```js
s.prop4 = "hello|people|today";
```

...且下列程式碼執行...

```js
s.eVar5 = rfl(s.prop4,"people","|");
```

...s.prop4 的最終值仍會是...

```js
s.prop4 = "hello|people|today";
```

...但 s.eVar5 的最終值將為：

```js
s.eVar5 = "hello|today";
```

請記得，外掛程式只會傳回值，實際上並不會「重設」透過 `lv` 引數傳入的變數。

### 範例 #5

若...

```js
s.prop4 = "hello|people|today";
```

...且下列程式碼執行...

```js
s.prop4 = rfl(s.prop4,"people");
```

...s.prop4 的最終值仍會是...

```js
s.prop4 = "hello|people|today";
```

若 `lv` 引數值包含與預設值不同的分隔字元 (即逗號)，請務必設定 `d1` 引數。

### 範例 #6

若...

```js
s.events = "event22,event23,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events,"EVenT23");
```

...s.events 的最終值將為：

```js
s.events = "event22,event23,event25";
```

雖然此範例並不實際，但呈現出傳入區分大小寫值的必要性。

### 範例 #7

若...

```js
s.events = "event22,event23:12345,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events,"event23");
```

...s.events 的最終值將為：

```js
s.events = "event22,event25";
```

### 範例 #8

若...

```js
s.events = "event22,event23:12345,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events,"event23:12345");
```

...s.events 的最終值將為：

```js
s.events = "event22,event23:12345,event25";
```

當您需要移除使用序列化及/或數值/貨幣語法的事件時，應該在 `rfl` 呼叫中僅指定事件本身 (亦即不含序列化/數值/貨幣值)。

### 範例 #9

若...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events,"event23");
```

...s.events 的最終值將為：

```js
s.events = "event22,event24,event25");
```

### 範例 #10

若...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events,"event23", "", "",true);
```

...s.events 的最終值將為：

```js
s.events = "event22,event23,event24,event25");
```

### 範例 #11

若...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events,"event23", "", "|",true);
```

...s.events 的最終值將為：

```js
s.events = "event22|event23|event24|event25");
```

### 範例 #12

若...

```js
s.events = "event22,event23,event24,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events,"event23,event24");
```

...s.events 的最終值將為：

```js
s.events = "event22,event23,event24,event25";
```

不支援在 `vr` 引數中設定多個值。 上述範例中，`rfl` 邏輯會先分割 `lv` 引數 (即 s.events) 中的值，然後嘗試比對每個分隔值與完整 `vr` 引數值 (即 `"event23,event24"`)。

### 範例 #13

若...

```js
s.events = "event22,event23,event24,event25";
```

...且下列程式碼執行...

```js
s.events = rfl(s.events,"event23");
s.events = rfl(s.events,"event24");
```

...s.events 的最終值將為：

```js
s.events = "event22,event25");
```

從清單中移除的每個值都應該包含在其自己的 `rfl` 呼叫中。

### 範例 #14

若...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...且下列程式碼執行...

```js
s.linkTrackVars = rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...s.linkTrackVars 的最終值將為：

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

此 `rfl` 呼叫結尾的最後三個引數 (即「,」、「,」、false) 並非必要，但是也不會因為存在而「影響任何項目」，因為它們符合預設設定。

### 範例 #15

若...

```js
s.events = "event22,event23,event24";
```

...且下列程式碼執行...

```js
rfl(s.events,"event23");
```

...s.events 的最終值仍會是：

```js
s.events = "event22,event23,event24";
```

再次強調，請記得外掛程式只會傳回值，實際上並不會「重設」透過 `lv` 引數傳入的變數。

## 版本記錄

### 2.1 (2021 年 3 月 19 日)

* 將版本編號加入為內容資料。

### 2.01 (2019 年 9 月 17 日)

* 預設分隔字元值的微幅錯誤修正

### 2.0 (2018 年 4 月 16 日)

* 單點發行 (重新編譯，程式碼大小較小)。
* 移除 `join` 外掛程式的必要性。

### 1.0 (2016 年 7 月 18 日)

* 首次發行。
