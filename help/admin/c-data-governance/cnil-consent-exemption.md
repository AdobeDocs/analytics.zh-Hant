---
description: 了解有關用戶同意在裝置或瀏覽器上儲存或讀取非必要 Cookie 的準則和建議。
title: CNIL 關於用戶同意和 Cookie 的準則是什麼？
translation-type: tm+mt
source-git-commit: fefc2433ef42bae232a9a9afc1040be8d04b2bbe
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 95%

---


# CNIL 同意豁免

2020 年 10 月 1 日，法國資料保護局 (「CNIL」) 發布了其 Cookie 指南 (以下簡稱「指南」) 的修訂版，以及有關取得用戶同意在用戶的裝置或瀏覽器上儲存或讀取非必要 Cookie 和類似技術的最終建議 (以下簡稱「建議」)。

本指南對同意要求提供了有限的豁免 (以下簡稱「同意豁免」)。同意豁免適用於 Analytics Cookie，其目的僅限於代表 Web 發行者測量網站或應用程式的對象。該指南規定，若要套用同意豁免，必須滿足以下條件：

* 最多保留 25 個月的資料。您可以在「Analytics > 管理員 > 資料管控」下查看目前的資料保留設定。[資料保留](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=zh-Hant)
* 在 ECID 中停用第三方 Cookie。[disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=zh-Hant#id-service-api)、[disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=zh-Hant#id-service-api) 和 [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=zh-Hant#id-service-api)
* 設定為靜態日期 (而非滾動) 的 13 個月 Cookie 限制。您可以使用 `cookieLifetime` 變數覆寫 Analytics Cookie 到期日期。[cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=zh-Hant)
* 有限的範圍。Cookie 的範圍必須限於單一網站或應用程式。[瀏覽器 Cookie](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=zh-Hant&quot;\l&quot;third-party-cookie-implementations)
* 匿名。將 IP 位址的最後一個八位元匿名。[一般帳戶設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=zh-Hant)
* 隱藏報表中的訪客 ID。預設情況下，無法在 Adobe Workspace 和 Adobe Reports and Analytics 中看見訪客 ID。訪客 ID 可在「資料摘要」和 Data Warehouse 中取得。對資料摘要和 Data Warehouse 的存取權可透過 [Admin Console 中的存取權限](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=zh-Hant&quot;\l&quot;task_040673FE3E3E429B9531FBCB8B6A4391)加以限制 和[資料饋送欄參考](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en#columns%2C-descriptions%2C-and-data-types)
* 地理位置參數。和郵遞區號層級比起來，地理位置可能比較不精確。[郵遞區號選項](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=zh-Hant&quot;\l&quot;zip-in-adobe-experience-platform-launch)和[一般帳戶設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=zh-Hant&quot;\l&quot;admin-tools)
* 設定「選擇加入」選項。「選擇加入」服務讓您可以設定訪客通訊協定，以確定是否能在用戶造訪您的網站時，在他們的裝置或瀏覽器上設定 Cookie。[「選擇加入」服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hant)
* 防止資料共用。若要防止與 Adobe Audience Manager 共用資料，請使用[隱私報告](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=zh-Hant&quot;\l&quot;variables)的`opt.dmp`內容變數，以封鎖點擊共用。
* 存取和刪除能力。利用隱私服務存取和刪除請求。[Analytics 及隱私服務](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=zh-Hant)

## 資料收集的其他注意事項

適用於以下其他注意事項：

* 請考慮收集 Analytics 變數中的選擇加入狀態，以便針對分段、虛擬報表套裝或路由傳送到個別端點來區分選擇加入的資料與選擇退出的資料。
* 未經事先同意，不得在網站或應用程式外部進行任何測量，例如，不進行場外活動、電子郵件活動或 iFrame。
* 未經同意，不允許收集變數中的個人資訊。[根據使用者同意控制 Experience Cloud 活動](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html?lang=en%22%20\l%20%22實作#實作)
* 資料僅用於產生匿名統計資料，而不能與其他資料合併使用。
* 資料不用於交互參照的動作。
* 未收集 GPS 地理位置資料。
* 當徵得一般用戶同意後，可以修改上述設定並放寬限制。

如需詳細資訊，請參閱 [CNIL Cookie 豁免](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications)網站。
