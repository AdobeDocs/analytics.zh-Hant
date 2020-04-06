---
description: 伺服器端轉送是專為想要即時將資料從Analytics分享到其他Experience Cloud解決方案的客戶所設計。 啟用後，伺服器端轉送也可讓Analytics將資料推送至其他Experience Cloud解決方案，讓這些解決方案在資料收集程式期間將資料推送至Analytics。
solution: Audience Manager
title: 伺服器端轉送概觀
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 伺服器端轉送概觀

伺服器端轉送是專為想要即時將資料從Analytics分享到其他Experience Cloud解決方案的客戶所設計。 啟用後，伺服器端轉送也可讓Analytics將資料推送至其他Experience Cloud解決方案，讓這些解決方案在資料收集程式期間將資料推送至Analytics。

伺服器端轉送可進一步改善資料收集方式，因為它：

* 減少來自頁面的呼叫。 有了伺服器端轉送，[!DNL Audience Manager] 客戶便不再需要使用 DIL 來收集資料，因為可從 Analytics 轉送資料。移除 DIL 代表消除 `"/event"` 呼叫。較少的呼叫有助於改善頁面載入時間，進而在您的網站上提供更佳的客戶體驗。
* 可讓您運用Experience Cloud解決方案之間的資料共用。
* 遵循我們的 Audience Manager 程式碼實作與部署最佳實務。

>[!TIP]
>
>使用 Analytics 的 Audience Manager 現有客戶應改為使用伺服器端轉送。Adobe Analytics 和 Audience Manager 的新客戶應實作伺服器端轉送 (而不是 DIL) 作為預設的資料收集和傳送方法。

>[!IMPORTANT]
>現在，根據歐盟 Cookie 法規規範，資料控管單位 (Analytics 客戶) 可以選擇將預先許可的資料限制在 Adobe Analytics，並防止其從伺服器端轉送至 Adobe Audience Manager (AAM)。新的實作上下文變數可讓您在未收到同意的地方標籤點擊。 變數在設定時，會防止這些點擊傳送至AAM，直到收到同意為止。 For more information, see [GDPR_ePrivacy compliance and server-side forwarding](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md).

若要瞭解貴組織實作伺服器端轉送的狀況，請進行以下驗證步驟：

## ![step1_icon.png image](assets/step1_icon.png) 確認 ECID 服務實作情形

檢查 [Analytics 追蹤請求](https://marketing.adobe.com/resources/help/zh_TW/mcvid/mcvid-test-verify.html)，確認是否已實作 Experience Cloud ID (ECID) 服務。

在「請求」標籤中，確認 ECID 值已完成設定。此步驟可告訴您身分識別服務已正確實作，此為伺服器端轉送的必要條件。

* 如果畫面顯示 ECID 值，請繼續執行步驟 2。
* 如果未顯示 ECID 值，請先[實作身分識別服務](https://marketing.adobe.com/resources/help/zh_TW/mcvid/mcvid-implementation-guides.html)，再繼續執行步驟 2。

## ![step2_icon.png image](assets/step2_icon.png) 確認伺服器端轉送實作版本

確認您是否具有已實作的伺服器端轉送版本，方法是[檢查 Analytics 追蹤請求](/help/admin/admin/c-server-side-forwarding/ssf-verify.md)。

在「回應」標籤中，檢查回應是否包含 Audience Manager 資料。如果您看到：

* **Audience Manager 的 JSON 回應包含「postbacks」或「dcs_region」等項目**：您已經啟用伺服器端轉送的部分形式。繼續進行步驟 3。
* **「狀態」:「SUCCESS」**：您已實作「對象管理模組」，但未正確設定伺服器端轉送。繼續進行步驟 3。
* **2 x 2 影像**：您尚未實作伺服器端轉送或「對象管理模組」。若要修正此問題：

   * **具有 DIL 的 AAM 客戶**：密切協調下列兩個項目：

      1. 移除DIL程式碼並安裝 [Audience Management Module頁面程式碼](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) 。
      1. 在 Analytics「Admin Console」UI 中，依照步驟 3 所述的方式啟用伺服器端轉送。在移除DIL程式碼前啟用此設定，將會複製資料並建立對Audience Manager的額外計費伺服器呼叫。
   * **新 AAM 客戶**：安裝[對象管理模組](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html)頁面程式碼，並繼續進行步驟 3。在步驟3中開啟伺服器端轉送之前，資料不會傳送至Audience Manager。


## ![step3_icon.png image](assets/step3_icon.png) 確認報表套裝的伺服器端轉送實作情形

確認您是否已在報表套裝層級實作伺服器端轉送，而非舊式追蹤伺服器方法。

建議您在報表套裝層級進行伺服器端轉送，而非舊版追蹤伺服器方法，因為您可以在更精細的層級控制從Analytics共用的資料。 這也是此Audience Analytics整合的先決條件。

前往&#x200B;**「Analytics** > **管理員** > **報表套裝** > (選取&#x200B;**「報表套裝」**) > **編輯設定** > **一般** > **伺服器端轉送」**。如果核取方塊為：

* **非作用中** (功能表不存在或無法選取)：您未將選定的報表套裝對應至您的 IMS 組織。請使用[報表套裝對應 UI](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/about-core-services/report-suite-mapping.html)，確認適用的報表套裝已對應至正確的 Experience Cloud 組織。
* **已停用**：您未開啟新的伺服器端轉送。閱讀頁面上的內容，然後繼續啟用功能。
* **已啟用**：您已佈建新的伺服器端轉送。您也可以設定此Audience Analytics整合。

>[!NOTE] 您必須完成全部 3 個步驟，資料才會出現在 [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) 或 [ Audiences](https://marketing.adobe.com/resources/help/zh_TW/mcloud/audience_library.html) 等其他 Experience Cloud 解決方案中。啟用後，這些設定需要數小時的時間才會生效。

