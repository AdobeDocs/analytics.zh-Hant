---
description: 在行銷管道管理員中新增或啟用行銷管道。對於沒有行銷渠道的報表套裝，自動設定可為您建立多個渠道及其規則。您可視需要編輯預定義渠道或建立自己的渠道 (最多總共 25 個)。
subtopic: Marketing channels
title: 管理行銷渠道
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 管理行銷渠道

在行銷管道管理員中新增或啟用行銷管道。對於沒有行銷渠道的報表套裝，自動設定可為您建立多個渠道及其規則。您可視需要編輯預定義渠道或建立自己的渠道 (最多總共 25 個)。

以下是建立渠道的指引:

* 透過設立所有渠道的清單來提前計劃，以便將所有訪客點按歸入正確的渠道類別。
* 一律包括[內部](/help/components/c-marketing-channels/c-faq.md)點按和[直接](/help/components/c-marketing-channels/c-faq.md)點按類別的渠道。

[!UICONTROL 新增渠道至「行銷渠道」頁面，與在「行銷渠道處理規則」頁面上建立規則是相互獨立的][](/help/components/c-marketing-channels/t-rules.md)。建立規則時，您會將規則與渠道相關聯。

## 新增行銷渠道 {#add-mktg-channels}

在行銷管道管理員中新增行銷管道。

> [!NOTE] 管道無法刪除。如果不想使用渠道，則可停用或重新命名它，並保留以備將來之用。

1. 按一下&#x200B;**[!UICONTROL 「Analytics]** &gt; **[!UICONTROL 管理員]** &gt; **[!UICONTROL 報表套裝」]**。
1. 在[!UICONTROL 「報告套裝管理員」]頁面上，選擇一個報告套裝。

   如果選擇多個報表套裝，請選擇一個範本，將範本設定複製到所選的報表套裝。

   請參閱[套用範本報表套裝設定至多個報表套裝](/help/components/c-marketing-channels/t-template.md)。

1. 按一下&#x200B;**[!UICONTROL 「編輯設定]** &gt; **[!UICONTROL 行銷管道]** &gt; **[!UICONTROL 行銷管道管理員」]**。

   如果報表套裝尚未定義管道，則會顯示[自動設定](/help/components/c-marketing-channels/c-channel-autosetup.md)頁面。

1. 在[!UICONTROL 行銷管道管理員]頁面上，按一下&#x200B;**[!UICONTROL 「新增管道」]**。

   已定義 25 個渠道時，此選項不可用。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 若要設定管道規則，請按一下&#x200B;**[!UICONTROL 「行銷管道處理規則」]**。

   請參閱[建立行銷管道處理規則](/help/components/c-marketing-channels/t-rules.md)。

## 行銷管道管理員 - 介面定義 {#mktg-channel-mgr}

[!UICONTROL 行銷渠道管理員]頁面的欄位定義。

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>欄位 </p> </th> 
   <th colname="col2" class="entry"> <p>定義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>已啟用 </p> </td> 
   <td colname="col2"> <p> 啟用或停用該行銷渠道。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>渠道名稱 </p> </td> 
   <td colname="col2"> <p>行銷渠道的友好名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>覆蓋上次接觸渠道 </p> </td> 
   <td colname="col2"> <p> 可讓您選擇是否使用選取的渠道覆蓋現有的永久性上次接觸渠道。如果勾選此核取方塊，任何渠道 (包括直接和內部) 都會覆蓋現有的上次接觸渠道。產生的結果會將轉換歸屬於可能不值得該評價的渠道。例如，若之前已透過免費搜尋渠道獲得使用者，則此選項可確保直接渠道不會接收用於轉換的評價。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>渠道劃分 </p> </td> 
   <td colname="col2"> <p>允許您依該值劃分渠道。建立行銷渠道分類時，您可新增可能的渠道劃分 (子渠道)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>類型 </p> </td> 
   <td colname="col2"> <p> 指定使用者前往您網站的方式。您可選擇<span class="uicontrol">「線上」</span>或<span class="uicontrol">「離線」</span>。對於透過搜尋引擎或電子郵件促銷活動到來的訪客，您可使用「線上」渠道。「離線」渠道適用於透過報章廣告或雜誌廣告找到您網站的訪客。離線渠道通常包括從報告資料來源匯入的資料。 </p> <p>請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/"  >Data Sources</a>。 </p> <p>請參閱<a href="/help/components/c-marketing-channels/t-offline-data.md"   >新增離線資料</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>色彩 </p> </td> 
   <td colname="col2"> <p>與該行銷渠道相關的色彩。該色彩代表<span class="wintitle">行銷渠道</span>報表中的渠道。 </p> </td> 
  </tr> 
 </tbody> 
</table>

