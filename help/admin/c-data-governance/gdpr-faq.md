---
description: 'null'
seo-description: 'null'
seo-title: 常見問題集
title: 常見問題集
uuid: 1cd41253-d74f-4b92-92e6-56f9afa3df85
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# 常見問題集

<table id="table_FA37A4B3960C4181B9CCDB569A476936"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics如何支援由客戶（資料掌控者）驗證的使用者（資料主體）存取和刪除要求？</b> </p> </td> 
   <td colname="col2"> <p>當各種資料隱私權規則(GDPR、CCPA)生效時，Adobe Analytics將支援處理資料掌控者提交至Experience cloud資料隱私權API的經驗證請求，以啟用更自動化的程式。 Adobe的資料隱私權API可協助處理客戶透過Adobe Experience cloud解決方案儲存的資料的個別權利要求（例如存取和刪除要求）。 它具有靈活彈性的特點，能因應貴公司從資料主體收到的資料存取和刪除請求數量而調整。此外，資料隱私權API可讓客戶檢查資料存取和刪除請求的執行方式。 </p> <p>For more details see <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external"> Data Privacy API documentation </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>由誰負責接收、接受和履行用戶的資料隱私權要求？</b> </p> </td> 
   <td colname="col2"> <p>資料掌控者（即Adobe客戶）有責任根據「資料隱私權」下的個人權利要求，向資料主體提供個人資料。 資料掌控者也負責接收要求並接受要求——驗證資料主體的身分，然後履行要求，其中部分可能包括與Adobe Analytics中儲存之資料相關的資料主體ID聯絡Adobe。 身為資料處理者，Adobe 必須為控管單位提供合理的協助，在可接受的時間內處理已驗證的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe客戶（資料掌控者）將如何找出哪些資料隱私權要求對應至Adobe Analytics中用於資料隱私權處理的ID?</b> </p> </td> 
   <td colname="col2"> <p>資料控管單位會判斷如何解析來自資料主體請求的身分識別。考慮部 <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external"> 署Adobe的資料隱私權ID擷取標籤 </a>。 您的開發團隊會使用我們的資料隱私權ID擷取標籤來擷取使用者ID(Cookie ID)，然後使用我們的資料隱私權API將這些使用者ID傳送至Adobe Experience cloud中相關的解決方案，以利資料隱私權要求處理，為您節省時間。 </p> <p>資料隱私權API可支援多個Adobe解決方案中廣泛的客戶ID。 如果資料主體提交與識別碼（自訂變數- prop或eVar）一起提交請求，Adobe Analytics會掃描為指定識別碼收集之資料的完整保留歷史記錄。 如需如何設定儲存在Analytics Prop或eVar中的自訂ID的詳細資訊，請參閱[名稱空間]上的Analytics檔案。](/help/admin/c-data-governance/gdpr-namespaces.md)
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics資料管理如何協助處理資料隱私權要求？</b> </p> </td> 
   <td colname="col2"> <p>資料控管是 Adobe Analytics 中的新工具，能讓資料控管單位在 Analytics 資料之間套用資料控管和分類。此新工具可讓Adobe客戶自訂資料隱私資料存取和資料刪除要求的處理。 在資料控管主控台中，管理員可為存放在 Adobe Analytics 中不同的資料欄，定義應套用其中的所需設定。定義這些標籤後，Adobe 將根據客戶所需的標籤設定，接受及處理每個下游存取或刪除請求。資料控管單位應負責偕同其法律代表檢閱及商討這些標籤設定。Adobe Analytics鼓勵客戶在GDPR生效日（即2018年5月25日）之前正確設定資料標籤，以便使用資料隱私API自訂完成要求。 </p> <p>資料控管工具含有以下資料標籤: </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_D7F4E4B60D6D40BEBC86B7004EF42AFF" format="dita" scope="local">身分資料標籤</a>: 用來分類可直接或與其他資料合併使用時，識別個人身分的資料。(無、I1、I2) </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_533E1406F3F24A01B51D94139B94CAEC" format="dita" scope="local">敏感資料標籤</a>: 用來分類由適當法律定義為敏感的資料。(無、S1、S2) 請注意，除了依照適當法律合法取得的精確地理位置資料 (在某些管轄區屬於敏感資料) 之外，目前 Adobe Analytics 禁止使用敏感資料。 </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_0C7F9EC4BB414A6D915C69F1D3259F1B" format="dita" scope="local"> 資料隱私資料標 </a>簽：用於定義可能包含個人識別碼的欄位，以用於「資料隱私權」要求，或應移除作為「資料隱私權」刪除要求一部分的欄位。 在某些情況下，這些標籤可能會與身分資料和敏感資料標籤重疊。 </li> 
    </ul> <p>For more information on Data Governance labels, see <a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Data Privacy Labels for Analytics Variables </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>從何處開始，開始使用Adobe Analytics來準備資料隱私權？</b> </p> </td> 
   <td colname="col2"> <p>如需準備適用「資料隱私權」規則的逐步逐步逐步說明，請參閱 <a href="../../admin/c-data-governance/an-gdpr-workflow.md#concept_1D1C0C1EAC3B4772AEDF5CC9F0EA604B" format="dita" scope="local"> Adobe Analytics資料隱私權工作流程 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>資料控管單位應對獲取使用者互動同意抱持什麼看法?</b> </p> </td> 
   <td colname="col2"> <p>GDPR和CCPA是重新考慮您的許可管理策略和做法的好機會，包括確定何時需要許可以及考慮用戶的價值主張。 請思考對消費者隱私的價值主張，此舉有助於促成轉換率和忠誠度。 </p> <p>急速演變同意管理領域 (如工具、標準、最佳實務) 十分值得關注。為了降低對使用者參與的影響，控管單位應與該領域的廠商合作，並參考他們的建議，同時遵循有關同意和 Cookie 的最新歐盟法規和指引。「體驗式隱私」(Experiential Privacy) 是個不錯的策略，您可以使用符合品牌形象的情境式相關體驗，說明資料收集活動的價值主張。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>資料掌控者在資料隱私權方面應該如何看待資料保留？</b> </p> </td> 
   <td colname="col2"> <p>資料隱私權一般規定個人資料通常不應保留超過收集目的所需的時間。 </p> <p>如同 Adobe 在 2 月發佈的客戶通信內容所述，除非另有安排 (會事先通知客戶並獲得授權)，否則我們會對大多數的客戶採用 25 個月的資料保留計劃。客戶必須先設定其資料保留政策，Adobe才能處理資料隱私權要求。 </p> <p>Adobe Analytics要求客戶設定其資料保留率，以處理其資料隱私權要求。 各報表套裝的現有資料保留政策會顯示在全新的「資料控管」管理員 UI 中。客戶如需調整其資料保留政策，應聯絡 Adobe 代表。請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Adobe Analytics 資料保留常見問題解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>客戶能縮短或延長預設資料保留期間嗎?</b> </p> </td> 
   <td colname="col2"> <p>客戶可以致電客戶服務，要求在 25 個月之內刪除他們的資料。客戶可購買擴充功能，將資料保留期延長至25個月以上。</p><p>
   擴充功能可以增加1(1)年，最多增加8(8)年（總計10年）。 延長期間可能需要更新合約條款及支付額外費用。
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> 從 Adobe Analytics 匯出個人資料時，資料控管單位應考慮哪些隱私事項?</b> </p> </td> 
   <td colname="col2"> <p>如果客戶透過 Adobe Analytics 資料摘要從 Analytics 匯出資料到其企業資料倉儲或 Adobe 以外的其他系統，客戶 (資料控管單位) 便有責任確保刪除請求已套用到資料上。這種情況也適用於內部部署的 Adobe Data Workbench (Insight) 實作，因為 Adobe Analytics 資料摘要會不斷填入 Data Workbench 資料。Adobe 可提供工具來協助尋找及刪除特定資料摘要類型中的記錄 (包括用於 Data Workbench 的記錄)，不過客戶 (資料控管單位) 仍然有責任確保依照其內部資料保留和刪除政策來刪除資料。 </p> <p>員工下載含有個人資料的 Adobe Analytics 報表也是值得思考的案例。如果收到與資料隱私權相關的刪除要求，且該要求涉及報表中可能顯示的ID，則這些報表可能需要更新或刪除。 客戶應與公司的法律顧問合作，一起決定保留期間，以及應套用在這類文件上的隱私和安全要求。 </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b>我們不小心將部分不應收集的資料傳入 Adobe Analytics。我們是否可以使用資料隱私權API來清除此資料？</b> </p> </td><td colname="col2"> <p>提供資料隱私API可協助您履行資料隱私權要求，此要求會有時間限制。 Adobe不支援將此API用於其他用途，並可能會影響Adobe為其他Adobe客戶提供高優先順序、使用者啟動的資料隱私權要求的能力。 我們要求您不要將資料隱私API用於其他用途，例如清除在大型訪客群組間意外提交的資料。</p> <p>您也應該注意，任何因「資料隱私權」刪除要求而遭到刪除（更新或匿名）點擊的訪客，都會重設其狀態資訊。 訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。當您想要清除資料欄位時，此副作用是不可取的，並強調資料隱私API不適用於此用途的一個原因。 </p> <p>請連絡您的客戶經理(CSM)，與我們的工程架構顧問團隊協作，以進一步審查並提供移除任何PII或資料問題的工作層級。</p></td></tr> <tr> 
   <td colname="col1"> <p><b>我們的法務團隊已判定，我們多年以來自某變數收集的值不符合新版隱私權政策。Can we use the Data Privacy API to clear out all values from this variable?</b> </p> </td><td colname="col2"> <p>提供資料隱私API可協助您履行資料隱私權要求，此要求會有時間限制。 Adobe不支援將此API用於其他用途，並可能會影響Adobe為其他Adobe客戶提供高優先順序、使用者啟動的資料隱私權要求的能力。 我們要求您不要將資料隱私API用於其他用途，例如清除在大型訪客群組間意外提交的資料。</p> <p>您也應該注意，任何因「資料隱私權」刪除要求而遭到刪除（更新或匿名）點擊的訪客，都會重設其狀態資訊。 訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。當您想要清除資料欄位時，此副作用是不可取的，並強調資料隱私API不適用於此用途的一個原因。 </p> <p>請連絡您的客戶經理(CSM)，與我們的工程架構顧問團隊協作，以進一步審查並提供移除任何PII或資料問題的工作層級。</p></td>
 </tbody> 
</table>

其他資料隱私權資源：

* [GDPR 常用詞彙](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience cloud資料隱私權 [服務套件](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 體驗式隱私[部落格文章](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
