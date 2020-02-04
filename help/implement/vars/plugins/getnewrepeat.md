---
title: getNewRepeat
description: 追蹤新訪客與重複訪客的活動。
translation-type: tm+mt
source-git-commit: aa4e1e71b8962fca8c880b9efe2b0a2b8b9e1360

---


# Adobe外掛程式：getNewRepeat

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以利您運用Adobe Analytics獲得更大價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `getNewRepeat` 程式可讓您判斷網站訪客是新訪客還是在所需天數內的重複訪客。 如果您想要使用自訂天數將訪客識別為「新」,Adobe建議使用此外掛程式。 如果分析工作區中的「新增／重複」訪客維度符合您組織的需求，則此外掛程式是不必要的。

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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

該方 `getNewRepeat` 法使用以下引數：

* **`d`**（整數，可選）:將訪客重設回訪客的瀏覽間所需的最小天數`"New"`。 如果未設定此引數，則預設為30天。

此方法會傳回 `"New"` 如果外掛程式設定的Cookie不存在或已過期的值。 它會傳回 `"Repeat"` 如果外掛程式設定的Cookie存在，且自目前點擊以來的時間量，以及Cookie中設定的時間超過30分鐘的值。 此方法會傳回整個瀏覽的相同值。

此外掛程式使用名為 `"s_nr[LENGTH]"` 其 `[LENGTH]` 等於引數的Cookie `d` 。 Cookie包含代表訪客（或）目前時間和狀態的Unix`"New"` 時 `"Repeat"`間戳記。

## 呼叫範例

### 範例#1

下列程式碼會為新訪客設定s.eVar1等於&quot;New&quot;的值，並在訪客瀏覽網站的其餘時間中，持續設定s.eVar1等於&quot;New&quot;（每次新呼叫）的值。

```js
s.eVar1=s.getNewRepeat();
```

### 範例#2

如果訪客自上次呼叫s.getNewRepeat()起31分鐘到30天內回訪網站，下列程式碼會在訪客造訪網站的其餘時間，將s.eVar1設定為等於&quot;Repeat&quot;的值，並繼續將s.eVar1設定為等於&quot;Repeat&quot;的值（每次新呼叫）。

```js
s.eVar1=s.getNewRepeat();
```

### 範例#3

如果訪客自上次呼叫s.getNewRepeat()起至少30天未瀏覽網站，下列程式碼會在訪客瀏覽網站的其餘時間，將s.eVar1設定為等於&quot;New&quot;的值，並持續將s.eVar1設定為等於&quot;New&quot;的值（每次新呼叫）。

```js
s.eVar1=s.getNewRepeat();
```

### 範例#4

如果訪客自上次呼叫s.getNewRepeat()起在31分鐘到365天（即1年）內回訪網站，下列程式碼會將s.eVar1設定為&quot;Repeat&quot;的值，並會在剩餘時間中繼續將s.eVar1設定為&quot;Repeat&quot;（每次新呼叫）的值訪客對網站的瀏覽。

```js
s.eVar1=s.getNewRepeat(365);
```

### 範例#5

如果訪客自上次呼叫s.getNewRepeat()起至少365天（即1年）未瀏覽網站，下列程式碼會將s.eVar1設定為&quot;New&quot;值，並會在剩餘的時間中，繼續將s.eVar1設定為&quot;New&quot;（含每個新訪客）的值瀏覽網站。

```js
s.eVar1=s.getNewRepeat(365);
```

## 版本記錄

### 2.1（2019年9月30日）

* 重新排列JavaScript邏輯以減少外掛程式大小

### 2.0（2018年4月16日）

* 以較小的程式碼大小重新編譯
* 移除命名Cookie以儲存瀏覽資訊的功能。 外掛程式現在會根據傳入至引數的值，動態命名Cookie `d` 。
