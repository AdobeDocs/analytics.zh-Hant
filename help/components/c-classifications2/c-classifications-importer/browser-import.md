---
description: 您可以使用瀏覽器匯入 (上傳) 分類資料。這種方法限制您的分類資料上傳只能上傳單一的報表套裝
subtopic: Classifications
title: 瀏覽器匯入
topic: Admin tools
uuid: 56dfbf4c-36e6-49f4-b5cb-8ab714432825
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 瀏覽器匯入

您可以使用瀏覽器匯入 (上傳) 分類資料。這種方法限制您的分類資料上傳只能上傳單一的報表套裝

## 瀏覽器匯入 {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

您可以使用瀏覽器匯入 (上傳) 分類資料。這種方法限制您的分類資料上傳只能上傳單一的報表套裝

**[!UICONTROL 管理員]** &gt; **[!UICONTROL 分類匯入工具]**

## 分類瀏覽器匯入 - 欄位說明 {#section_F628C47081DA4026A4D30E3D3454B1DA}

<table id="table_7FC7E510E7E74C2D9E8F316C5C6B66DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 選取報表套裝 </td> 
   <td colname="col2"> <p>您要匯入分類資料的報表套裝。匯入資料檔案必須與報表套裝中資料集的格式相符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 要分類的資料集 </td> 
   <td colname="col2"> <p>要接收分類的資料集。下拉式清單含有報表套裝中所有已針對分類設定的報告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 選取要匯入的 檔案 </td> 
   <td colname="col2"> <p>可讓您瀏覽以找出您要上傳的匯入資料檔案。 </p> <p>注意: 上傳檔案大小限制是 1 MB。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 覆寫衝突的資料 </td> 
   <td colname="col2"> <p>自動覆寫與匯入之資料衝突的現有資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 在匯入完成之後自動下載分類檔案 </td> 
   <td colname="col2"> <p>自動下載一個定位點分隔檔案，這個檔案代表包含新上傳之分類資料的資料集。如果匯入作業建立任何唯一 ID 或發生任何錯誤，Adobe 會自動產生此檔案。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 透過瀏覽器匯入分類 {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

<!-- 

t_upload_a_saint_data_file_via_web_browser.xml

 -->

1. 按一下&#x200B;**[!UICONTROL 「管理員]** &gt; **[!UICONTROL 分類匯入工具」]**。
1. 按一下&#x200B;**[!UICONTROL 「匯入檔案」]**。
1. 設定&#x200B;**[!UICONTROL 瀏覽器匯入]**&#x200B;欄位。
1. 按一下&#x200B;**[!UICONTROL 「匯入檔案」]**。
1. 觀察狀態視窗中的處理訊息。
1. (條件性) 若您選取&#x200B;**[!UICONTROL 上傳完成時自動下載分類檔案]**，需指定處理完成時要將產生的檔案儲存於何處。
>成功的匯入作業會立即顯示匯出內容中的正確變更。然而，報告中的資料變更需花費 4 小時 (使用瀏覽器匯入) 到 24 小時 (使用 FTP 匯入) 的時間。

