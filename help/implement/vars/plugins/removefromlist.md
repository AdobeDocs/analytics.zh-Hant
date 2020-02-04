---
title: rfl
description: 從字元分隔字串移除特定值。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe外掛程式：rfl（從清單中刪除）

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以協助您從Adobe Analytics中獲得更多價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `rfl` 程式可讓您「安全」地從分隔字串移除值，例如 `events``products`、清單變數等。 如果您想從分隔字串移除特定值，而不需擔心分隔字元，此外掛程式會很有用。 其他數個外掛程式則依賴此程式碼才能正確執行。 如果您不需要一次對多個Analytics變數執行特定函式，或者您未使用任何相依外掛程式，則不需要此外掛程式。

外掛程式使用下列邏輯：

* 如果您要移除的值存在，外掛程式會保留變數中除要移除的值以外的所有項目。
* 如果您要移除的值不存在，外掛程式會將原始字串維持原狀。

## 使用Adobe Experience Platform Launch擴充功能安裝增效模組

Adobe提供擴充功能，讓您使用最常用的增效模組。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「目錄 [!UICONTROL 」按鈕]
1. 安裝和發佈 [!UICONTROL Common Analytics Plugins] extension
1. 對於您想要使用外掛程式的任何「啟動規則」，請新增具有下列設定的動作：
   * 擴充功能：常見Analytics外掛程式
   * 動作類型：初始化addProductEvar
1. 儲存並發佈規則的變更

## 使用Launch自訂程式碼編輯器安裝外掛程式

如果您不想使用外掛程式擴充功能，則可使用自訂程式碼編輯器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 按一下所要的屬性。
1. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下 [!UICONTROL Adobe Analytics延伸模組下的「設定] 」按鈕。
1. 展開「使 [!UICONTROL 用自訂程式碼] accordion設定追蹤」，此會顯示 [!UICONTROL 「開啟編輯器] 」按鈕。
1. 開啟自訂程式碼編輯器，並將下方提供的外掛程式碼貼入編輯視窗。
1. 儲存變更並發佈至Analytics擴充功能。

## 使用AppMeasurement安裝外掛程式

在Analytics追蹤物件實例化（使用）後，將下列程式碼複製並貼至AppMeasurement檔案中的任 `s_gi`何位置。 保留您實作中的程式碼注釋和版本號碼，有助於Adobe疑難排解任何潛在問題。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `rfl` 法使用以下引數：

* **`lv`**（必要，字串）:包含分隔值清單的變數（或字串）
* **`vr`**（必要，字串）:您要從引數中移除的`lv`值。 Adobe建議您不要在單一呼叫期間移除多個`rfl`值。
* **`d1`**（可選，字串）:引數使用的`lv`分隔字元。 預設為逗號(`,`)。
* **`d2`**（可選，字串）:您要使用傳回字串的分隔字元。 預設為與引數相同的`d1`值。
* **`df`**（可選，布林）:如`true`果，則僅強制從引數中重複`vr`執行個`lv`體，而非所有執行個體。 預設為`false`未設定時。

呼叫此方法會傳回包含引數的修 `lv` 改字串，但不會傳回在引數中指定值的例項（或重複例項） `vr` 。

## 呼叫範例

### 範例#1

若...

```js
s.events = "event22,event24,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events,"event24");
```

...s.events的最終值為：

```js
s.events = "event22,event25";
```

### 範例#2

若...

```js
s.events = "event22,event24,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events,"event26");
```

...s.events的最終值為：

```js
s.events = "event22,event24,event25";
```

在此範例中，rfl呼叫對s.events未做任何變更，因為s.events不包含&quot;event26&quot;

### 範例#3

若...

```js
s.events = "event22,event24,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events);
```

...s.events的最終值為：

```js
s.events = "";
```

如果s.rfl呼叫中的lv引數或vr引數為空白，則外掛程式將不會傳回任何內容

### 範例#4

若...

```js
s.prop4 = "hello|people|today";
```

...下列程式碼會執行……

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

...s.prop4的最終值仍將是……

```js
s.prop4 = "hello|people|today";
```

...但s.eVar5的最終值將是：

```js
s.eVar5 = "hello|today";
```

請記住，外掛程式只會傳回值；它實際上不會「重設」透過lv引數傳入的變數。

### 範例#5

若...

```js
s.prop4 = "hello|people|today";
```

...下列程式碼會執行……

```js
s.prop4 = s.rfl(s.prop4,"people");
```

...s.prop4的最終值仍將是……

```js
s.prop4 = "hello|people|today";
```

在lv引數值包含與預設值不同的分隔字元（即逗號）時，請務必設定d1引數。

### 範例#6

若...

```js
s.events = "event22,event23,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events,"EVenT23");
```

...s.events的最終值為：

```js
s.events = "event22,event23,event25";
```

雖然此範例不實用，但它顯示需要傳入區分大小寫的值。

### 範例#7

若...

```js
s.events = "event22,event23:12345,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events,"event23");
```

...s.events的最終值為：

```js
s.events = "event22,event25";
```

### 範例#8

若...

```js
s.events = "event22,event23:12345,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events,"event23:12345");
```

...s.events的最終值為：

```js
s.events = "event22,event23:12345,event25";
```

當您需要移除使用序列化及／或數值／貨幣語法的事件時，您應在s.rfl呼叫中僅指定事件本身（亦即沒有序列化／數值／貨幣值）。

### 範例#9

若...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events,"event23");
```

...s.events的最終值為：

```js
s.events = "event22,event24,event25");
```

### 範例#10

若...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

...s.events的最終值為：

```js
s.events = "event22,event23,event24,event25");
```

### 範例#11

若...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

...s.events的最終值為：

```js
s.events = "event22|event23|event24|event25");
```

### 範例#12

若...

```js
s.events = "event22,event23,event24,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events,"event23,event24");
```

...s.events的最終值為：

```js
s.events = "event22,event23,event24,event25";
```

不支援在vr參數中設定多個值。 上述範例中的rfl邏輯會先分割lv引數（即s.events）中的值，然後嘗試將每個分隔值與完整vr引數值(即&quot;event23,event24&quot;)。

### 範例#13

若...

```js
s.events = "event22,event23,event24,event25";
```

...下列程式碼會執行……

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

...s.events的最終值為：

```js
s.events = "event22,event25");
```

從清單中移除的每個值都應包含在其自己的s.rfl呼叫中。

### 範例#14

若...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...下列程式碼會執行……

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...s.linkTrackVars的最終值將是：

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

最後三個論點(即&quot;,&quot;,&quot;,&quot;,false)不是必要的，但是也不會因為存在而「傷害任何東西」，因為它們符合預設設定。

### 範例#15

若...

```js
s.events = "event22,event23,event24";
```

...下列程式碼會執行……

```js
s.rfl(s.events,"event23");
```

...s.events的最終值仍為：

```js
s.events = "event22,event23,event24";
```

請記住，外掛程式只會傳回值；它實際上不會「重設」透過lv引數傳入的變數。

## 版本記錄

### 2.01（2019年9月17日）

* 預設分隔字元值的次要錯誤修正

### 2.0（2018年4月16日）

* 點數發行（重新編譯，程式碼大小較小）。
* 已移除外掛程 `join` 式的需求。

### 1.0（2016年7月18日）

* 首次發行。
