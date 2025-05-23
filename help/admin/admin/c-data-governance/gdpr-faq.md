---
description: Adobe Analytics 資料控管常見問題集
title: 資料控管的常見問題集
feature: Data Governance
role: Admin
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: ht
source-wordcount: '2042'
ht-degree: 100%

---

# 常見問題

+++ **Adobe Analytics 如何支援由客戶 (資料控管單位) 驗證的使用者 (資料主體) 存取和刪除請求？**

各種資料隱私權規定 (GDPR、CCPA) 生效時，Adobe Analytics 會協助處理由資料控管單位提交到 Experience Cloud 資料隱私權 API 的已驗證請求，藉此提高程序的自動化程度。Adobe 資料隱私權 API 的設計目的，是為了協助處理客戶儲存在不同 Adobe Experience Cloud 解決方案中之資料的個別權限請求 (如存取和刪除請求)。那具有靈活彈性的特點，能因應貴公司從資料主體收到的資料存取和刪除請求數量而調整。

此外，Privacy Service API 也允許客戶查看資料存取和刪除請求的履行狀態。如需詳細資訊，請參閱 [](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)Privacy Service API 文件。 

+++

+++ **誰負責接收、接受及履行使用者的資料隱私權請求？**

資料控制者全權負責接收和接受請求。資料控管單位驗證資料主體的身分，然後履行請求。此責任的一部分可能涉及使用儲存在 Adobe Analytics 中的相關聯資料主體 ID 聯繫 Adobe。

身為資料處理者，Adobe 必須為控管單位提供合理的協助，在可接受的時間內處理已驗證的請求。

+++

+++ **Adobe 客戶 (資料控管單位) 如何找出哪個資料隱私權請求對應到 Adobe Analytics 中的哪個 ID，以便進行資料隱私權處理？**

資料控管單位會判斷如何解析來自資料主體請求的身分識別。請考慮部署 Adobe 的資料隱私權 ID 擷取標記。您的開發團隊透過使用我們的資料隱私權 ID 檢索標記擷取使用者 ID (cookie ID) 以節省時間。然後，他們可以使用我們的資料隱私權 API，將那些使用者 ID 發送到 Adobe Experience Cloud 中的相關解決方案，以進行資料隱私權請求處理。資料隱私權 API 可支援多個 Adobe 解決方案中的各種客戶 ID。

如果資料主體連同識別碼一併提交請求 (自訂變數為 prop 或 eVar)，Adobe Analytics 便會掃描針對該識別碼所收集完整的資料保留記錄。如需進一步了解如何設定 Analytics prop 或 eVar 中儲存的自訂 ID，請參閱[命名空間上的 Analytics 文件](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md)。

+++

+++ **Adobe Analytics 資料控管如何協助處理資料隱私權請求？**

資料控管是 Adobe Analytics 中的新工具，提供資料控管單位在 Analytics 資料之間套用資料控管和分類的能力。這項新工具讓 Adobe 客戶可以自訂資料隱私權資料存取和資料刪除請求的處理方式。在資料控管主控台中，管理員可為存放在 Adobe Analytics 中不同的資料欄，定義應套用其中的所需設定。定義這些標籤後，Adobe 將根據客戶所需的標籤設定來接受及處理每個下游存取或刪除請求。資料控管單位應負責偕同其法律代表檢閱及商討這些標籤設定。

資料控管工具含有以下資料標籤：

* **身分識別資料標籤**：透過直接分類，或與其他資料結合後，可用於進行個人身分識別資料的分類。(無、I1、I2)

* **敏感資料標籤**：可用於分類經適用法律定義為敏感性質的資料。(無、S1、S2) 請注意，除了依照適當法律合法取得的精確地理位置資料 (在某些管轄區屬於敏感資料) 之外，目前 Adobe Analytics 禁止使用敏感資料。

