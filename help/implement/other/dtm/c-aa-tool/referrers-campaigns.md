---
description: 在 Adobe Analytics 中部署 Dynamic Tag Management 時，Dynamic Tag Management 中用於反向連結與促銷活動選項的欄位說明。
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: 反向連結與促銷活動
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# 反向連結與促銷活動

Field descriptions in [!UICONTROL Dynamic Tag Management] for referrers and campaign options when deploying [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

**[!UICONTROL  *`Property`*]** >齒輪 ![圖示](assets/settings_gear.png) > **[!UICONTROL Edit Tool]****[!UICONTROL Referrers & Campaigns]**

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
   <td colname="col2"> <p>覆寫s.referrer變數中設 <span class="varname"> 定的值</span> ，此變數通常由瀏覽器中設定的反向連結填入。 </p> <p>請參閱 <a href="../../../vars/page-vars/referrer.md">反向連結</a>。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 促銷活動 </td>
   <td colname="col2"> <p>一種變數，可識別用來吸引訪客進入您網站的行銷促銷活動。 促銷活動的值通常取自查詢字串參數。 </p> <p>請參閱 <a href="../../../vars/page-vars/campaign.md">促銷活動</a>。 </p> </td>
  </tr>
 </tbody>
</table>

使用 DTM 介面來選擇您要使用查詢字串或值 (可能從資料元素提取):

![查詢參數](assets/dtm-queryparam.png)

您可以在介面中輸入您的查詢字串，或是如果您有追蹤促銷活動的其他方法，則可以參考個別的資料元素。
