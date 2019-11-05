---
description: 'null'
seo-description: 'null'
seo-title: Adobe Analytics 資料隱私權工作流程
title: Adobe Analytics 資料隱私權工作流程
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Adobe Analytics 資料隱私權工作流程

歡迎使用 Adobe Analytics 和資料隱私權整備! 此工作流程概述的必要步驟，可讓您的 Adobe Analytics 實作準備好支援資料主體的資料隱私權存取和刪除權限。

<!--
<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Task Description </th> 
   <th colname="col3" class="entry"> Links to Instructions and More Information </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> Ensure that any of your report suites that might contain Data Privacy-relevant data are mapped to your Experience Cloud (or IMS) organization. </p> <p>Data Privacy requests are submitted using an Experience Cloud Organization and will be applied to all report suites claimed by that Organization. Requests will not apply to report suites not mapped to that Organization, even if they are part of your login company. </p> </td> 
   <td colname="col3"> <p>Refer to <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html"> Map report suites to an organization</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Set your data retention policy. </p> </td> 
   <td colname="col3"> <p>A data retention policy needs to be in place in order for Adobe to service Data Privacy data access/delete requests. </p> <p>For more information, see this <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html"> Analytics Data Retention FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarize yourself with DULE/Data Privacy labels, Adobe Analytics IDs, namespaces, and ID expansion. </p> </td> 
   <td colname="col3"> <p> Read these topics in this documentation set: 
     <ul> 
      <li><a href="/help/admin/c-data-governance/gdpr-labels.md"> Data Privacy Labels for Analytics Variables</a> </li> 
      <li><a href="/help/admin/c-data-governance/gdpr-analytics-ids.md"> Labeling Best Practices</a>--> </li>
    &lt;/ul&gt; &lt;/p&gt; &lt;/td&gt;
</tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" />將身分、敏感程度以及資料控管標籤，指派至報表套裝中的每個變數。 </p> <p>注意: 請記住，每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須檢閱標籤。啟用新解決方案整合時也必須檢閱標籤，因為它們可能會公開需要加上標籤的新變數。重新實作行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。 </p> </td> 
   <td colname="col3"> <p> 請依照<a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md">標籤報表套裝資料</a>的指示操作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" />連線至 Adobe 資料隱私權 API 並提交存取與刪除請求。 </p> </td> 
   <td colname="col3"> <p>As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html"> Adobe Experience Cloud Data Privacy API</a>. </p> <p>您可以提交任何 Analytics 識別碼 (如<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md">標籤最佳實務</a>一節中所述)，及其各自的命名空間 ID (資料來源 ID)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" />檢視及管理您的報表套裝資料隱私權設定。 </p> </td> 
   <td colname="col3"> <p>請依照<a href="/help/admin/c-data-governance/gdpr-view-settings.md">檢視報表套裝資料控管設定</a>的指示操作。 </p> </td> 
  </tr> 
 </tbody> 
</table>
--&gt;

| 工作說明 | 指示與更多資訊的連結 |
|--- |--- |
| **步驟 1**: 確認所有可能包含資料隱私權相關資料的報表套裝均已對應至您的 Experience Cloud (或 IMS) 組織。資料隱私權請求已使用 Experience Cloud 組織提交，並套用至該組織申請的所有報表套裝。即使未對應至該組織的報表套裝是登入公司的一部分，請求也不會套用到這些報表套裝。 | 請參閱[將報表套裝對應至組織](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)。 |
| **步驟2**:設定您的資料保留政策。 | 需要制定資料保留政策，Adobe 才能為資料隱私權資料存取/刪除請求提供服務。如需更多詳細資訊，請參閱這篇 [Analytics 資料保留常見問題集](/help/technotes/data-retention.md)。 |
| **步驟 3**: 熟悉 DULE/資料隱私權標籤、Adobe Analytics ID、命名空間及 ID 擴增。 | 請閱讀此文件集中的這些主題:<ul><li>[Analytics 變數的資料隱私權標籤](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[標籤最佳實務](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **步驟 4**: 將身分、敏感程度以及資料控管標籤，指派給報表套裝中的每個變數。注意: 請記住，每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須檢閱標籤。啟用新解決方案整合時也必須檢閱標籤，因為它們可能會公開需要加上標籤的新變數。重新實作行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。 | 請依照[標籤報表套裝資料](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)中的指示操作。 |
| **步驟 5**: 連線至 Adobe 資料隱私權 API 並提交存取與刪除請求。 | Adobe Analytics 客戶可以透過呼叫 [Adobe Experience Cloud 資料隱私權 API 來提交個別資料隱私權請求，以存取及刪除客戶資料。](https://www.adobe.io/apis/experienceplatform/gdpr.html)您可以提交任何 Analytics 識別碼 (如[標籤最佳實務](/help/admin/c-data-governance/gdpr-analytics-ids.md)一節中所述)，及其各自的命名空間 ID (資料來源 ID)。 |
| **步驟 6**: 檢視及管理您的報表套裝資料隱私權設定。 | 請依照[檢視報表套裝資料控管設定](/help/admin/c-data-governance/gdpr-view-settings.md)中的指示操作。 |
