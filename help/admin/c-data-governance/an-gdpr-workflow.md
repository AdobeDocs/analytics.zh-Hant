---
description: 'null'
seo-description: 'null'
seo-title: Adobe Analytics資料隱私權工作流程
title: Adobe Analytics資料隱私權工作流程
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: af95cc329414cfca68968c463206314aae1b8e18

---


# Adobe Analytics資料隱私權工作流程

歡迎使用Adobe Analytics和資料隱私權準備！ 此工作流程概述您需要採取哪些步驟，才能讓Adobe Analytics實作準備好支援您資料主體的資料隱私權存取和刪除權限。

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> 工作說明 </th> 
   <th colname="col3" class="entry"> 指示與更多資訊的連結 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> 請確定您的任何可能包含「資料隱私權」相關資料的報表套裝都對應至您的Experience Cloud（或IMS）組織。 </p> <p>資料隱私權要求是使用Experience cloud組織提交，且會套用至該組織宣稱擁有的所有報表套裝。 即使未對應至該組織的報表套裝是登入公司的一部分，請求也不會套用到這些報表套裝。 </p> </td> 
   <td colname="col3"> <p>Refer to <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external"> Map report suites to an organization.</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/>設定您的資料保留政策。 </p> </td> 
   <td colname="col3"> <p>Adobe必須制定資料保留政策，才能為「資料隱私權」資料存取／刪除要求提供服務。 </p> <p>For more information, see this <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external"> Analytics Data Retention FAQ.</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> 熟悉「DULE/資料隱私權」標籤、Adobe Analytics ID、命名空間和ID擴充。 </p> </td> 
   <td colname="col3"> <p> 請閱讀此文件集中的這些主題: 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><!--<a href="/help/admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Data Privacy Labels for Analytics Variables</a>--> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">清單項目 </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>--> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" />將身分、敏感程度以及資料控管標籤，指派至報表套裝中的每個變數。 </p> <p>注意: 請記住，每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須檢閱標籤。啟用新解決方案整合時也必須檢閱標籤，因為它們可能會公開需要加上標籤的新變數。重新實作行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。 </p> </td> 
   <td colname="col3"> <p> 遵循 <!--<a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Label Report Suite Data</a>-->. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> 連線至Adobe資料隱私權API並提交存取和刪除要求。 </p> </td> 
   <td colname="col3"> <p>As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external"> Adobe Experience Cloud Data Privacy API.</a> </p> <p>You can submit any Analytics identifiers (as described in the section <!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>-->) in the requests along with their respective namespace IDs (data source IDs). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> 檢視並管理您報表套裝的「資料隱私權」設定。 </p> </td> 
   <td colname="col3"> <p>遵循 <!--<a href="/help/admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> View Report Suite's Data Governance Settings</a>-->. </p> </td> 
  </tr> 
 </tbody> 
</table>

| 工作說明 | 指示與更多資訊的連結 |
|--- |--- |
| **步驟1**: 請確定您的任何可能包含「資料隱私權」相關資料的報表套裝都對應至您的Experience Cloud（或IMS）組織。  資料隱私權要求是使用Experience cloud組織提交，且會套用至該組織宣稱擁有的所有報表套裝。 即使未對應至該組織的報表套裝是登入公司的一部分，請求也不會套用到這些報表套裝。 | Refer to [Map report suites to an organization.](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html) |
| **步驟 2**: 設定您的資料保留政策。 | Adobe必須制定資料保留政策，才能為「資料隱私權」資料存取／刪除要求提供服務。  For more information, see this [Analytics Data Retention FAQ.](/help/technotes/data-retention.md) |
| **步驟3**: 熟悉「DULE/資料隱私權」標籤、Adobe Analytics ID、命名空間和ID擴充。 | 請閱讀此文件集中的這些主題:<ul><li>[Analytics變數的資料隱私權標籤](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[標籤最佳實務](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **步驟 4**: 將身分、敏感程度以及資料控管標籤，指派給報表套裝中的每個變數。注意: 請記住，每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須檢閱標籤。啟用新解決方案整合時也必須檢閱標籤，因為它們可能會公開需要加上標籤的新變數。重新實作行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。 | Follow the instructions in [Label Report Suite Data.](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) |
| **步驟5**: 連線至Adobe資料隱私權API並提交存取和刪除要求。 | As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Cloud Data Privacy API.](https://www.adobe.io/apis/experienceplatform/gdpr.html)您可以提交任何 Analytics 識別碼 (如[標籤最佳實務](/help/admin/c-data-governance/gdpr-analytics-ids.md)一節中所述)，及其各自的命名空間 ID (資料來源 ID)。 |
| **步驟6**:檢視並管理您報表套裝的「資料隱私權」設定。 | Follow the instructions in [View Report Suite's Data Governance Settings.](/help/admin/c-data-governance/gdpr-view-settings.md) |
