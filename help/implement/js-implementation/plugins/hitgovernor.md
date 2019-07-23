---
description: s.hitGovernor 外掛程式可在預先定義的滾動時間範圍期間，追蹤傳送的 Analytics 影像請求總數，若總數超過特定的臨界值，則可執行其他邏輯。
seo-description: s.hitGovernor 外掛程式可在預先定義的滾動時間範圍期間，追蹤傳送的 Analytics 影像請求總數，若總數超過特定的臨界值，則可執行其他邏輯。
seo-title: hitGovernor
title: hitGovernor
uuid: d9091ee-005a-43c2-b419-980b795 bc2 a9
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# hitGovernor

s.hitGovernor 外掛程式可在預先定義的滾動時間範圍期間，追蹤傳送的 Analytics 影像請求總數，若總數超過特定的臨界值，則可執行其他邏輯。

## hitGovernor {#topic_56B636A42A624B38A0A446C607ACD700}

s.hitGovernor 外掛程式可在預先定義的滾動時間範圍期間，追蹤傳送的 Analytics 影像請求總數，若總數超過特定的臨界值，則可執行其他邏輯。

雖然系統可將來自機器人、編目程式、特定使用者代理，或 IP 位址特定清單的流量，識別為機器人流量或以其他方式從報表中排除，但報表套裝可能仍會擷取到不應計算的流量。例如，不合理時間內的高點擊數或頁面檢視數 (即約每秒一個請求)，可能為假性流量。

使用此外掛程式可讓系統自動封鎖該訪客剩餘期間的流量，並在報表中動態識別該流量。

## Hit Governor 外掛程式的運作方式 {#section_541BC639E31442D09B1C85A2FFCDC02C}