* **資料隱私權資料標籤**：用於定義資料隱私權請求中可能含有個人識別碼的欄位，或是應在資料隱私權刪除請求中移除的欄位。在某些情況下，這些標籤可能會與身分識別資料和敏感資料標籤重疊。

如需資料控管標籤的更多資訊，請參閱 [Analytics 變數的資料隱私權標籤](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md)。

+++

+++ **我如何驗證 Privacy Service 請求是否正常運作，以便從 Adobe Analytics 中刪除資料？**

通常，Analytics 客戶會在向大眾發布之前，先行設定一些測試報告套裝以驗證功能。預先製作的網站或應用程式會傳送資料至這些測試/開發/QA 報告套裝，以評估程式碼發布之後的執行狀況，然後才會讓真正的流量傳送至生產報告套裝。

然而，若是使用標準設定，則您在將請求套用到生產報告套裝前，不能先在這些測試版報告套裝上測試 GPDR 請求處理。這是因為資料隱私權請求會自動套用至 Experience Cloud 組織中的所有報告套裝，通常就是貴公司的所有報告套裝。

不過，在套用至所有報告套裝之前，您仍然可以透過以下幾種方法測試您的資料隱私權處理：

* 一個選項是另行設定 Experience Cloud 組織，其中只包含測試報表套裝。然後使用此 Experience Cloud 組織進行資料隱私權測試，並將您的正常 Experience Cloud 組織用來進行實際的資料隱私權處理。

* 另一個選項是將不同的命名空間指派給測試報表套裝中的 ID，而不是生產報表套裝中的 ID。例如，您可以在測試報表套裝中為每個命名空間的字首加上「qa-」。當您提交僅含有 qa 字首的命名空間的資料隱私權請求時，這些請求只會針對您的測試報表套裝來執行測試。稍後，當您提交不含 qa 字首的請求時，這些請求將套用於您的生產報表套裝。**推薦使用此方法，除非您使用的是 visitorId、AAID、ECID 或 customVisitorId 命名空間。這些命名空間是硬式編碼，您不能在測試報表套裝中指定它們的替代名稱。**

+++

+++ **我該如何透過 Adobe Analytics 開始進行資料隱私權整備？**

如需針對資料隱私權規定進行整備的逐步說明，請參閱 [Adobe Analytics 資料隱私權工作流程](/help/admin/admin/c-data-governance/an-gdpr-workflow.md)。

+++

+++ **資料控管單位對於取得使用者參與的同意抱持什麼看法？**

GDPR 和 CCPA 是重新考慮您的同意管理策略和實務的好機會。這包括確定何時需要同意並考慮使用者的價值提議。請思考對消費者隱私權的價值提議，此舉有助於促成轉換率和忠誠度。同意管理領域 (例如工具、標準、最佳做法) 演變迅速，十分值得關注。為了降低對使用者參與的影響，控管單位應與該領域的廠商及其法律顧問合作，以確保遵循關於同意和 Cookie 的最新法規和指引。「體驗式隱私」(Experiential Privacy) 是個不錯的策略，您可以使用符合品牌形象的情境式相關體驗，說明資料收集活動的價值提議。

