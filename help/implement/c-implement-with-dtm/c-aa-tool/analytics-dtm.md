---
description: 使用動態標籤管理來部署Adobe Analytics，方法是建立Adobe Analytics工具並自動或手動設定頁面代碼。建議大多數使用者採用自動方法。
keywords: Analytics實作；實施方法；動態標籤管理；dtm；分析工具；property；工具類型；工具名稱；設定方法；分析Premium；evar；events
seo-description: 使用動態標籤管理來部署Adobe Analytics，方法是建立Adobe Analytics工具並自動或手動設定頁面代碼。建議大多數使用者採用自動方法。
seo-title: 新增Adobe Analytics工具
solution: Analytics
title: 新增Adobe Analytics工具
topic: 開發人員和實施
uuid: 1c54331e-de03-4f44-8002-a19723 c585 b0
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 新增Adobe Analytics工具

使用動態標籤管理來部署Adobe Analytics，方法是建立Adobe Analytics工具並自動或手動設定頁面代碼。建議大多數使用者採用自動方法。

>[!NOTE]
>
>For improved visitor tracking, we strongly recommend that you enable [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## 新增 Adobe Analytics 工具 {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Click  **[!UICONTROL *`Web Property Name`*]** &gt; **[!UICONTROL Overview]** &gt; **[!UICONTROL Add a Tool]** &gt; **[!UICONTROL Adobe Analytics]** .

   ![](assets/dtm-add-analytics-tool.png)

1. 填寫欄位: 

<table id="table_1CFB53FE72E74CCB8CAA5D4E3873D286"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>工具類型 </p> </td> 
   <td colname="col2">工具的類型，例如 <span class="keyword">Adobe Analytics</span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>工具名稱 </p> </td> 
   <td colname="col2">此工具的描述性名稱。此名稱會顯示<span class="wintitle">「概述」</span>索引標籤的<span class="wintitle">「已安裝工具」</span>下。 </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>「配置方法」 </p> </td> 
   <td colname="col2"> <p> <b>自動</b> (建議): 使用動態標籤管理來管理配置。This method enables automatic synchronization of <span class="keyword"> Adobe Analytics</span> report suites via a <span class="keyword"> Experience Cloud</span> login or Web Services ID, and manages the [!DNL AppMeasurement] code. </p> <p>帳戶連線之後，動態標籤管理會將 <span class="keyword">Adobe Analytics</span> 報表套裝 ID 和名稱提取至工具設定介面，讓工具部署的速度增加，並降低使用者錯誤的可能性。 </p> <p> <p>注意: 如果您是 <span class="wintitle">Adobe Analytics Premium</span> 客戶，則必須選擇<span class="keyword">自動</span>選項。請參閱以下的 <a href="../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#section_AEAA44566B5A46D2922E17A11D7EA217" format="dita" scope="local">Adobe Analytics Premium</a>。 </p> </p> <p>填寫自動配置的特定欄位: </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>: (預設) 使用 <span class="keyword">Experience Cloud</span> 單一登入。指定 Experience Cloud ID 和密碼。 </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>網站服務</b>: 指定您的網站服務使用者名稱和共用機密。 </p> <p>共用機密憑證位於<span class="uicontrol">「管理工具</span> &gt; <span class="uicontrol">公司設定</span> &gt; <a href="https://microsite.omniture.com/t2/help/en_US/reference/web_services_admin.html" format="html" scope="external">網站服務</a>」中。 </p> <p>開發人員請參閱<a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api" format="https" scope="external">取得企業 API 的網站服務存取權限</a>，以獲得取得網站服務憑證的說明。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>手冊</b>：手動管理[！DNL AppMeasurement]代碼。您可以從「<span class="keyword"></span>管理工具<span class="keyword"> &gt; </span>代碼管理員<span class="ignoretag"><span class="uicontrol">」下載 </span>Analytics<span class="uicontrol"> </span>AppMeasurement</span> 代碼。 </p> <p>Click <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html" format="https" scope="external"> JavaScript (new)</a> for information about downloading the code locally to copy and paste in the <span class="wintitle"> Edit Code</span> field in <a href="../../../implement/c-implement-with-dtm/c-aa-tool/library-management.md#concept_24654766343B4E82A9416A112D2125FE" format="dita" scope="local"> Library Management</a>. </p> <p>填寫手動配置的特定欄位: </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>生產帳戶 ID: </b>(必要) 您用於資料收集的生產帳戶。若為 Analytics，這是您的報表套裝 ID。動態標籤管理會自動在生產與測試環境中安裝正確帳戶。 </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>測試帳戶 ID: </b>(必要) 用於您的開發或測試環境。若為 Analytics，這是您的報表套裝 ID。測試帳戶可讓您的測試資料與生產資料彼此分離。 </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>追蹤伺服器: </b>指定追蹤伺服器的資訊。 </p> <p><span class="wintitle">追蹤伺服器</span>和 <span class="wintitle">SSL 追蹤伺服器</span>變數用於第一方 Cookie 實施，以指定影像要求和 Cookie 寫入所在的網域。如需詳細資訊，請參閱<a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external">正確填入 trackingServer 和 trackingServerSecure 變數</a>一文。 </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>SSL 追蹤伺服器: </b>指定 SSL 追蹤伺服器的資訊。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. 按一下&#x200B;**[!UICONTROL 「建立工具」]來建立工具，並顯示它以便進行編輯。**

   工具會顯示在[!UICONTROL 「綜覽」]索引標籤的[!UICONTROL 「已安裝工具」]下。

1. (有條件) 視需要進一步配置工具，方法是遵循以下連結中的指示: [!UICONTROL 「一般] &gt; [!UICONTROL 程式庫管理] &gt; [!UICONTROL 全域變數] &gt; [!UICONTROL 頁面檢視與內容] &gt; [!UICONTROL 連結追蹤] &gt; [!UICONTROL 反向連結與促銷活動] &gt; [!UICONTROL Cookie] &gt; [!UICONTROL 自訂頁面代碼」]。

See [Frequently Asked Questions About the Adobe Analytics Tool](../../../implement/faq.md#concept_00DF9AF14D30469BB986BF56A448806B) for additional information about this tool.

## 編輯現有的 Adobe Analytics 工具 {#section_148B16AF429B4949B06238D90635B726}

您可以編輯現有的 Adobe Analytics 工具以變更其配置配置設定。

1. 從[!UICONTROL 「概述」] 標籤按一下已安裝工具旁的 ![](assets/settings_gear.png) 圖示。
1. 視需要編輯欄位。

   下表僅包含與您建立 Analytics 工具時可用的元素不同的那些元素，如以上所述。不過，您可以變更頁面上的任何元素，如這兩個表格中所述。

<table id="table_2B60CD109CFF4839AB7F91D61125EDFF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>啟用自動配置 </p> </td> 
   <td colname="col2"> <p>Note: Enabling this setting changes a manually configured implementation to the automatic configuration method described in <span class="term"> Configuration Method</span>. </p> <p>此選項允許動態標籤管理自動擷取您 <span class="keyword">Adobe Analytics</span> 帳戶的設定。 </p> <p>最新可用[！會使用DNL AppMeasurement]程式碼，並在新版本推出時顯示升級通知。您也可以還原回之前[！DNL AppMeasurement]版本(如基於相容性原因)。最多會顯示五個先前的版本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更新憑證 </p> </td> 
   <td colname="col2"> <p>重新整理 API，例如，將報表套裝更新為與使用者產生關聯。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (有條件) 視需要進一步配置工具，方法是遵循以下連結中的指示: [!UICONTROL 「一般] &gt; [!UICONTROL 程式庫管理] &gt; [!UICONTROL 全域變數] &gt; [!UICONTROL 頁面檢視與內容] &gt; [!UICONTROL 連結追蹤] &gt; [!UICONTROL 反向連結與促銷活動] &gt; [!UICONTROL Cookie] &gt; [!UICONTROL 自訂頁面代碼」]。
1. Click **[!UICONTROL Save Changes]**.
