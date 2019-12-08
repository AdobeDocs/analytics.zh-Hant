---
description: 記錄您的頁面在瀏覽器中是作用中標籤的秒數，並傳遞該值給下一個頁面檢視的量度。
keywords: Analytics Implementation
title: getPageVisibility
topic: Developer and implementation
uuid: 3891e2aa-d5c1-4a2b-8522-eb2bae39ea2e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getPageVisibility

記錄您的頁面在瀏覽器中是作用中標籤的秒數，並傳遞該值給下一個頁面檢視的量度。

> [!NOTE]此為測試版外掛程式，隨後可能有其他更新。

此外掛程式需要使用 [getVisitStart](/help/implement/js-implementation/plugins/getvisitstart.md)。

此外掛程式也會記錄頁面在瀏覽器中的秒數總計 (包括作用中和被動檢視時間)。必須使用 getPreviousValue 外掛程式，才能追蹤與頁面可見度事件關聯的上一頁名稱。追蹤這些值可讓您更清楚瞭解訪客參與，以及更精確追蹤您網站上的訪客行為。

您必須使用 getPreviousValue 外掛程式，才能追蹤與頁面可見度事件關聯的上一頁名稱。追蹤這些值可讓您更清楚瞭解訪客參與，以及更精確追蹤您網站上的訪客行為。

> [!NOTE]下列指示會要求您變更網站上的資料收集程式碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 Analytics 的開發人員執行。此外掛程式僅與 [!DNL AppMeasurement] 追蹤程式庫相容。

## 必要的支援外掛程式 {#section_0CA7624F4A7B4B5F851A4300937887AD}

* appendList
* getPreviousValue
* getVisitStart

## 外掛程式的程式碼與實施 {#section_543ABD8B3E6A48A5AFD86CFEDE144696}

**設定區段**

`s.pvel` 變數應包含您想使用的三個事件:

| 事件 | 定義 |
|---|---|
| 頁面可見度秒數總計 (數值) | 頁面在瀏覽器中為作用中的時間量 |
| 頁面秒數總計 (數值) | 頁面載入至瀏覽器的時間量，無論其可見度狀態 |
| 頁面可見度例項總計 (計數器) | 記錄前兩個事件之值的總次數 |

**範例呼叫**

```
//Page Visibility Event List (total page visibility seconds, total page seconds, total page visibility instances) 
s.pvel='event7,event8,event9' 
```

**doPlugins 區段**

若要初始化外掛程式，需要在 s_code 的 `doPlugins` 區段中加入兩行程式碼，最好在指定 `s.pageName` 變數後進行。

**範例呼叫**

```
/* Page Visibility */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.getPageVisibility(); 
```

**外掛程式區段**

```
/* Page Visibility Plugin 0.1 (BETA) */ 
s.getPageVisibility=new Function("","" 
+"var s=this;if(s.getVisitStart()){s.Util.cookieWrite('s_pvs','');s.U" 
+"til.cookieWrite('s_tps','');}if(s.Util.cookieRead('s_pvs')&&s.pvt<1" 
+"){if(parseInt(s.Util.cookieRead('s_pvs'))<=parseInt(s.Util.cookieRe" 
+"ad('s_tps'))){s.pve=s.pvel.split(',');s.events=s.apl(s.events,s.pve" 
+"[0]+'='+(parseInt(s.Util.cookieRead('s_pvs'))),',',2);s.Util.cookie" 
+"Write('s_pvs','');s.events=s.apl(s.events,s.pve[1]+'='+(parseInt(s." 
+"Util.cookieRead('s_tps'))),',',2);s.Util.cookieWrite('s_tps','');s." 
+"events=s.apl(s.events,s.pve[2],',',2);}}s.pvi=setInterval(s.pvx,100" 
+"0);s.wpvi=setInterval(s.wpvc,5000);"); 
s.gbp=new Function("","" 
+"if('hidden'in document){return null;}var bp=['moz','ms','o','webkit" 
+"'];for(var i=0;i<bp.length;i++){var p=bp[i]+'Hidden';if(p in docume" 
+"nt){return bp[i];}}return null;"); 
s.hp=new Function("p","" 
+"if(p){return p+'Hidden';}else{return'hidden';}"); 
s.vs=new Function("p","" 
+"if(p){return p+'VisibilityState';}else{return'visibilityState';}"); 
s.ve=new Function("p","" 
+"if(p){return p+'visibilitychange';}else{return'visibilitychange';}"); 
s.pvx=new Function("","" 
+"s.pvt+=1;"); 
s.wpvc = function(){var tempDate = Date.now();s.Util.cookieWrite('s_tps', 
Math.ceil((tempDate - s.totalTime)/1000));s.Util.cookieWrite('s_pvs', s.pvt)} 
document.addEventListener('visibilitychange',function(event){if(document.hidden){s.visibility = false;clearTimeout(s.pvi);}else{s.visibility=true;s.pvi=setInterval(s.pvx,1000);}});s.totalTime=new Date();s.pvt=0;s.prefix=s.gbp;s.hidden=s.hp(s.prefix);s.visibility=true;s.visibilityState=s.vs(s.prefix);s.visibilityEvent=s.ve(s.prefix); 
```