身為資料控管單位，在收集有關資料主體的資料 (可能包括 Adobe Analytics 資料) 之前，您有責任取得他們的明確同意，也必須負責在網站上實作[選擇退出機制](https://www.adobe.com/tw/privacy/opt-out.html#customeruse)。 這可讓您的資料主體選擇退出未來的 Adobe Experience Cloud 資料收集。

+++

+++ **資料控管單位應對資料隱私權的資料保留抱持什麼看法？**

個人資料的保留時間通常不應超過達到資料收集目的所需的時間。 Adobe 的一般條款適用預設的 25 個月資料保留計畫，除非在契約協議了不同的資料保留期限。客戶必須在 Adobe 能夠處理資料隱私權請求前，設定其資料保留政策。

各報告套裝的現有資料保留政策會顯示在全新的「資料控管」管理員 UI 中。如需調整其資料保留政策，客戶應與 Adobe 代表聯絡。請參閱 [Adobe Analytics 資料保留常見問題集](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=zh-Hant)。

+++

+++ **客戶可以縮短或延長預設資料保留期間嗎？**

客戶可以致電客戶服務，要求在比 25 個月更短的時間內刪除他們的資料。客戶還可以購買延長方案，進一步將資料保留期間延長到 25 個月以上。延長的單位以多 1 (一) 年漸增計算，最多可延長 8 (八) 年 (共計 10 年)。延長期間將需要更新契約條款及支付額外費用。

+++

+++ **從 Adobe Analytics 匯出個人資料時，資料控管單位應考慮哪些隱私事項？**

如果客戶透過 Adobe Analytics 資料摘要從 Analytics 匯出資料到其企業資料倉儲或 Adobe 以外的其他系統，客戶 (資料控管單位) 便有責任確保刪除請求已套用到資料上。這種情況也適用於內部部署的 Adobe Data Workbench 實作，因為 Adobe Analytics 資料摘要會不斷填入 Data Workbench 資料。Adobe 可提供工具來協助尋找及刪除特定資料摘要類型中的記錄 (包括用於 Data Workbench 的記錄)，不過客戶 (資料控管單位) 仍然有責任確保依照其內部資料保留和刪除政策來刪除資料。

請同時思考員工已下載含有個人資料之 Adobe Analytics 報告的情況。如果收到涉及 ID 出現在報告中的資料隱私權相關刪除請求，這些報告可能需要更新或刪除。客戶應與其公司的法律顧問合作決定保留期間，以及應套用在這類文件上的隱私權和安全性要求。

+++

+++ **我們意外將部分不應收集的資料傳入 Adobe Analytics。我們可以使用資料隱私權 API 清除這些資料嗎？**

[資料隱私權 API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) 的用途為協助您履行資料隱私權請求，這些請求常有時效性。Adobe 不支援將此 API 用於其他用途，這麼做可能會影響 Adobe 為其他客戶及時處理較優先、由使用者提出的資料隱私權請求。

請勿將資料隱私權 API 用於其他用途，例如清除大量訪客群組不小心提交的資料。另外也請留意，任何訪客若因資料隱私權刪除請求而導致點擊遭刪除 (更新或匿名)，其狀態資訊也會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，就不會樂見發生這樣的連帶作用，這也突顯出資料隱私權 API 不適合此用途的原因。

請和您的 Adob&#x200B;&#x200B;e 客戶團隊聯絡，與我們的工程架構顧問團隊進行協調，以進一步檢閱並提供移除任何 PII 或資料問題所需的努力。

+++

+++ **我們的法務團隊已判定，我們多年以在一個變數所收集的值已經不符合新版的隱私權政策。我們可以使用資料隱私權 API 來清除該變數所有的值嗎？**

[資料隱私權 API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) 的用途為協助您履行資料隱私權請求，這些請求常有時效性。Adobe 不支援將此 API 用於其他用途，這麼做可能會影響 Adobe 為其他客戶即時處理較優先、由使用者提出的資料隱私權請求。請勿將資料隱私權 API 用於其他用途，例如清除大量訪客群組不小心提交的資料。

另外也請留意，任何訪客若因資料隱私權刪除請求而導致點擊遭刪除 (更新或匿名)，其狀態資訊也會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，就不會樂見發生這樣的連帶作用，這也突顯出資料隱私權 API 不適合此用途的原因。

請和您的 Adob&#x200B;&#x200B;e 客戶團隊聯絡，與我們的工程架構顧問團隊進行協調，以進一步檢閱並提供移除任何 PII 或資料問題所需的努力。

+++

其他資料隱私權資源：

* [GDPR 常用詞彙](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud 資料隱私權[服務套件](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 體驗式隱私[部落格文章](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
