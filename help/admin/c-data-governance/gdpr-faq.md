---
description: Adobe Analytics 資料控管常見問題集
title: 資料控管的常見問題集
feature: Data Governance
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: 4bbed2efde0574bc9f5f6a78a022a22490e75549
workflow-type: tm+mt
source-wordcount: '2164'
ht-degree: 87%

---

# 常見問答集

+++ **Adobe Analytics 如何支援由客戶 (資料控管單位) 驗證的使用者 (資料主體) 存取和刪除請求？**

各種資料隱私權規則(GDPR、CCPA)生效後，Adobe Analytics將能支援處理由資料控管單位提交至Experience Cloud資料隱私權API的已驗證請求，以啟用更自動化的程式。 Adobe 資料隱私權 API 的設計目的，是為了協助處理客戶儲存在不同 Adobe Experience Cloud 解決方案中之資料的個別權限請求 (如存取和刪除請求)。它具有靈活彈性的特點，能因應貴公司從資料主體收到的資料存取和刪除請求數量而調整。

此外，Privacy Service API 也允許客戶查看資料存取和刪除請求的履行狀態。如需詳細資訊，請參閱 [](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)Privacy Service API 文件。 

+++

+++ **誰負責接收、接受及履行使用者的資料隱私權請求？**

資料控管單位(即Adobe客戶)應全權負責回應資料隱私權下的個人權限請求，將個人資料提供給資料主體。 資料控管單位也應全權負責接收及接受請求，也就是驗證資料主體的身分並履行請求，其中部分工作可能會需要聯絡 Adobe，告知與 Adobe Analytics 所儲存資料相關聯的資料主體 ID。

身為資料處理方，Adobe 必須為控管單位提供合理協助，在可接受的時間內處理已驗證的請求。

+++

+++ **Adobe 客戶 (資料控管單位) 如何找出哪個資料隱私權請求對應到 Adobe Analytics 中的哪個 ID，以便進行資料隱私權處理？**

資料控管單位將決定如何解析資料主體請求的身分。 請考慮部署 Adobe 的資料隱私權 ID 擷取標記。使用我們的資料隱私權 ID 擷取標記來擷取使用者 ID (Cookie ID)，再使用資料隱私權 API 將擷取的使用者 ID 傳送到 Adobe Experience Cloud 中的相關解決方案，以便處理資料隱私權請求，讓您的開發團隊節省時間。資料隱私權 API 可支援多個 Adobe 解決方案中的各種客戶 ID。

