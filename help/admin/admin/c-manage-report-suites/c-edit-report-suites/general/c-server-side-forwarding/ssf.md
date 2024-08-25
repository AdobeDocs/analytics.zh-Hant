---
description: 伺服器端轉送功能經過精心設計，可讓客戶即時從 Analytics 將資料共用至其他 Experience Cloud 解決方案。啟用伺服器端轉送功能後，也可在資料收集過程中讓 Analytics 推送資料到其他 Experience Cloud 解決方案，並讓這些解決方案推送資料到 Analytics。
solution: Analytics
title: 伺服器端轉送總覽
feature: Server-Side Forwarding
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
role: Admin
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 100%

---

# 伺服器端轉送總覽

伺服器端轉送功能經過精心設計，可讓客戶即時從 Analytics 將資料共用至其他 Experience Cloud 解決方案。啟用伺服器端轉送功能後，也可在資料收集過程中讓 Analytics 推送資料到其他 Experience Cloud 解決方案，並讓這些解決方案推送資料到 Analytics。

伺服器端轉送可進一步改善資料收集方式，因為它：

* 可減少來自頁面的呼叫。有了伺服器端轉送，[!DNL Audience Manager] 客戶便不再需要使用 DIL 來收集資料，因為可從 Analytics 轉送資料。移除 DIL 代表消除 `"/event"` 呼叫。較少的呼叫次數有助於改善頁面載入時間，進而使網站提供更佳的客戶體驗。
* 讓您善用 Experience Cloud 解決方案之間的資料共用功能。
* 遵循我們的 Audience Manager 程式碼實施與部署最佳實務。

>[!TIP]
>
>使用 Analytics 的 Audience Manager 現有客戶應改為使用伺服器端轉送。Adobe Analytics 和 Audience Manager 的新客戶應實施伺服器端轉送 (而不是 DIL) 作為預設的資料收集和傳送方法。

>[!IMPORTANT]
>現在，根據歐盟 Cookie 法規規範，資料控管單位 (Analytics 客戶) 可以選擇將預先許可的資料限制在 Adobe Analytics，並防止其從伺服器端轉送至 Adobe Audience Manager。新的實作內容變數可讓您在未收到同意的地方標籤點擊。 設定變數時，可防止這些點擊在收到許可前傳送至 Adobe Audience Manager。如需詳細資訊，請參閱 [GDPR_ePrivacy 法規遵循與伺服器端轉送](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)。

若要瞭解貴組織實施伺服器端轉送的狀況，請進行以下驗證步驟：

## ![step1_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step1_icon.png) 確認 ECID 服務實施情形

檢查 [Analytics 追蹤請求](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html)，確認是否已實施 Experience Cloud ID (ECID) 服務。

在「請求」索引標籤中，確認 ECID 值已完成設定。此步驟可告訴您身分識別服務已正確實施，此為伺服器端轉送的必要條件。

* 如果畫面顯示 ECID 值，請繼續執行步驟 2。
* 如果未顯示 ECID 值，請先[實施身分識別服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html)，再繼續執行步驟 2。

## ![step2_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step2_icon.png) 確認伺服器端轉送實施版本

確認您是否具有已實施的伺服器端轉送版本，方法是[檢查 Analytics 追蹤請求](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)。

在「回應」索引標籤中，檢查回應是否包含 Audience Manager 資料。如果您看到：

* **Audience Manager 的 JSON 回應包含「postbacks」或「dcs_region」等項目**：您已經啟用伺服器端轉送的部分形式。繼續進行步驟 3。
* **「狀態」：「SUCCESS」**：您已實施「客群管理模組」，但未正確設定伺服器端轉送。繼續進行步驟 3。
* **2 x 2 影像**：您尚未實施伺服器端轉送或「客群管理模組」。若要修正此問題：

   * **具有 DIL 的 Adob&#x200B;&#x200B;e Audience Manager 客戶**：密切協調下列兩個項目：

      1. 移除 DIL 程式碼，並安裝[對象管理模組](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html)頁面程式碼。
      1. 在 Analytics「Admin Console」UI 中，依照步驟 3 所述的方式啟用伺服器端轉送。未移除 DIL 程式碼即啟用此設定將會使資料重複，並建立對 Audience Manager 的其他計費伺服器呼叫。

   * **新 Adobe Audience Manager 客戶** - 安裝[對象管理模組](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html)頁面程式碼，並繼續進行步驟 3。在步驟 3 中開啟伺服器端轉送前，資料將不會傳送至 Audience Manager。

## ![step3_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step3_icon.png) 確認報表套裝的伺服器端轉送實施情形

確認您是否已在報表套裝層級實施伺服器端轉送，而不是使用舊有的追蹤伺服器方法。

建議在報表套裝層級使用伺服器端轉送，而非舊有的追蹤伺服器方法，因為透過前者您可以更細微的層級控制要從 Analytics 分享的資料。這也是此 Audience Analytics 整合的必要條件。

前往&#x200B;**「Analytics** > **管理員** > **報表套裝** > (選取&#x200B;**「報表套裝」**) > **編輯設定** > **一般** > **伺服器端轉送」**。如果核取方塊為：

* **非作用中** (您無法進行選擇或選單不存在)：您沒有將選定的報表套裝對應到組織 ID。 聯絡客戶服務部 (Customer Care) 以確保報表套裝的對應正確無誤。
* **已停用**：您未開啟新的伺服器端轉送。閱讀頁面中的內容，然後繼續啟用功能。
* **已啟用**：您已佈建新的伺服器端轉送。您也可以設定此 Audience Analytics 整合。

>[!NOTE]
>
>您必須完成全部 3 個步驟，資料才會出現在 [Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html) 或 [ Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) 等其他 Experience Cloud 解決方案中。啟用後，這些設定需要數小時的時間才會生效。
