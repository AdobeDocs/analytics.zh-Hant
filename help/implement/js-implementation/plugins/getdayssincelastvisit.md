---
description: 判斷使用者前次瀏覽您的網站後所經過的天數，並將這項資訊擷取到 Analytics 變數中。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getDaysSinceLastVisit
topic: Developer and implementation
uuid: cad95882-3bd0-4f94-a0c3-4e7b6058d246
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getDaysSinceLastVisit

判斷使用者前次瀏覽您的網站後所經過的天數，並將這項資訊擷取到 Analytics 變數中。

>[!IMPORTANT]
>
>[分析工作區](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) 現在包含自上 **[!UICONTROL 次瀏覽開始的天數維度]** ，因此無法使用此外掛程式。

這項回訪頻率資料可用來解答下列問題:

* 使用者回訪網站的頻率為何? 
* 回訪頻率與轉換如何產生關聯? 重複購買者的瀏覽頻率高不高？
* 點進促銷活動的使用者其後是否頻繁回訪？

此外掛程式也可產生用於劃分的值。例如，您可以僅針對之前的 30 天或更長時間沒有使用者瀏覽的頁面建立一個分段，來檢視其所有的資料。

> [!NOTE]下列指示會要求您變更網站上的資料收集程式碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

## 外掛程式的程式碼與實施 {#section_5600DBB819F143D59527A73BD94418DE}

**設定區段**

無需變更。

**外掛程式設定**

將下列程式碼放入 `s_doPlugins()` 函數中；此函數位於 [!DNL s_code.js] 檔案中標示為 *Plugin Config* 的區域中。選擇一個自訂流量 (s.prop) 變數和 (或) 一個自訂轉換 (s.eVar) 變數，用於回訪頻率資料的擷取。選取的變數應為已使用管理控制台加以啟用，但目前未做任何其他用途的變數。下列內容為範例，請依照您的需求適當加以更新。

```js
s.prop1=s.getDaysSinceLastVisit(Cookie_Name);
```

**外掛程式區段**&#x200B;將下列程式碼新增至 [!DNL s_code.js]*檔案中標示為* PLUGINS SECTION 的區域中。請勿對此部分的外掛程式程式碼進行任何變更。

```js
/* 
 * Plugin: Days since last Visit 1.1 - capture time from last visit 
 */ 
s.getDaysSinceLastVisit=new Function("c","" 
+"var s=this,e=new Date(),es=new Date(),cval,cval_s,cval_ss,ct=e.getT" 
+"ime(),day=24*60*60*1000,f1,f2,f3,f4,f5;e.setTime(ct+3*365*day);es.s" 
+"etTime(ct+30*60*1000);f0='Cookies Not Supported';f1='First Visit';f" 
+"2='More than 30 days';f3='More than 7 days';f4='Less than 7 days';f" 
+"5='Less than 1 day';cval=s.c_r(c);if(cval.length==0){s.c_w(c,ct,e);" 
+"s.c_w(c+'_s',f1,es);}else{var d=ct-cval;if(d>30*60*1000){if(d>30*da" 
+"y){s.c_w(c,ct,e);s.c_w(c+'_s',f2,es);}else if(d<30*day+1 && d>7*day" 
+"){s.c_w(c,ct,e);s.c_w(c+'_s',f3,es);}else if(d<7*day+1 && d>day){s." 
+"c_w(c,ct,e);s.c_w(c+'_s',f4,es);}else if(d<day+1){s.c_w(c,ct,e);s.c" 
+"_w(c+'_s',f5,es);}}else{s.c_w(c,ct,e);cval_ss=s.c_r(c+'_s');s.c_w(c" 
+"+'_s',cval_ss,es);}}cval_s=s.c_r(c+'_s');if(cval_s.length==0) retur" 
+"n f0;else if(cval_s!=f1&&cval_s!=f2&&cval_s!=f3&&cval_s!=f4&&cval_s" 
+"!=f5) return '';else return cval_s;");
```

**附註**

* 在部署至生產環境前，請務必對外掛程式安裝進行全面性的測試，以確保資料收集可如預期運作。
* 此外掛程式會依照回訪頻率，將使用者分類為下列群組:

   * 第一次瀏覽
   * 少於 1 天
   * 少於 7 天
   * 多於 7 天
   * 多於 30 天

* 此外掛程式會利用 Cookie 為先前曾瀏覽的使用者加上旗標。若瀏覽器不接受 Cookie，外掛程式會傳回值 *「Cookies Not Supported」*(不支援 Cookie)。