## 附註 {#section_47964BB9D0A24BFEB4B2498A41D8B017}

* 在部署至生產環境前，請務必對外掛程式安裝進行測試，以確保資料收集可如預期運作。
* 由於外掛程式所傳送的是與上一頁關聯的頁面可見度秒數和秒數總計，因此不會收集瀏覽之最後一個頁面檢視的資料。
* 此外掛程式需仰賴在使用者的網頁瀏覽器中設定 Cookie 的功能。若使用者不接受第一方 Cookie，外掛程式即不會將資料傳入 Analytics 中。
* 外掛程式會建立本身的第一方 Cookie，名為 `s_tps` 和 `s_pvs`。

* 很小一部分的使用者由於瀏覽器限制而不會傳送所檢視頁面資料的百分比，因此在外掛程式中包含邏輯以確保做為結果的資料不會產生偏差。不過，此外掛程式在 IE、Firefox、Chrome、與 Safari 中均已順利通過測試。
* 由於外掛程式用於測量秒數總計以及將該值與上一頁名稱建立關聯的方式不同，預設頁面逗留時間量度和秒數總計量度之間會存在差異。
* 可以建立[!UICONTROL 計算量度]來協助彙總及瞭解與以下量度關聯的訪客行為:

   * **頁面可見度比率**(頁面可見度秒數總計/頁面秒數總計)
   * **隱藏秒數總計** （頁面秒數總計——頁面可見度秒數總計）
   * **頁面可見度平均秒數**(頁面可見度秒數總計/頁面可見度例項總計)
   * **頁面隱藏平均秒數** ((頁面秒數總計 - 頁面可見度秒數總計)/頁面可見度例項總計)

* 由於外掛程式進位秒數的方式，頁面可見度秒數總計和秒數總計之間有 1-2 秒的差異，秒數總計會比較高。(未來更新將會解決此問題)
* 使用 getVisitStart 外掛程式應注意閒置 30 分鐘以上的訪客會起始新的瀏覽階段。這不是設計的；不過，當我們將「活動秒數總計」納入外掛程式的未來小版本時，可能會有因應措施。

## 常見問題集 {#section_1ED9391D3BAA4208817F0DF69ABBB25E}

**此外掛程式會進行額外的伺服器呼叫嗎?**

外掛程式只會記錄後續頁面檢視伺服器呼叫的頁面可見度值。所以不會結合使用額外的伺服器呼叫。

**如果我不想擷取頁面秒數總計或頁面可見度例項總計，可以不把它們列入事件清單嗎?**

可以，頁面秒數總計和可見度例項總計是可選事件，可以視需要不列入清單。

**如果我在「上一頁名稱」以外的報表中使用這些擷取的事件，這些事件仍有意義嗎?**

由於外掛程式只會在後續影像要求上記錄值，因此只能套用在「上一頁」內容中擷取的其他eVar，即「上一頁URL」。

**外掛程式會在 s.tl() 呼叫中傳送可見度時間，還是只在 s.t() 呼叫中傳送?**

可見度時間只在 s.t() 呼叫中記錄。
