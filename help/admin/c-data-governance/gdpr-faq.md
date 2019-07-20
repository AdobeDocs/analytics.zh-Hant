---
description: 'null'
seo-description: 'null'
seo-title: 常見問題集
title: 常見問題集
uuid: 1cd41253-d74 f-4b92-92e6-56f9 afa3 df
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
   <td colname="col1"> <p><b>Adobe Analytics如何支援由客戶(資料掌控者)驗證的使用者(資料主體)存取和刪除請求？</b> </p> </td> 
   <td colname="col2"> <p>當 GDPR 生效時，Adobe Analytics 便會協助處理由資料控管單位提交到 Experience Cloud GDPR API 的已驗證請求，藉此提高程序的自動化程度。Adobe 的 GDPR API 的設計目的，是為了協助處理客戶儲存在不同 Adobe Experience Cloud 解決方案中之資料的個別權利請求 (如存取和刪除請求)。它具有靈活彈性的特點，能因應貴公司從資料主體收到的資料存取和刪除請求數量而調整。此外，GDPR API 還允許客戶查看資料存取和刪除請求的完成狀態。 </p> <p>如需更多詳細資料，請參閱 <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external">GDPR API 文件</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>誰負責接收、接受和履行使用者的GDPR要求？</b> </p> </td> 
   <td colname="col2"> <p>資料控管單位 (即 Adobe 客戶) 應全權負責將個人資料提供給資料主體，以符合 GDPR 下的個別權利請求。資料掌控者也負責接收要求並接受要求-驗證資料主體的身分，然後履行要求，其中包括與Adobe聯絡資料主體的ID，其中可能與儲存在Adobe Analytics中的資料關聯。身為資料處理者，Adobe 必須為控管單位提供合理的協助，在可接受的時間內處理已驗證的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe 客戶 (資料控管單位) 要如何找出哪個 GDPR 請求與 Adobe Analytics 中的哪個 ID 相對應，以便進行 GDPR 處理?</b> </p> </td> 
   <td colname="col2"> <p>資料控管單位會判斷如何解析來自資料主體請求的身分識別。Consider deploying <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external"> Adobe's GDPR ID Retrieval Tag </a>. 使用我們的 GDPR ID 擷取標記來擷取使用者 ID (Cookie ID)，再使用我們的 GDPR API 將擷取的使用者 ID 傳送到 Adobe Experience Cloud 中的相關解決方案，以便處理 GDPR 請求，讓您的開發團隊節省時間。 </p> <p>GDPR API 可支援多個 Adobe 解決方案中的各種客戶 ID。如果資料主體連同識別碼(自訂變數- prop或eVar)提交請求，則Adobe Analytics會掃描為指定識別碼收集的資料的完整保留歷史記錄。如需如何設定儲存在Analytics prop或eVar中的自訂ID的詳細資訊，請參閱[Namespaces]上的Analytics文件(/help/admin/c-data-ishance/gdpr-namespaces. md)。
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics 資料控管如何協助處理 GDPR 請求?</b> </p> </td> 
   <td colname="col2"> <p>資料控管是 Adobe Analytics 中的新工具，能讓資料控管單位在 Analytics 資料之間套用資料控管和分類。這項新工具讓 Adobe 客戶可以自訂 GDPR 資料存取和資料刪除請求的處理方式。在資料控管主控台中，管理員可為存放在 Adobe Analytics 中不同的資料欄，定義應套用其中的所需設定。定義這些標籤後，Adobe 將根據客戶所需的標籤設定，接受及處理每個下游存取或刪除請求。資料控管單位應負責偕同其法律代表檢閱及商討這些標籤設定。Adobe Analytics 鼓勵客戶在 GDPR 於 2018 年 5 月 25 日生效前設定正確的資料標籤，以便運用 GDPR API 自訂完成請求。 </p> <p>資料控管工具含有以下資料標籤: </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_D7F4E4B60D6D40BEBC86B7004EF42AFF" format="dita" scope="local">身分資料標籤</a>: 用來分類可直接或與其他資料合併使用時，識別個人身分的資料。(無、I1、I2) </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_533E1406F3F24A01B51D94139B94CAEC" format="dita" scope="local">敏感資料標籤</a>: 用來分類由適當法律定義為敏感的資料。(無、S1、S2) 請注意，除了依照適當法律合法取得的精確地理位置資料 (在某些管轄區屬於敏感資料) 之外，目前 Adobe Analytics 禁止使用敏感資料。 </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_0C7F9EC4BB414A6D915C69F1D3259F1B" format="dita" scope="local">GDPR 資料標籤</a>: 用來定義 GDPR 請求中可能含有個人識別碼的欄位，或是應在 GDPR 刪除請求中移除的欄位。在某些情況下，這些標籤可能會與身分資料和敏感資料標籤重疊。 </li> 
    </ul> <p>如需資料控管標籤的詳細資訊，請參閱 <a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local">Analytics 變數的 GDRP 標籤</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>我該如何透過 Adobe Analytics 開始進行 GDPR 整備?</b> </p> </td> 
   <td colname="col2"> <p>如需 GDPR 整備的逐步解說，請參閱 <a href="../../admin/c-data-governance/an-gdpr-workflow.md#concept_1D1C0C1EAC3B4772AEDF5CC9F0EA604B" format="dita" scope="local">Adobe Analytics GDPR 工作流程</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>資料控管單位應對獲取使用者互動同意抱持什麼看法?</b> </p> </td> 
   <td colname="col2"> <p>GDPR 是讓您重新檢視同意管理策略和實務做法的良機，包括決定需要取得同意的時機，以及思考對使用者的價值主張。請思考對消費者隱私的價值主張，此舉有助於促成轉換率和忠誠度。 </p> <p>急速演變同意管理領域 (如工具、標準、最佳實務) 十分值得關注。為了降低對使用者參與的影響，控管單位應與該領域的廠商合作，並參考他們的建議，同時遵循有關同意和 Cookie 的最新歐盟法規和指引。「體驗式隱私」(Experiential Privacy) 是個不錯的策略，您可以使用符合品牌形象的情境式相關體驗，說明資料收集活動的價值主張。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>資料控管單位應對 GDPR 的資料保留抱持什麼看法?</b> </p> </td> 
   <td colname="col2"> <p>根據 GDPR 的廣泛規定，個人資料的保留時間通常不應超過達到資料收集目的所需的時間。 </p> <p>如同 Adobe 在 2 月發佈的客戶通信內容所述，除非另有安排 (會事先通知客戶並獲得授權)，否則我們會對大多數的客戶採用 25 個月的資料保留計劃。客戶必須在 Adobe 能夠處理 GDPR 請求前，設定資料保留政策。 </p> <p>Adobe Analytics 會要求客戶設定處理 GDPR 請求時的資料保留時間。各報表套裝的現有資料保留政策會顯示在全新的「資料控管」管理員 UI 中。客戶如需調整其資料保留政策，應聯絡 Adobe 代表。請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Adobe Analytics 資料保留常見問題解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>客戶能縮短或延長預設資料保留期間嗎?</b> </p> </td> 
   <td colname="col2"> <p>客戶可以致電客戶服務，要求在 25 個月之內刪除他們的資料。客戶可購買擴充功能，將資料保留超過25個月。</p><p>
   擴充功能的增量為(一)一年，最多可超過8(8)年(總計10年)。延長期間可能需要更新合約條款及支付額外費用。
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> 從 Adobe Analytics 匯出個人資料時，資料控管單位應考慮哪些隱私事項?</b> </p> </td> 
   <td colname="col2"> <p>如果客戶透過 Adobe Analytics 資料摘要從 Analytics 匯出資料到其企業資料倉儲或 Adobe 以外的其他系統，客戶 (資料控管單位) 便有責任確保刪除請求已套用到資料上。這種情況也適用於內部部署的 Adobe Data Workbench (Insight) 實作，因為 Adobe Analytics 資料摘要會不斷填入 Data Workbench 資料。Adobe 可提供工具來協助尋找及刪除特定資料摘要類型中的記錄 (包括用於 Data Workbench 的記錄)，不過客戶 (資料控管單位) 仍然有責任確保依照其內部資料保留和刪除政策來刪除資料。 </p> <p>員工下載含有個人資料的 Adobe Analytics 報表也是值得思考的案例。如果收到 GDPR 或其他隱私相關的刪除請求，而這些請求又涉及可能出現在報表的 ID，客戶便可能需要更新或刪除這些報表。客戶應與公司的法律顧問合作，一起決定保留期間，以及應套用在這類文件上的隱私和安全要求。 </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b>我們不小心將部分不應收集的資料傳入 Adobe Analytics。Can we use the GDPR API to cleanup this data?</b> </p> </td><td colname="col2"> <p>GDPR API已提供協助您履行敏感的GDPR要求。Adobe 不支援將此 API 用於其他目的，這麼做可能會影響 Adobe 為其他客戶即時處理較優先、由使用者提出的 GDPR 請求。請您不要將 GDPR API 用於其他目的，例如清除大量訪客群組內不小心提交的資料。</p> <p>您亦應瞭解，任何訪客若因 GDPR 刪除請求而造成點擊遭刪除 (更新或匿名)，其狀態資訊亦會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，將不樂見發生這樣的連帶作用，這也突顯出 GDPR API 不適合此用途的原因。 </p> <p>請聯絡您的客戶經理(CSM)，與我們的工程結構設計師諮詢團隊進行進一步的審查，以進一步審查並提供移除任何PII或資料問題的努力。</p></td></tr> <tr> 
   <td colname="col1"> <p><b>我們的法務團隊已判定，我們多年以來自某變數收集的值不符合新版隱私權政策。我們可以使用 GDPR API 來清除該變數所有的值嗎?</b> </p> </td><td colname="col2"> <p>GDPR API已提供協助您履行敏感的GDPR要求。Adobe 不支援將此 API 用於其他目的，這麼做可能會影響 Adobe 為其他客戶即時處理較優先、由使用者提出的 GDPR 請求。請您不要將 GDPR API 用於其他目的，例如清除大量訪客群組內不小心提交的資料。</p> <p>您亦應瞭解，任何訪客若因 GDPR 刪除請求而造成點擊遭刪除 (更新或匿名)，其狀態資訊亦會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，將不樂見發生這樣的連帶作用，這也突顯出 GDPR API 不適合此用途的原因。 </p> <p>請聯絡您的客戶經理(CSM)，與我們的工程結構設計師諮詢團隊進行進一步的審查，以進一步審查並提供移除任何PII或資料問題的努力。</p></td>
 </tbody> 
</table>

其他 GDPR 資源:

* [GDPR 常用詞彙](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud GDPR [大補帖](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 體驗式隱私[部落格文章](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
