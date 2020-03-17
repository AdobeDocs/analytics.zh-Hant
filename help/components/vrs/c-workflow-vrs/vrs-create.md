---
description: 開始建立虛擬報表套裝前，請謹記以下一些注意事項。
keywords: Virtual Report Suite
title: 建立虛擬報表套裝
topic: Reports and analytics
uuid: 022a6656-808e-4c92-b7ec-4d2a42e84fa8
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 建立虛擬報表套裝

開始建立虛擬報表套裝前，請謹記以下一些注意事項。

* 非管理員使用者看不到「虛擬報表套裝管理器」。
* 虛擬報表套裝無法共用。「共用」是透過群組/權限達成。
* 在「虛擬報表套裝管理器」中，您只看得到您自己的虛擬報表套裝。必須按一下「全部顯示」才能查看其他人的虛擬報表套裝。

1. 導覽至「**[!UICONTROL 元件]** > **[!UICONTROL 虛擬報表套裝]**」。
1. 按一下&#x200B;**[!UICONTROL 「新增 +」]**。

   ![](assets/new_vrs.png)

1. 填寫欄位：

<table id="table_0F85B56480BB46CBA5BE236BBD70156D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> <p>虛擬報表套裝的名稱不會繼承自父報表套裝，且應為不同的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 說明 </td> 
   <td colname="col2"> <p>為您的企業使用者著想，加入適當說明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 標記 </td> 
   <td colname="col2"> <p>您可新增標記來組織報表套裝。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 群組  </td> 
   <td colname="col2"> <p>選取您希望可存取此 VRS 的權限群組。(您也可以從<span class="ignoretag"><span class="uicontrol">「管理員</span> &gt; <span class="uicontrol">使用者管理</span> &gt; <span class="uicontrol">群組」</span></span>管理群組權限。) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父報表套裝 </td> 
   <td colname="col2"> <p>此虛擬報套裝會繼承報表套裝的以下設定。繼承大部分的服務層級和功能 (例如 eVar 設定、處理規則、分類等)。若要在 VRS 上變更這些繼承設定，您必須編輯父報表套裝 (<span class="ignoretag"><span class="uicontrol">「管理員</span> &gt; <span class="uicontrol">報表套裝」</span></span>)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時區 </td> 
   <td colname="col2"> <p>選擇時區是選用的。 </p> <p>如果您選擇了時區，則會與 VRS 一併儲存。如果您沒有選擇時區，則系統會使用父報表套裝的時區。 </p> <p>編輯 VRS 時，隨著 VRS 儲存的時區將顯示在下拉式選擇器中。如果系統新增時區支援之前，VRS 已經建立，則父報表套裝的時區會顯示在下拉式選擇器中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 區段 </td> 
   <td colname="col2"> <p>您可以只新增一個區段，也可以<a href="https://marketing.adobe.com/resources/help/zh_TW/analytics/segment/seg_stack.html"  >堆疊區段</a>。 </p> <p> <p>注意：將兩個區段堆疊在一起時，會使用 AND 陳述式加以連結。無法變更為 OR 陳述式。 </p> </p> <p>如果嘗試刪除或修改虛擬報表套裝目前使用中的區段，便會出現警告。 </p> </td> 
  </tr> 
 </tbody> 
</table>

