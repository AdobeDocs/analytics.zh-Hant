---
description: 瞭解使用者同意在裝置或瀏覽器上儲存或讀取非必要Cookie的准則和建議。
title: CNIL的使用者同意和Cookie准則為何
translation-type: tm+mt
source-git-commit: c5ebc92622e012699d64c27701b24a88429e9f4f
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---


# CNIL同意豁免

於2020年10月1日，法國資料保護局(「CNIL」)發佈其Cookie准則（「准則」）修訂版，並就取得使用者同意在使用者裝置或瀏覽器上儲存或讀取非必要Cookie和類似技術之最終建議（「建議」）。

本准則對同意要求提供有限豁免（「同意豁免」）。 「同意豁免」適用於分析Cookie，其目的僅限於僅代表網頁發行者測量網站或應用程式的讀者。 《准則》規定，如要適用「同意豁免」，必須執行下列條件：

* 最多25個月的資料保留率。  您可以在「分析>管理>資料管理」下檢視目前的資料保留設定。  [資料保留](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* 13個月Cookie限制。  您可以使用`cookieLifetime`變數覆寫分析Cookie有效期。  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html)
* 範圍有限。 Cookie的範圍必須限制為單一網站或應用程式。 [瀏覽器Cookie](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=en&quot;\l&quot;third-party-cookie-implementations)
* 匿名. 使IP位址的最後八位元匿名。 [一般帳戶設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* 隱藏訪客ID，使其不受報告影響。  依預設，訪客ID在Adobe工作區和Adobe報告與分析中不可見。  「資料饋送」和「資料倉庫」中提供訪客ID。  存取「資料饋送」和「資料倉庫」的權限可受「管理控制台」中的「存取權限」限制[](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en&quot;\l&quot;task_040673FE3E3E429B9531FBCB8B6A4391)
* 地理位置參數。 地理位置的精確度不比郵遞區號層級高。 [郵遞](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en&quot;\l&quot;zip-in-adobe-experience-platform-launch) 區號選 [項和一般帳戶設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=en&quot;\l&quot;admin-tools)
* 設定選擇加入選項。  「選擇加入」服務可讓您設定訪客通訊協定，以判斷您是否可在使用者造訪網站時在使用者的裝置或瀏覽器上設定Cookie。 [選擇加入服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* 防止資料共用。  若要防止資料共用給Adobe Audience Manager，請使用[隱私權報告](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=en&quot;\l&quot;變數)的`opt.dmp`上下文變數來封鎖點擊無法共用。
* 存取和刪除功能。 使用隱私權服務存取和刪除要求。 [Analytics與隱私權服務](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## 資料收集的其他考量事項

需要考慮以下事項：

* 未經事先同意，網站或應用程式外不得進行測量，例如不得進行站外促銷活動、電子郵件促銷活動或iFrames。
* 未經同意，不得收集變數中的個人資訊。
* 資料只能用來產生匿名統計資料，而不與其他資料結合。
* 資料不會用於交叉參考動作。
* 不會收集GPS地理位置資料。

如需詳細資訊，請參閱[CNIL Cookie免除](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications)網站。
