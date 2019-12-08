---
description: getVisitNum 外掛程式可判斷某個使用者對您的網站的瀏覽次數，並將此數目擷取到 Analytics 變數中。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getVisitNum
topic: Developer and implementation
uuid: 27d57f92-fffb-44d0-b9ca-9da93323f64c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getVisitNum

getVisitNum 外掛程式可判斷某個使用者對您的網站的瀏覽次數，並將此數目擷取到 Analytics 變數中。

## 外掛程式的程式碼與實施 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**設定區段**: 此區段無需變更。

**外掛程式設定**

將下列程式碼放入 *`s_doPlugins()`* 函數中；此函數位於 *`s_code.js`檔案中標示為* Plugin Config *的區域中。*&#x200B;選擇一個自訂流量 (s.prop) 變數或一個自訂轉換 (s.eVar) 變數，用於瀏覽次數資料的擷取。此變數應為已使用管理控制台加以啟用，但目前未做其他用途的變數。您可以使用下列範例，並根據您的需求加以更新。

`s.prop1=s.getVisitNum();`

> [!NOTE]下列指示會要求您變更網站上的資料收集程式碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

**外掛程式區段**: 將下列程式碼新增至 [!DNL s_code.js] 檔案中標示為 PLUGINS SECTION 的區域中。請勿對此部分的外掛程式程式碼進行任何變更。

```js
/* 
* Plugin: getVisitNum - version 3.0 
*/ 
s.getVisitNum=new Function("tp","c","c2","" 
+"var s=this,e=new Date,cval,cvisit,ct=e.getTime(),d;if(!tp){tp='m';}" 
+"if(tp=='m'||tp=='w'||tp=='d'){eo=s.endof(tp),y=eo.getTime();e.setTi" 
+"me(y);}else {d=tp*86400000;e.setTime(ct+d);}if(!c){c='s_vnum';}if(!" 
+"c2){c2='s_invisit';}cval=s.c_r(c);if(cval){var i=cval.indexOf('&vn=" 
+"'),str=cval.substring(i+4,cval.length),k;}cvisit=s.c_r(c2);if(cvisi" 
+"t){if(str){e.setTime(ct+1800000);s.c_w(c2,'true',e);return str;}els" 
+"e {return 'unknown visit number';}}else {if(str){str++;k=cval.substri" 
+"ng(0,i);e.setTime(k);s.c_w(c,k+'&vn='+str,e);e.setTime(ct+1800000);" 
+"s.c_w(c2,'true',e);return str;}else {s.c_w(c,e.getTime()+'&vn=1',e)" 
+";e.setTime(ct+1800000);s.c_w(c2,'true',e);return 1;}}"); 
s.dimo=new Function("m","y","" 
+"var d=new Date(y,m+1,0);return d.getDate();"); 
s.endof=new Function("x","" 
+"var t=new Date;t.setHours(0);t.setMinutes(0);t.setSeconds(0);if(x==" 
+"'m'){d=s.dimo(t.getMonth(),t.getFullYear())-t.getDate()+1;}else if(" 
+"x=='w'){d=7-t.getDay();}else {d=1;}t.setDate(t.getDate()+d);return " 
+"t;");
```

**參數**

* tp = (字串，選用) 追蹤期間。使用 "d" 表示日、"w" 表示週、"m" 表示月，或使用數字表示自訂的天數。

   * 如果選取日、週或月，則將在/週/月結束時重設瀏覽數目。
   * 如果選取自訂天數，則在該天數之後將重設瀏覽數目。
   * 如果未提供任何值，則將使用 "m"。

* c = (字串，選用) 指定永久 Cookie 名稱。預設為 's_vnum'。
* c2 = (字串，選用) 指定工作階段 Cookie 名稱。預設為 's_invisit'

**傳回**

* 傳回瀏覽的瀏覽數目 (1、2、3 等)。僅在每次瀏覽第一頁時才會增加此數目。
* 如果外掛程式無法識別瀏覽數目 (Cookie 遭到封鎖)，則傳回「不明的瀏覽數目」。

**範例**

```js
s.prop1=s.getVisitNum(365); //custom length, 365 days. Default cookie names 
s.prop1=s.getVisitNum('w'); //resets weekly 
s.prop1=s.getVisitNum('m','s_vmonthnum','s_monthinvisit'); //resets montly, custom cookie names 
s.prop1=s.getVisitNum('d'); //resets daily
```

**附註**

* 在部署至生產環境前，請務必對外掛程式安裝進行全面性的測試，以確保資料收集可如預期運作。
* 此外掛程式需仰賴在使用者的網頁瀏覽器中設定 Cookie 的功能。若使用者不接受 Cookie，則所有瀏覽都將被視為第一次瀏覽。

