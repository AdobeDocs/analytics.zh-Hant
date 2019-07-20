---
description: 在 Activity Map 或舊版 ClickMap 中停止連結追蹤的步驟。
seo-description: 在 Activity Map 或舊版 ClickMap 中停止連結追蹤的步驟。
seo-title: 停止連結追蹤
solution: Analytics
title: 停止連結追蹤
topic: Activity Map
uuid: e17fb7bd-d6 ed-45c3-a006-9150d5718 cff
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 停止連結追蹤

在 Activity Map 或舊版 ClickMap 中停止連結追蹤的步驟。

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 若要在此項目中停止連結追蹤... </th> 
   <th colname="col2" class="entry"> 執行動作... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> 移除 Appmeasurement.js 檔案中的下列內容:<code>/* START Activity Map模組下列模組啓用Adobe Analytics中的Activity Map追蹤。Activity Map可讓您檢視連結和內容上的資料覆蓋，以瞭解使用者如何與您的網站互動。如果您不打算使用Activity Map，可以從AppMeasurement. js檔案移除下列程式碼區塊。
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
   <td colname="col2"> <p>將 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external">trackInlineStats</a> 變數設定為 false (此為預設值)。The syntax reads as follows: 
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

