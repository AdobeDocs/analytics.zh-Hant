---
description: Dynamic Tag Management 中「程式庫管理」設定的欄位和選項說明。
keywords: library management;page code;load library at;managed by adobe;custom;code hosted;s_code hosted
solution: Experience Cloud,Dynamic Tag Management
title: 程式庫管理
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
translation-type: ht
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# 程式庫管理

Dynamic Tag Management 中「程式庫管理」設定的欄位和選項說明。

**[!UICONTROL *`Property`*]**>![](assets/settings_gear.png)**[!UICONTROL &#x200B;編輯工具&#x200B;]**>**[!UICONTROL &#x200B;程式庫管理&#x200B;]**

> [!NOTE]如果在單一 Web 屬性中使用了超過一個 Adobe Analytics 工具，每個工具必須具有獨特的追蹤器變數名稱。單一 Web 屬性內 Adobe Analytics 工具之間重複的物件變數名稱將造成衝突。

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>頁面程式碼已存在 </p> </td> 
   <td colname="col2"> <p> 如果您的網站上已存在 <span class="keyword">Adobe Analytics</span> 頁面程式碼，則防止 Dynamic Tag Management 安裝程式碼。 </p> <p>此功能可讓您使用 Dynamic Tag Management 將項目新增到您現有的實施，而非從頭建立。勾選此方塊時，請確定您已正確設定追蹤器變數名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>載入程式庫，位於 &lt;<span class="term"> 頁面頂端</span>或<span class="term">頁面底部</span>&gt; </p> </td> 
   <td colname="col2"> <p>指定載入頁面程式碼的位置和時機。無論選取項目為何，使用 Analytics 工具的任何規則將必須具備相同的設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>由 Adobe 管理 (建議) </p> </td> 
   <td colname="col2"> <p>啟用 Dynamic Tag Management 以管理您的程式庫。 </p> <p>選取此選項後，便可使用下列選項: </p> <p> <b>程式庫版本：</b>從<span class="wintitle">「程式庫版本」</span>選單中選取最新版本。當版本可用時，動態標籤管理會通知您。如需要，您可以還原為先前的版本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 自訂 </p> </td> 
   <td colname="col2"> <p>您可以配置程式庫程式碼。 </p> <p>選取此選項後，便可使用下列選項: </p> <p> <b>使用以下的自訂程式碼設定報表套裝：</b>核取此方塊時，Dynamic Tag Management 會在您的自訂程式碼中尋找名為以下的變數：  <span class="varname"> s_account</span>。此變數應包含您想要傳送資料之以逗號區隔的報表套裝清單。 </p> <p> <b>託管的程式碼：</b> 選擇託管 <span class="filepath">s_code</span> 的選項： </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>位於 DTM</b>：您可以在 Dynamic Tag Management 內託管 <span class="filepath">s_code</span>。按一下<span class="uicontrol">「編輯程式碼」</span>，將檔案剪下並直接貼到編輯器中。 </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL</b>：如果您擁有正確的 <span class="filepath">s_code</span> 檔案，而且不會覺得更新該檔案很麻煩，可以在此處提供該檔案的 URL。然後，動態標籤管理便會其實施的 <span class="filepath">Adobe Analytics</span> 中取用該 <span class="keyword">s_code</span> 檔案。 </li> 
    </ul> <p> <b>開啟編輯器：</b>可讓您<a href="/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md"  >插入核心 AppMeasurement 程式碼</a>。使用如 <a href="/help/implement/other/dtm/c-aa-tool/analytics-dtm.md"  >Adobe Analytics 設定</a>所述的自動配置方法時，會自動填入此程式碼。 </p> <p> <b>追蹤器變數名稱：</b>如果您要平行執行兩個 <span class="keyword"> Adobe Analytics</span> 例項 (一個在 Dynamic Tag Management 中，一個在原生程式中)，您可以重新命名主要的 <span class="term">s</span> 物件。重新命名物件名稱可避免衝突。 </p> </td> 
  </tr> 
 </tbody> 
</table>

