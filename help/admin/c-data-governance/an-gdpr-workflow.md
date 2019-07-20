---
description: 'null'
seo-description: 'null'
seo-title: Adobe Analytics GDPR工作流程
title: Adobe Analytics GDPR工作流程
uuid: f24e8be3-8b5c-409b-ad6 b-770198ae2549
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Adobe Analytics GDPR工作流程

歡迎使用 Adobe Analytics 和 GDPR 整備! 此工作流程概述讓您的 Adobe Analytics 實作可支援資料主體之 GDPR 存取和刪除權限的所需步驟。

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> 工作說明 </th> 
   <th colname="col3" class="entry"> 指示與更多資訊的連結 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" />確保任何可能包含 GDPR 相關資料的報表套裝皆對應至您的 Experience Cloud (或 IMS) 組織。 </p> <p>GDPR 請求已使用 Experience Cloud 組織提交，並套用至該組織申請的所有報表套裝。即使未對應至該組織的報表套裝是登入公司的一部分，請求也不會套用到這些報表套裝。 </p> </td> 
   <td colname="col3"> <p>請參閱<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">將報表套裝對應至組織</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/>設定您的資料保留政策。 </p> </td> 
   <td colname="col3"> <p>需要制定資料保留政策，以便 Adobe 為 GDPR 資料存取/刪除請求提供服務。 </p> <p>如需更多詳細資訊，請參閱這篇 <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Analytics 資料保留常見問題解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" />請熟悉 DULE/GDPR 標籤、Adobe Analytics ID、命名空間及 ID 擴增。 </p> </td> 
   <td colname="col3"> <p> 請閱讀此文件集中的這些主題: 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Analytics 變數的 GDRP 標籤</a> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">清單項目 </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> 標籤最佳實務</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" />將身分、敏感程度以及資料控管標籤，指派至報表套裝中的每個變數。 </p> <p>注意: 請記住，每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須檢閱標籤。啟用新解決方案整合時也必須檢閱標籤，因為它們可能會公開需要加上標籤的新變數。重新實作行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。 </p> </td> 
   <td colname="col3"> <p> Follow the instructions in <a href="../../admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Label Report Suite Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" />連線至 Adobe GDPR API 並提交存取與刪除請求。 </p> </td> 
   <td colname="col3"> <p>身為 Adobe Analytics 客戶，您可以藉由呼叫 <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external">Adobe Experience Cloud GDPR API</a> 來提交個別 GDPR 請求，以存取和刪除客戶資料。 </p> <p>您可以提交任何 Analytics 識別碼 (如<a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local">標籤最佳實務</a>一節中所述)，及其各自的命名空間 ID (資料來源 ID)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" />檢視及管理您的報表套裝 GDPR 設定。 </p> </td> 
   <td colname="col3"> <p>Follow the instructions in <a href="../../admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> View Report Suite's Data Governance Settings</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
