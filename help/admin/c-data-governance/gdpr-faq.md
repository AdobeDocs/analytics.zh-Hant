---
description: 'null'
title: 常見問題集
uuid: 1cd41253-d74f-4b92-92e6-56f9afa3df85
translation-type: ht
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

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
   <td colname="col1"> <p><b>Adobe Analytics 如何支援由客戶 (資料控管單位) 驗證的使用者 (資料主體) 存取和刪除請求？</b> </p> </td> 
   <td colname="col2"> <p>各種資料隱私權規定 (GDPR、CCPA) 生效時，Adobe Analytics 會協助處理由資料控管單位提交到 Experience Cloud 資料隱私權 API 的已驗證請求，藉此提高程序的自動化程度。Adobe 資料隱私權 API 的設計目的，是為了協助處理客戶儲存在不同 Adobe Experience Cloud 解決方案中之資料的個別權限請求 (如存取和刪除請求)。它具有靈活彈性的特點，能因應貴公司從資料主體收到的資料存取和刪除請求數量而調整。此外，資料隱私權 API 還允許客戶查看資料存取和刪除請求的履行狀態。 </p> <p>如需更多詳細資料，請參閱<a href="https://www.adobe.io/apis/cloudplatform/gdpr.html">資料隱私權 API 文件</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>誰負責接收、接受及履行使用者的資料隱私權請求？</b> </p> </td> 
   <td colname="col2"> <p>根據資料隱私權之規定，資料控管單位 (即 Adobe 客戶) 應全權負責回應個別權限請求，將個人資料提供給資料主體。資料控管單位也應全權負責接收及接受請求，也就是驗證資料主體的身分並履行請求，其中部分工作可能會需要聯絡 Adobe，告知與 Adobe Analytics 所儲存資料相關聯的資料主體 ID。身為資料處理方，Adobe 必須為控管單位提供合理協助，在可接受的時間內處理已驗證的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe 客戶 (資料控管單位) 如何找出哪個資料隱私權請求對應到 Adobe Analytics 中的哪個 ID，以便進行資料隱私權處理？</b> </p> </td> 
   <td colname="col2"> <p>資料控管單位會判斷該如何解析資料主體請求的身分。請考慮部署 <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm">Adobe 的資料隱私權 ID 擷取標記。</a>使用我們的資料隱私權 ID 擷取標記來擷取使用者 ID (Cookie ID)，再使用資料隱私權 API 將擷取的使用者 ID 傳送到 Adobe Experience Cloud 中的相關解決方案，以便處理資料隱私權請求，讓您的開發團隊節省時間。 </p> <p>資料隱私權 API 可支援多個 Adobe 解決方案中的各種客戶 ID。如果資料主體提交請求時一併提供了識別碼 (自訂變數為屬性或 eVar)，Adobe Analytics 會掃描針對該識別碼收集之資料的完整保留記錄。如需進一步瞭解如何設定 Analytics prop 或 eVar 中儲存的自訂 ID，請參閱<a href="/help/admin/c-data-governance/gdpr-namespaces.md">命名空間</a>上的 Analytics 文件。
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics 資料控管如何協助處理資料隱私權請求？</b> </p> </td> 
   <td colname="col2"> <p>資料控管是 Adobe Analytics 中的新工具，能讓資料控管單位在 Analytics 資料之間套用資料控管和分類。這項新工具讓 Adobe 客戶可以自訂資料隱私權資料存取和資料刪除請求的處理方式。在資料控管主控台中，管理員可為存放在 Adobe Analytics 中不同的資料欄，定義應套用其中的所需設定。定義這些標籤後，Adobe 將根據客戶所需的標籤設定來接受及處理每個下游存取或刪除請求。資料控管單位應負責偕同其法律代表檢閱及商討這些標籤設定。Adobe Analytics 鼓勵客戶在 2018 年 5 月 25 日資料隱私權生效前設定正確的資料標籤，以便運用資料隱私權 API 自訂完成請求。 </p> <p>資料控管工具含有以下資料標籤： </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="/help/admin/c-data-governance/gdpr-labels.md#identity-data-labels"> 身分資料標籤</a>：透過直接分類，或與其他資料結合後，可用於分類個人識別資料。(無、I1、I2) </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="/help/admin/c-data-governance/gdpr-labels.md#sensitive-data-labels"> 敏感資料標籤</a>：可用於分類經適用法律定義為具敏感性質的資料。(無、S1、S2) 請注意，除了依照適當法律合法取得的精確地理位置資料 (在某些管轄區屬於敏感資料) 之外，目前 Adobe Analytics 禁止使用敏感資料。 </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels"> 資料隱私權資料標籤</a>：用來定義資料隱私權請求中可能含有個人識別碼的欄位，或是應在資料隱私權刪除請求中移除的欄位。在某些情況下，這些標籤可能會與身分資料和敏感資料標籤重疊。 </li> 
    </ul> <p>如需「資料控管」標籤的更多資訊，請參閱 <a href="/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels">Analytics 變數的資料隱私權標籤</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>我該如何透過 Adobe Analytics 開始進行資料隱私權整備？</b> </p> </td> 
   <td colname="col2"> <p>如需針對資料隱私權規定進行整備的逐步說明，請參閱 <a href="/help/admin/c-data-governance/an-gdpr-workflow.md">Adobe Analytics 資料隱私權工作流程</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>資料控管單位應對獲取使用者互動同意抱持什麼看法？</b> </p> </td> 
   <td colname="col2"> <p>GDPR 和 CCPA 是讓您重新檢視同意管理策略和實務作法的良機，包括決定需要取得同意的時機，以及思考對使用者的價值主張。請思考對消費者隱私的價值主張，此舉有助於促成轉換率和忠誠度。 </p> <p>急速演變同意管理領域 (如工具、標準、最佳實務) 十分值得關注。為了降低對使用者參與的影響，控管單位應與該領域的廠商合作，並參考他們的建議，同時遵循有關同意和 Cookie 的最新歐盟法規和指引。「體驗式隱私」(Experiential Privacy) 是個不錯的策略，您可以使用符合品牌形象的情境式相關體驗，說明資料收集活動的價值主張。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>資料控管單位應對資料隱私權的資料保留抱持什麼看法？</b> </p> </td> 
   <td colname="col2"> <p>根據資料隱私權的廣泛規定，個人資料的保留時間通常不應超過達到資料收集目的所需的時間。 </p> <p>如同 Adobe 在 2 月發佈的客戶通信內容所述，除非另有安排 (會事先通知客戶並獲得授權)，否則我們會對大多數的客戶採用 25 個月的資料保留計劃。客戶必須在 Adobe 能夠處理資料隱私權請求前，設定資料保留政策。 </p> <p>Adobe Analytics 會要求客戶設定處理資料隱私權請求時的資料保留時間。各報表套裝的現有資料保留政策會顯示在全新的「資料控管」管理員 UI 中。客戶如需調整其資料保留政策，應聯絡 Adobe 代表。請參閱 <a href="https://marketing.adobe.com/resources/help/zh_TW/reference/data-retention-client-table-faq.html">Adobe Analytics 資料保留的常見問題集</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>客戶能縮短或延長預設資料保留期間嗎？</b> </p> </td> 
   <td colname="col2"> <p>客戶可以致電客戶服務，要求在 25 個月之內刪除他們的資料。客戶可以購買延長方案，進一步將資料保留期間延長到 25 個月以上。</p><p>
   延長的單位以 1 (一) 年計算，最多可延長 8 (八) 年 (共計 10 年)。延長期間可能需要更新合約條款及支付額外費用。
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> 從 Adobe Analytics 匯出個人資料時，資料控管單位應考慮哪些隱私事項？</b> </p> </td> 
   <td colname="col2"> <p>如果客戶透過 Adobe Analytics 資料摘要從 Analytics 匯出資料到其企業資料倉儲或 Adobe 以外的其他系統，客戶 (資料控管單位) 便有責任確保刪除請求已套用到資料上。這種情況也適用於內部部署的 Adobe Data Workbench (Insight) 實作，因為 Adobe Analytics 資料摘要會不斷填入 Data Workbench 資料。Adobe 可提供工具來協助尋找及刪除特定資料摘要類型中的記錄 (包括用於 Data Workbench 的記錄)，不過客戶 (資料控管單位) 仍然有責任確保依照其內部資料保留和刪除政策來刪除資料。 </p> <p>員工下載含有個人資料的 Adobe Analytics 報表也是值得思考的案例。如果收到資料隱私權相關的刪除請求，而這些請求又涉及可能出現在報表中的 ID，客戶便可能需要更新或刪除這些報表。客戶應與公司的法律顧問合作，一起決定保留時間，以及應套用在這類文件上的隱私和安全要求。 </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b>我們不小心將部分不應收集的資料傳入 Adobe Analytics。我們可以使用資料隱私權 API 來清除這些資料嗎？</b> </p> </td><td colname="col2"> <p>資料隱私權 API 的用途為協助您履行資料隱私權請求，這些請求常有時效性。Adobe 不支援將此 API 用於其他用途，這麼做可能會影響 Adobe 為其他客戶即時處理較優先、由使用者提出的資料隱私權請求。請勿將資料隱私權 API 用於其他用途，例如清除大量訪客群組不小心提交的資料。</p> <p>另外也請留意，任何訪客若因資料隱私權刪除請求而導致點擊遭刪除 (更新或匿名)，其狀態資訊也會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，就不會樂見發生這樣的連帶作用，這也突顯出資料隱私權 API 不適合此用途的原因。 </p> <p>請連絡您的客戶經理 (CSM) 來協調工程架構顧問團隊，以進一步檢視及著手移除所有 PII 或資料問題。</p></td></tr> <tr> 
   <td colname="col1"> <p><b>我們的法務團隊已判定，我們多年以來自某變數收集的值不符合新版隱私權政策。我們可以使用資料隱私權 API 來清除該變數所有的值嗎？</b> </p> </td><td colname="col2"> <p>資料隱私權 API 的用途為協助您履行資料隱私權請求，這些請求常有時效性。Adobe 不支援將此 API 用於其他用途，這麼做可能會影響 Adobe 為其他客戶即時處理較優先、由使用者提出的資料隱私權請求。請勿將資料隱私權 API 用於其他用途，例如清除大量訪客群組不小心提交的資料。</p> <p>另外也請留意，任何訪客若因資料隱私權刪除請求而導致點擊遭刪除 (更新或匿名)，其狀態資訊也會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，就不會樂見發生這樣的連帶作用，這也突顯出資料隱私權 API 不適合此用途的原因。 </p> <p>請連絡您的客戶經理 (CSM) 來協調工程架構顧問團隊，以進一步檢視及著手移除所有 PII 或資料問題。</p></td>
 </tbody> 
</table>

其他資料隱私權資源：

* [GDPR 常用詞彙](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud 資料隱私權[服務套件](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 體驗式隱私[部落格文章](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
