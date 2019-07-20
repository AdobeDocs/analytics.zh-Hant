---
description: 在 Adobe Analytics 中部署動態標籤管理時，動態標籤管理中用於反向連結與促銷活動選項的欄位說明。
keywords: 動態標籤管理；反向連結；促銷活動；反向連結覆蓋；促銷活動變數；查詢參數
seo-description: 在 Adobe Analytics 中部署動態標籤管理時，動態標籤管理中用於反向連結與促銷活動選項的欄位說明。
seo-title: 反向連結和促銷活動
solution: Marketing Cloud，Analytics，動態標籤管理
title: 反向連結和促銷活動
uuid: 56580206-a382-4993-9bba-a488 da65 cf89
translation-type: tm+mt
source-git-commit: e271cf73e7fd31d8893ed57112f2f3bb7821fbdd

---


# 反向連結和促銷活動

Field descriptions in [!UICONTROL Dynamic Tag Management] for referrers and campaign options when deploying [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png)**[!UICONTROL 編輯工具]** &gt; **[!UICONTROL 反向連結和促銷活動]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 反向連結覆寫 </td> 
   <td colname="col2"> <p>覆寫<span class="varname"> s. referrer</span> 變數，此變數通常由瀏覽器中設定的反向連結填入。 </p> <p>請參閱[頁面變數](/help/implement/js-implementation/c-variables/page-variables/page-variables. md)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 促銷活動 </td> 
   <td colname="col2"> <p>變數，可識別用以吸引訪客進入網站的促銷活動。促銷活動的值通常取自查詢字串參數。 </p> <p>請參閱[頁面變數](/help/implement/js-implementation/c-variables/page-variables/page-variables. md)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

使用 DTM 介面來選擇您要使用查詢字串或值 (可能從資料元素提取):

![](assets/dtm-queryparam.png)

您可以在介面中輸入您的查詢字串，或是如果您有追蹤促銷活動的其他方法，則可以參考個別的資料元素。
