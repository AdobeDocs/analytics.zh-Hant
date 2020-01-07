---
description: 在 Adobe Analytics 中部署動態標籤管理時，動態標籤管理中用於反向連結與促銷活動選項的欄位說明。
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: 反向連結與促銷活動
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: ht
source-git-commit: e9820869d16b8656ebebe11e397a3d7d8123fbcf

---


# 反向連結與促銷活動

在 Adobe [!DNL Analytics] 中部署 [!UICONTROL Dynamic Tag Management] 時，[!UICONTROL Dynamic Tag Management] 中用於反向連結與促銷活動選項的欄位說明。

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) **[!UICONTROL 編輯工具]** &gt; **[!UICONTROL 反向連結與促銷活動]**

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
   <td colname="col2"> <p>覆寫<span class="varname"> s.referrer</span> 變數中所設定的值，該變數通常是由瀏覽器中設定的反向連結填入。 </p> <p>請參閱<a href="/help/implement/js-implementation/page-variables/page-variables.md">頁面變數</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 促銷活動 </td> 
   <td colname="col2"> <p>變數，可識別用以吸引訪客進入網站的促銷活動。促銷活動的值通常取自查詢字串參數。 </p> <p>請參閱<a href="/help/implement/js-implementation/page-variables/campaign.md">頁面變數</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

使用 DTM 介面來選擇您要使用查詢字串或值 (可能從資料元素提取):

![](assets/dtm-queryparam.png)

您可以在介面中輸入您的查詢字串，或是如果您有追蹤促銷活動的其他方法，則可以參考個別的資料元素。
