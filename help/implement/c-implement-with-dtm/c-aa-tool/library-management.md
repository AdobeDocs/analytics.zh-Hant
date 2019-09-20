---
description: 動態標籤管理中「程式庫管理」設定的欄位和選項說明。
keywords: 程式庫管理；頁面代碼；載入程式庫at；由adobe;custom;code hosted;scode代管
seo-description: 動態標籤管理中「程式庫管理」設定的欄位和選項說明。
seo-title: 程式庫管理
solution: Experience Cloud，動態標籤管理
title: 程式庫管理
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 程式庫管理

動態標籤管理中「程式庫管理」設定的欄位和選項說明。

**[!UICONTROL 「*`Property`*]** &gt;編 ![](assets/settings_gear.png) 輯工具 **[!UICONTROL &gt;程式]****[!UICONTROL 庫管理」]**

>[!NOTE]
>
>如果在單一Web屬性中使用多個Adobe Analytics工具，則每個工具都必須有唯一的追蹤器變數名稱。 單一 Web 屬性內 Adobe Analytics 工具之間重複的物件變數名稱將造成衝突。

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>頁面代碼已存在 </p> </td> 
   <td colname="col2"> <p> 如果您的網站上已存在 <span class="keyword">Adobe Analytics</span> 頁面代碼，則防止動態標籤管理安裝代碼。 </p> <p>此功能可讓您使用動態標籤管理將項目新增到您現有的實施，而非從頭建立。勾選此方塊時，請確定您已正確設定追蹤器變數名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>載入程式庫，位於 &lt;<span class="term"> 頁首</span> 或頁 <span class="term"> 底</span>&gt; </p> </td> 
   <td colname="col2"> <p>指定載入頁面代碼的位置和時機。無論選取項目為何，使用 Analytics 工具的任何規則將必須具備相同的設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>由 Adobe 管理 (建議) </p> </td> 
   <td colname="col2"> <p>啟用動態標籤管理以管理您的程式庫。 </p> <p>選取此選項後，便可使用下列選項: </p> <p> <b>程式庫版本: </b>從<span class="wintitle">「程式庫版本」</span>選單中選取最新版本。當版本可用時，動態標籤管理會通知您。如需要，您可以還原為先前的版本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 自訂 </p> </td> 
   <td colname="col2"> <p>您可以配置程式庫代碼。 </p> <p>選取此選項後，便可使用下列選項: </p> <p> <b>使用以下的自訂代碼設定報表套裝: </b>核取此方塊時，動態標籤管理會在您的自訂代碼中尋找名為以下的變數: <span class="varname"> s_account</span>. 此變數應包含您想要傳送資料之以逗號區隔的報表套裝清單。 </p> <p> <b>託管的代碼:</b> 選擇選項來託管 <span class="filepath">s_code</span>: </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>位於 DTM</b>: 您可以在動態標籤管理內託管 <span class="filepath">s_code</span>。按一下<span class="uicontrol">「編輯代碼」</span>，將檔案剪下並直接貼到編輯器中。 </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL</b>: 如果您擁有正確的 <span class="filepath">s_code</span> 檔案，而且不會覺得更新該檔案很麻煩，可以在此處提供該檔案的 URL。然後，動態標籤管理便會其實施的 <span class="filepath">Adobe Analytics</span> 中取用該 <span class="keyword">s_code</span> 檔案。 </li> 
    </ul> <p> <b>開啟編輯器：可讓 </b>您插 <a href="../../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658" format="dita" scope="local"> 入核心AppMeasurement代碼</a>。 This code is populated automatically when using the automatic configuration method described in <a href="../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8" format="dita" scope="local"> Adobe Analytics Settings</a>. </p> <p> <b>追蹤器變數名稱：如 </b>果您想同時執行兩個 <span class="keyword"> Adobe Analytics例項（一個在「動態標籤管理」中，另一個在本機），您可以重新命名主</span> 要s <span class="term"></span> 物件。 重新命名物件名稱可避免衝突。 </p> </td> 
  </tr> 
 </tbody> 
</table>

