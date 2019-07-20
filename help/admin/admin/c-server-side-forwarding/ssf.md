---
description: 伺服器端轉送功能經過精心設計，可讓客戶即時從 Analytics 將資料共用至其他 Experience Cloud 解決方案。啟用伺服器端轉送功能後，可在資料收集程序期間期間，讓 Analytics 推送資料到其他 Experience Cloud 解決方案，以及讓這些解決方案推送資料到 Analytics。
seo-description: 伺服器端轉送功能經過精心設計，可讓客戶即時從 Analytics 將資料共用至其他 Experience Cloud 解決方案。啟用伺服器端轉送功能後，可在資料收集程序期間期間，讓 Analytics 推送資料到其他 Experience Cloud 解決方案，以及讓這些解決方案推送資料到 Analytics。
seo-title: 伺服器端轉送總覽
solution: Audience Manager
title: 伺服器端轉送總覽
uuid: 22ddbde5-6805-4ea ba-8f82-6277264dcaa
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 伺服器端轉送總覽

伺服器端轉送功能經過精心設計，可讓客戶即時從 Analytics 將資料共用至其他 Experience Cloud 解決方案。啟用伺服器端轉送功能後，可在資料收集程序期間期間，讓 Analytics 推送資料到其他 Experience Cloud 解決方案，以及讓這些解決方案推送資料到 Analytics。

伺服器端轉送可進一步改善資料收集方式，因為它:

* 可減少來自頁面的呼叫。With server-side forwarding, [!DNL Audience Manager] customers no longer need to use DIL for data collection because it is being forwarded from Analytics. Removing DIL means eliminating an `"/event"` call. 較少的呼叫次數有助於改善頁面載入時間，進而使網站提供更佳的客戶體驗。
* 讓您善用 Experience Cloud 解決方案之間的資料共用功能。
* 遵循我們的 Audience Manager 程式碼實施與部署最佳實務。

>[!TIP]
>
>使用Analytics的目前Audience Manager客戶應移轉至伺服器端轉送。Adobe Analytics 和 Audience Manager 的新客戶應實作伺服器端轉送 (而不是 DIL) 作為預設的資料收集和傳送方法。

>[!IMPORTANT]
>現在，根據歐盟 Cookie 法規規範，資料控管單位 (Analytics 客戶) 可以選擇將預先許可的資料限制在 Adobe Analytics，並防止其從伺服器端轉送至 Adobe Audience Manager (AAM)。如此一來，實作環境變數有別於以往，可讓您標記未獲許可的點擊。設定變數時，可防止這些點擊在收到許可前傳送至 AAM。如需詳細資訊，請參閱 GDPR_ePrivacy 法規遵循與伺服器端轉送。

若要瞭解貴組織實作伺服器端轉送的狀況，請進行以下驗證步驟:

## ![步驟1_ icon. png影像](assets/step1_icon.png) 驗證MID服務實作

檢查 [Analytics 追蹤請求](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html)，確認是否已實作 Experience Cloud ID (MID) 服務。

在「請求」標籤中，確認已設定 MID 值。這表示Identity Service已正確實施，這是伺服器端轉送的先決條件。

* 如果您有看到 MID 值，請繼續進行步驟 2。
* If you do not see a MID value, [implement Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) before proceeding to step 2.

## ![步驟2_ icon. png影像](assets/step2_icon.png) 驗證伺服器端轉送實作版本

[檢查Analytics追蹤要求](../../../admin/admin/c-server-side-forwarding/ssf-verify.md)，確認您已實施伺服器端轉送版本。

在「回應」標籤中，檢查回應是否包含 Audience Manager 資料。如果您看到:

* **Audience Manager 的 JSON 回應包含「postbacks」或「dcs_region」等項目**: 您已經啟用伺服器端轉送的部分形式。繼續進行步驟 3。
* **「status":"SUCCESS」**: 您已實作「對象管理模組」，但未正確設定伺服器端轉送。繼續進行步驟 3。
* **2 x 2 影像**: 您尚未實作伺服器端轉送或「對象管理模組」。若要修正此問題:

   * **具有 DIL 的 AAM 客戶**: 密切協調下列兩個項目:

      1. 移除 DIL 程式碼，並安裝[對象管理模組](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html)頁面程式碼。
      1. 在 Analytics「管理控制台」UI 中，依照步驟 3 所述的方式啟用伺服器端轉送。未移除 DIL 程式碼即啟用此設定將會使資料重複，並建立對 Audience Manager 的其他計費伺服器呼叫。
   * **新 AAM 客戶**: 安裝[對象管理模組](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html)頁面程式碼，並繼續進行步驟 3。在步驟 3 中開啟伺服器端轉送前，資料將不會傳送至 Audience Manager。


## ![步驟3_ icon. png影像](assets/step3_icon.png) 驗證報表套裝的伺服器端轉送實作

確認您是否已在報表套裝層級實作伺服器端轉送，而不是使用舊有的追蹤伺服器方法。

建議在報表套裝層級使用伺服器端轉送，而非舊有的追蹤伺服器方法，因為透過前者您可以更細微的層級控制要從 Analytics 分享的資料。這也是此 Audience Analytics 整合的必要條件。

Go to **Analytics** &gt; **Admin** &gt; **Report Suites** &gt; (select **report suites**) &gt; **Edit Settings** &gt; **General** &gt; **Server Side Forwarding**. 如果核取方塊為:

* **非活動** (您無法選取或功能表不存在): 您未將選定報表套裝對應至您的 IMS 組織。請使用[報表套裝對應 UI](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)，確認適用的報表套裝已對應至正確的 IMS 組織。
* **已停用**: 您未開啟新的伺服器端轉送。閱讀頁面中的內容，然後繼續啟用功能。
* **已啟用**: 您已佈建新的伺服器端轉送。您也可以設定此 Audience Analytics 整合。

<!-- Meike, check Report Suite Mapping UI link above -->

>[!NOTE]
>
>Data will not appear in other Experience Cloud solutions, such as [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) or [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) until all 3 steps are complete. 啟用後，這些設定需要數小時的時間才會生效。

