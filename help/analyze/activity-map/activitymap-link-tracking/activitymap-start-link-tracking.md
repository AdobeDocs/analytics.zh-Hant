---
description: 在 Activity Map 或舊版 ClickMap 中開始進行連結追蹤的步驟。
seo-description: 在 Activity Map 或舊版 ClickMap 中開始進行連結追蹤的步驟。
seo-title: 開始連結追蹤
solution: Analytics
title: 開始連結追蹤
topic: Activity Map
uuid: 425cb287-f76 e-4430-802f-288499711ba9
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

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
   <td colname="col2"> 新增 Appmeasurement.js 檔案中的下列內容:<code>/* START Activity Map模組下列模組啓用Adobe Analytics中的Activity Map追蹤。Activity Map可讓您檢視連結和內容上的資料覆蓋，以瞭解使用者如何與您的網站互動。如果您不打算使用Activity Map，可以從AppMeasurement. js檔案移除下列程式碼區塊。
  Additional documentation on how to configure Activity Map is available at:
      https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function AppMeasurement_Module_Activity Map(g){func
     ...
     /* END Activity Map MODULE */
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (舊稱 Visitor ClickMap) </td> 
   <td colname="col2"> <p>將 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external">trackInlineStats</a> 變數設定為 true。The syntax reads as follows: 
     <code>
       s.trackInlineStats=true
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

