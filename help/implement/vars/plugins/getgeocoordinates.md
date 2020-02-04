---
title: getGeoCoordinates
description: 追蹤訪客的geoLocation。
translation-type: tm+mt
source-git-commit: e08f3e168a779f9678a109d7f533761629cd38f3

---


# Adobe外掛程式：getGeoCoordinates

> [!IMPORTANT] 此外掛程式由Adobe Consulting提供，以利您運用Adobe Analytics獲得更大價值。 Adobe客戶服務不提供此外掛程式的支援，包括安裝或疑難排解。 如果您需要此外掛程式的協助，請連絡您組織的客戶經理。 客人可安排與顧問會面以尋求協助。

外掛 `getGeoCoordinates` 程式可讓您擷取訪客裝置的經緯度。 如果您想要在Analytics變數中擷取地理位置資料，Adobe建議使用此外掛程式。

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
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用外掛程式

方 `getGeoCoordinates` 法不使用任何引數。 它返回以下值之一：

* `"geo coordinates not available"`:對於在外掛程式執行時沒有地理位置資料的裝置。 此值在第一次瀏覽點擊時很常見，尤其是當訪客第一次需要在追蹤其位置時提供同意時。
* `"error retrieving geo coordinates"`:當外掛程式嘗試擷取裝置位置時遇到任何錯誤時
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`:其 [中LATITUDE]/[LOGNITUDE] 分別是經緯度

> [!NOTE] 坐標值四捨五入到最接近的四小數。 例如，值會四捨五入 `"40.438635333"` 以限制要 `"40.4386"` 擷取的唯一值數目。 這些值非常接近，可以精確定位裝置在20英尺內的確切位置。

此外掛程式會使用名為的Cookie `"s_ggc"` 來儲存點擊之間的座標。

## 呼叫範例

### 範例#1

下列程式碼……

```js
s.eVar1 = s.getGeoCoordinates();
```

...根據訪客的裝置狀態，將eVar1設為上述其中一個傳回值

### 範例#2

下列程式碼會將緯度和經度擷取至其自己的變數（稱為finalLatitude和finalLognitude）中，以用於其他程式碼／應用程式

```js
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```

從這裡，您可以判斷訪客是否在自由女神像：

```js
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
  var visitorAtStatueOfLiberty = true;
else
  var visitorAtStatueOfLiberty = false;
```

## 版本記錄

### 1.0（2015年5月25日）

* 首次發行。
