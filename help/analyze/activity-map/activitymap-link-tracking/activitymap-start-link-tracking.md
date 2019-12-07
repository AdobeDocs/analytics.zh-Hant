---
description: 在 Activity Map 或舊版 ClickMap 中開始進行連結追蹤的步驟。
title: 開始連結追蹤
topic: Activity map
uuid: 425cb287-f76e-4430-802f-288499711ba9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 開始連結追蹤

在 Activity Map 或舊版 ClickMap 中開始進行連結追蹤的步驟。

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 若要在此項目中開始連結追蹤... </th> 
   <th colname="col2" class="entry"> 執行動作... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> 新增 Appmeasurement.js 檔案中的下列內容: 
    <code>
     /*
     &nbsp;START&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;The&nbsp;following&nbsp;module&nbsp;enables&nbsp;Activity&nbsp;Map&nbsp;tracking&nbsp;in&nbsp;Adobe&nbsp;Analytics.&nbsp;Activity&nbsp;Map
     &nbsp;allows&nbsp;you&nbsp;to&nbsp;view&nbsp;data&nbsp;overlays&nbsp;on&nbsp;your&nbsp;links&nbsp;and&nbsp;content&nbsp;to&nbsp;understand&nbsp;how
     &nbsp;users&nbsp;engage&nbsp;with&nbsp;your&nbsp;web&nbsp;site.&nbsp;If&nbsp;you&nbsp;do&nbsp;not&nbsp;intend&nbsp;to&nbsp;use&nbsp;Activity&nbsp;Map,&nbsp;you
     &nbsp;can&nbsp;remove&nbsp;the&nbsp;following&nbsp;block&nbsp;of&nbsp;code&nbsp;from&nbsp;your&nbsp;AppMeasurement.js&nbsp;file.
     &nbsp;Additional&nbsp;documentation&nbsp;on&nbsp;how&nbsp;to&nbsp;configure&nbsp;Activity&nbsp;Map&nbsp;is&nbsp;available&nbsp;at:
     &nbsp;https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function&nbsp;AppMeasurement_Module_Activity&nbsp;Map(g){func
     ...
     /*&nbsp;END&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;*/
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (舊稱 Visitor ClickMap) </td> 
   <td colname="col2"> <p>將 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html"  >trackInlineStats</a> 變數設定為 true。語法如下: 
     <code>
       s.trackInlineStats=true
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

