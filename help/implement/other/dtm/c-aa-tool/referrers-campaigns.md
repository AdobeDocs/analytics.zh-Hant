---
description: 在 Adobe Analytics 中部署動態標籤管理時，動態標籤管理中用於反向連結與促銷活動選項的欄位說明。
keywords: Dynamic Tag Management;反向連結;促銷活動;反向連結覆寫;促銷活動變數;查詢參數
solution: Experience Cloud,Analytics
title: 反向連結與促銷活動
uuid: 56580206-a382-4993-9bba-a488da65cf89
exl-id: cced5e00-ba8e-4bf4-b475-ed8ab08ab427
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '166'
ht-degree: 100%

---

# 反向連結與促銷活動

在 Adobe [!DNL Analytics] 中部署 [!UICONTROL Dynamic Tag Management] 時，[!UICONTROL Dynamic Tag Management] 中用於反向連結與促銷活動選項的欄位說明。

**[!UICONTROL *`Property`*]**> ![齒輪圖示](assets/settings_gear.png)**[!UICONTROL &#x200B;編輯工具&#x200B;]**>**[!UICONTROL &#x200B;反向連結與促銷活動&#x200B;]**

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
   <td colname="col2"> <p>覆寫<span class="varname"> s.referrer</span> 變數中所設定的值，該變數通常是由瀏覽器中設定的反向連結填入。 </p> <p>請參閱 <a href="../../../vars/page-vars/referrer.md">referrer</a>。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 促銷活動 </td>
   <td colname="col2"> <p>變數，可識別用以吸引訪客進入網站的促銷活動。促銷活動的值通常取自查詢字串參數。 </p> <p>請參閱 <a href="../../../vars/page-vars/campaign.md">campaign</a>。 </p> </td>
  </tr>
 </tbody>
</table>

使用 DTM 介面來選擇您要使用查詢字串或值 (可能從資料元素提取)：

![查詢參數](assets/dtm-queryparam.png)

您可以在介面中輸入您的查詢字串，或是如果您有追蹤促銷活動的其他方法，則可以參考個別的資料元素。