每次影像請求傳送至追蹤伺服器時，外掛程式都會增加 Cookie 值，並在滾動時間範圍期間追蹤該請求。預設的時間範圍為 1 分鐘，但您可以覆寫時間範圍。(請參閱[下方的實施](../../../implement/js-implementation/plugins/hitgovernor.md#task_D4BDB524AA294C139AFCAE2B61FEA3F2)。)If the total number of hits during that time frame exceeds the default hit threshold (60), a final custom link image request is sent to set the *`exceptionFlag`* context data variable. 您也可以覆寫預設的點擊次數臨界值。

可視需要自該值起，停止收集特定訪客的流量，預設時間為 60 天。封鎖流量需要在 doPlugins 函數中，新增一行程式碼 (如下所示)。您也能調整時間範圍。The logic allows time to either include that visitor's IP address, User Agent, or [!DNL Experience Cloud] Visitor ID in the proper permanent exception logic, or to reset the timeout period after the sixty days have elapsed. 若 60 天後，外掛程式將該流量識別為假性流量，系統會再次將該流量標記為例外，並在另一個 60 天期間停止收集該流量。

## 報告 {#section_E742F19B528041808454744DB2C7007C}

不需要設定預設變數或事件。但是，我們強烈建議您設定處理規則邏輯，據以設定變數和事件。那些自訂變數和事件可能包括:

* [!DNL Experience Cloud] 訪客 ID
* IP 位址
* 使用者代理
* 已標記的例外事件

為那些變數建立區段，可讓您建立區段和虛擬報表套裝，以檢視這些不明確點擊的整體網站影響。

我們建議使用報表中擷取的值，來更新機器人規則、DB VISTA 規則，或公司 IP 排除項目。

## 實施 {#task_D4BDB524AA294C139AFCAE2B61FEA3F2}

若要實施 hitGovernor 外掛程式:

1. 修改 AppMeasurement 程式庫。

   若要初始化外掛程式，請將此行程式碼，(以粗體字) 包含在 AppMeasurement 程式庫程式碼的 `registerPostTrackCallback` 函數中。

   >[!NOTE]
   >
   >`registerPostTrackCallback` 雖然AppMeasurement程式庫1.8.0+中包含此功能，但預設不會包含在任何自訂代碼設定中。此函數會包含在 doPlugins 函數之後和&#x200B;*之外*。

   ```
    s.registerPostTrackCallback(function(){ 
       
<b> s.governor();</b> 
   });
   ```

   Below the doPlugins section of your AppMeasurement file, include the plugin code contained in [Plugin Source Code](../../../implement/js-implementation/plugins/hitgovernor.md#reference_76423C81A7A342B2AC4BE41490B27DE0), below.

   The hit limit threshold, hit timing threshold, and traffic exclusion time frames can all be overridden by setting these variables, outside of the plugin itself and preferably with your other configuration variables:

<table id="table_9959A40F5F0B40B39DB86E21D03E25FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Syntax </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Hit Limit Threshold </p> </td> 
   <td colname="col2"> <p> <code> s.hl = 60; </code> </p> </td> 
   <td colname="col3"> <p>The total number of hits that should not be exceeded during a given timeframe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hit Time Threshold </p> </td> 
   <td colname="col2"> <p> <code> s.ht = 10; </code> </p> </td> 
   <td colname="col3"> <p>The window, in seconds, for when hits are recorded. This number is divided by six to determine the rolling timing windows. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclusion Threshold </p> </td> 
   <td colname="col2"> <p> <code> s.he = 60; </code> </p> </td> 
   <td colname="col3"> <p>Number of days that the exclusion cookie is set for that visitor. </p> </td> 
  </tr> 
 </tbody> 
</table>

   >[!NOTE]
   >
   >Your implementation might use a different object name than the default analytics "s" object. If so, please update the object name accordingly.

1. Configure processing rules.

   This plugin records flagged exceptions as context data in a link tracking image request. As such, processing rules must be configured to assign track those flagged exceptions into appropriate variables like those below.

   ![](assets/hitgov-config.png)

1. (Optional) Include the traffic-blocking code in doPlugins.

   After traffic has been identified as an exception, any subsequent hits from that visitor can be blocked entirely by including this code within the `doPlugins` function:

   ```
   //Check for hit governor flag 
         if(s.Util.cookieRead('s_hg')==9)s.abort=true;
   ```

   If this code is not included, traffic from that visitor will be flagged but not blocked. 

## Plugin Source Code {#reference_76423C81A7A342B2AC4BE41490B27DE0}

This code should be added below the doPlugins section of your AppMeasurement library.

```
//Hit Governor (Version 0.1 BETA, 11-13-17) 
s.governor=new Function("","" 
+"var s=this;if(typeof s.hl=='undefined'){s.hl=60;}if(typeof s.ht=='u" 
+"ndefined'){s.ht=60;}if(typeof s.he=='undefined'){s.he=60;}if(s.Util" 
+".cookieRead('s_hg')==8){var i=new Date(),y=i.getFullYear(),m=i.getM" 
+"onth(),d=i.getDate(),i=new Date(y,m,d+s.he);s.Util.cookieWrite('s_h" 
+"g',9,i);return;}var f=s.Util.cookieRead('s_hc'),g=Number(s.Util.coo" 
+"kieRead('s_ht')),h=Math.floor((new Date()).getTime()),ha=f!=''?f.sp" 
+"lit('|').map(Number):[0,0,0,0,0],i=ha.reduce(function(ha,b){return " 
+"ha+b;},0),j=g==0?0:Math.floor(((h-g)/(s.ht/6))/1000);if(g==0)s.Util" 
+".cookieWrite('s_ht',h);if(i<s.hl){if(j>=1){if(j>=6){ha=[0,0,0,0,0];" 
+"}else{for(var k=0;k<j;k++){ha.unshift(0);ha.pop();}}s.Util.cookieWr" 
+"ite('s_ht',h);}}else{s.Util.cookieWrite('s_hg',8);s.linkTrackVars+=" 
+"',contextData.exceptionFlag';s.contextData['exceptionFlag']='true';" 
+"s.tl(this,'o','exceptionFlag');}ha[0]++;s.Util.cookieWrite('s_hc',h" 
+"a.join('|'));"); 

```