如果資料主體提交請求時一併提供了識別碼 (自訂變數為屬性或 eVar)，Adobe Analytics 會掃描針對該識別碼收集之資料的完整保留記錄。如需進一步了解如何設定Analytics prop或eVar中儲存的自訂ID，請參閱 [命名空間上的Analytics檔案](/help/admin/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **Adobe Analytics 資料控管如何協助處理資料隱私權請求？**

資料控管是 Adobe Analytics 中的新工具，能讓資料控管單位在 Analytics 資料之間套用資料控管和分類。這項新工具讓 Adobe 客戶可以自訂資料隱私權資料存取和資料刪除請求的處理方式。在資料控管主控台中，管理員可為存放在 Adobe Analytics 中不同的資料欄，定義應套用其中的所需設定。定義這些標籤後，Adobe 將根據客戶所需的標籤設定來接受及處理每個下游存取或刪除請求。資料控管單位應負責偕同其法律代表檢閱及商討這些標籤設定。Adobe Analytics鼓勵客戶在GDPR生效日期（2018年5月25日）前正確設定資料標籤，以利用資料隱私權API自訂完成請求。

資料控管工具含有以下資料標籤：

*  身分資料標籤：透過直接分類，或與其他資料結合後，可用於分類個人識別資料。(無、I1、I2)

*  敏感資料標籤：可用於分類經適用法律定義為具敏感性質的資料。(無、S1、S2) 請注意，除了依照適當法律合法取得的精確地理位置資料 (在某些管轄區屬於敏感資料) 之外，目前 Adobe Analytics 禁止使用敏感資料。

*  資料隱私權資料標籤：用來定義資料隱私權請求中可能含有個人識別碼的欄位，或是應在資料隱私權刪除請求中移除的欄位。在某些情況下，這些標籤可能會與身分資料和敏感資料標籤重疊。

如需資料控管標籤的更多資訊，請參閱 [Analytics 變數的資料隱私權標籤](/help/admin/c-data-governance/data-labeling/gdpr-labels.md)。

+++

+++ **如何驗證隱私權服務要求是否正常運作，以刪除Adobe Analytics中的資料？**

通常，Analytics客戶會先設定一些測試報表套裝來驗證功能，然後再將其發佈給一般大眾。 預先製作的網站或應用程式會傳送資料至這些測試/開發/QA 報表套裝以評估程式碼發行之後的表現，然後才會讓真正的流量傳送至生產報表套裝。

然而，若是使用標準設定，則您在將請求套用到生產報表套裝前，不能先在這些測試版報表套裝上測試 GPDR 請求處理。原因在於資料隱私權請求會自動套用至 Experience Cloud 組織中的所有報表套裝，通常就是貴公司的所有報表套裝。

在將您的資料隱私權處理套用至所有報表套裝之前，您仍然可以透過以下幾種方法進行測試：

* 一個選項是另行設定 Experience Cloud 組織，其中只包含測試報表套裝。然後使用此 Experience Cloud 組織進行資料隱私權測試，並將您的正常 Experience Cloud 組織用來進行實際的資料隱私權處理。

* 另一個選項是將不同的命名空間指派給測試報表套裝中的 ID，而不是生產報表套裝中的 ID。例如，您可以在測試報表套裝中為每個命名空間的字首加上「qa-」。當您提交僅含有 qa 字首的命名空間的資料隱私權請求時，這些請求只會針對您的測試報表套裝來執行測試。稍後，當您提交不含 qa 字首的請求時，這些請求將套用於您的生產報表套裝。**除非您使用visitorId、AAID、ECID或customVisitorId命名空間，否則建議使用此方法。 這些命名空間會以硬式編碼撰寫，且您無法在測試報表套裝中指定其替代名稱。**

+++

+++ **我該如何透過 Adobe Analytics 開始進行資料隱私權整備？**

如需針對資料隱私權規定進行整備的逐步說明，請參閱 [Adobe Analytics 資料隱私權工作流程](/help/admin/c-data-governance/an-gdpr-workflow.md)。

+++

+++ **資料控管單位應對獲取使用者互動同意抱持什麼看法？**

GDPR 和 CCPA 是讓您重新檢視同意管理策略和實務作法的良機，包括決定需要取得同意的時機，以及思考對使用者的價值主張。請思考對消費者隱私的價值主張，此舉有助於促成轉換率和忠誠度。急速演變同意管理領域 (如工具、標準、最佳實務) 十分值得關注。為了降低對使用者參與的影響，控管單位應與該領域的廠商合作，並參考他們的建議，同時遵循有關同意和 Cookie 的最新歐盟法規和指引。「體驗式隱私」(Experiential Privacy) 是個不錯的策略，您可以使用符合品牌形象的情境式相關體驗，說明資料收集活動的價值主張。

身為資料控管單位，在收集有關資料主體的資料 (可能包括 Adobe Analytics 資料) 之前，您有責任取得他們的明確同意，也必須負責在網站上實作[選擇退出機制](https://www.adobe.com/tw/privacy/opt-out.html#customeruse)。 這可讓您的資料主體退出未來的 Adobe Experience Cloud 資料收集。

+++

+++ **資料控管單位應對資料隱私權的資料保留抱持什麼看法？**

根據資料隱私權的廣泛規定，個人資料的保留時間通常不應超過達到資料收集目的所需的時間。如同 Adobe 在 2 月發佈的客戶通信內容所述，除非另有安排 (會事先通知客戶並獲得授權)，否則我們會對大多數的客戶採用 25 個月的資料保留計劃。客戶必須在 Adobe 能夠處理資料隱私權請求前，設定資料保留政策。

Adobe Analytics 會要求客戶設定處理資料隱私權請求時的資料保留時間。各報表套裝的現有資料保留政策會顯示在全新的「資料控管」管理員 UI 中。客戶如需調整其資料保留政策，應聯絡 Adobe 代表。請參閱 [Adobe Analytics資料保留常見問題集](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=en).

+++

+++ **客戶能縮短或延長預設資料保留期間嗎？**

客戶可以致電客戶服務，要求在 25 個月之內刪除他們的資料。客戶可以購買延長方案，進一步將資料保留期間延長到 25 個月以上。延長的單位以 1 (一) 年計算，最多可延長 8 (八) 年 (共計 10 年)。延長期間可能需要更新合約條款及支付額外費用。

+++

+++ **從 Adobe Analytics 匯出個人資料時，資料控管單位應考慮哪些隱私事項？**

如果客戶透過 Adobe Analytics 資料摘要從 Analytics 匯出資料到其企業資料倉儲或 Adobe 以外的其他系統，客戶 (資料控管單位) 便有責任確保刪除請求已套用到資料上。這也適用於AdobeData Workbench的內部部署實作，持續的Adobe Analytics資料摘要會填入Data Workbench資料。 Adobe 可提供工具來協助尋找及刪除特定資料摘要類型中的記錄 (包括用於 Data Workbench 的記錄)，不過客戶 (資料控管單位) 仍然有責任確保依照其內部資料保留和刪除政策來刪除資料。

員工下載含有個人資料的 Adobe Analytics 報表也是值得思考的案例。如果收到資料隱私權相關的刪除請求，而這些請求又涉及可能出現在報表中的 ID，客戶便可能需要更新或刪除這些報表。客戶應與公司的法律顧問合作，一起決定保留時間，以及應套用在這類文件上的隱私和安全要求。

+++

+++ **我們不小心將部分不應收集的資料傳入 Adobe Analytics。我們可以使用資料隱私權 API 來清除這些資料嗎？**

此 [資料Privacy ServiceAPI](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) 的用途是協助您履行資料隱私權請求，這些請求常有時效性。 Adobe 不支援將此 API 用於其他用途，這麼做可能會影響 Adobe 為其他客戶即時處理較優先、由使用者提出的資料隱私權請求。請勿將資料隱私權 API 用於其他用途，例如清除大量訪客群組不小心提交的資料。另外也請留意，任何訪客若因資料隱私權刪除請求而導致點擊遭刪除 (更新或匿名)，其狀態資訊也會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，就不會樂見發生這樣的連帶作用，這也突顯出資料隱私權 API 不適合此用途的原因。

請連絡您的客戶經理 (CSM) 來協調工程架構顧問團隊，以進一步檢視及著手移除所有 PII 或資料問題。

+++

+++ **我們的法務團隊已判定，我們多年以來自某變數收集的值不符合新版隱私權政策。我們可以使用資料隱私權 API 來清除該變數所有的值嗎？**

此 [資料Privacy ServiceAPI](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) 的用途是協助您履行資料隱私權請求，這些請求常有時效性。 Adobe 不支援將此 API 用於其他用途，這麼做可能會影響 Adobe 為其他客戶即時處理較優先、由使用者提出的資料隱私權請求。請勿將資料隱私權 API 用於其他用途，例如清除大量訪客群組不小心提交的資料。

另外也請留意，任何訪客若因資料隱私權刪除請求而導致點擊遭刪除 (更新或匿名)，其狀態資訊也會重設。訪客下一次回訪您的網站時，會變成新訪客。所有 eVar 屬性會重新開始，造訪次數、反向連結、首次造訪頁面等資訊亦同。若您希望清空資料欄位，就不會樂見發生這樣的連帶作用，這也突顯出資料隱私權 API 不適合此用途的原因。

請聯絡您的客戶經理 (CSM) 來協調工程架構顧問團隊，進一步檢視，並投入移除所有 PII 或資料問題。

+++


其他資料隱私權資源：

* [GDPR 常用詞彙](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud 資料隱私權[服務套件](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 體驗式隱私[部落格文章](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
