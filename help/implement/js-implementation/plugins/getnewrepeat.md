---
description: 判斷訪客是新訪客還是回訪訪客，並將這項資訊擷取到 Analytics 變數中。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getNewRepeat
topic: Developer and implementation
uuid: e3e9f362-e0b1-4a2b-bb5b-98eddaa0a7f4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getNewRepeat

判斷訪客是新訪客還是回訪訪客，並將這項資訊擷取到 Analytics 變數中。

使用此外掛程式可解答下列問題:

* 我的訪客中有多少百分比是新訪客 (相對於回訪訪客)？
* 回訪訪客所創造的單位人口轉換是否高於新訪客？其比例為何？
* 我的促銷活動是否帶來持續性的瀏覽？例如，點進促銷活動的使用者其後是否還會回訪？

> [!NOTE]下列指示會要求您變更網站上的資料收集程式碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

## 外掛程式的程式碼與實施 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**設定區段**: 此區段無需變更。

**外掛程式設定**

將下列程式碼放入 *`s_doPlugins()`* 函數中；此函數位於 *`s_code.js`檔案中標示為* Plugin Config *的區域中。*&#x200B;選擇一個自訂流量 (s.prop) 變數或一個自訂轉換 (s.eVar) 變數，用於持續值資料的擷取。此變數應為已使用管理控制台加以啟用，但目前未做任何其他用途的變數。您可以使用下列範例，並根據您的需求加以更新。

`s.prop1=s.getNewRepeat(30,'s_getNewRepeat');`

*`s.getNewRepeat`* 有兩個可選引數:

1. 第一個可選引數是 Cookie 應存留的天數。若省略此引數，則會使用預設值 30 天。
1. 第二個可選引數是 Cookie 名稱。若省略此引數，則會使用預設值。

**外掛程式區段**: 將下列程式碼新增至 [!DNL s_code.js] 檔案中標示為 PLUGINS SECTION 的區域中。請勿對此部分的外掛程式程式碼進行任何變更。

```js
/* 
 * Plugin: getNewRepeat 1.2 - Returns whether user is new or repeat 
 */ 
s.getNewRepeat=new Function("d","cn","" 
+"var s=this,e=new Date(),cval,sval,ct=e.getTime();d=d?d:30;cn=cn?cn:" 
+"'s_nr';e.setTime(ct+d*24*60*60*1000);cval=s.c_r(cn);if(cval.length=" 
+"=0){s.c_w(cn,ct+'-New',e);return'New';}sval=s.split(cval,'-');if(ct" 
+"-sval[0]<30*60*1000&&sval[1]=='New'){s.c_w(cn,ct+'-New',e);return'N" 
+"ew';}else{s.c_w(cn,ct+'-Repeat',e);return'Repeat';}"); 
/* 
* Utility Function: split v1.5 (JS 1.0 compatible) 
*/ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a");
```

在部署至生產環境前，請務必對外掛程式安裝進行全面性的測試，以確保資料收集可如預期運作。
