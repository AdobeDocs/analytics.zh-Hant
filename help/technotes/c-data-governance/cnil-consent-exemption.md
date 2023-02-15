---
description: 了解有關使用者同意在裝置或瀏覽器上儲存或讀取非必要 Cookie 的準則和建議。
title: CNIL 關於使用者同意和 Cookie 的準則是什麼？
feature: Data Governance
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
source-git-commit: 1ca7040156f7f2105a9625f921de3d90b4175056
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 75%

---

# CNIL 同意豁免

2020年10月1日，法國資料保護局(「CNIL」)發佈其Cookie准則（「准則」）的修訂版本及其最終建議，以取得使用者同意在使用者的裝置或瀏覽器上儲存或讀取非必要Cookie和類似技術(「Recommendations」)。

本准則對同意要求提供有限豁免（「同意豁免」）。 同意豁免適用於 Analytics Cookie，其目的僅限於代表 Web 發行者測量網站或應用程式的對象。該指南規定，若要套用同意豁免，必須滿足以下條件：

* 最多保留 25 個月的資料。您可以在 [!UICONTROL Analytics] > [!UICONTROL 管理] > [!UICONTROL 資料控管].  [資料保留](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=zh-Hant)
* 在 ECID 中停用協力廠商 Cookie。[disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html#id-service-api)、[disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html#id-service-api) 和 [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html#id-service-api)
* 13 個月的 Cookie 限制。您可以使用 `cookieLifetime` 變數覆寫 Analytics Cookie 到期日期。Experience Cloud Cookie (包括 Analytics 和 ECID) 會隨著每次瀏覽延長 Cookie 到期日。若要設定靜態、非滾動的 Cookie 有效期，您可以：(1) 撰寫自訂程式碼，設定刪除 Cookie 的日期，或 (2) 使用您的 CMP 控制 Cookie 重設的日期。[cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=zh-Hant) 和 [Experience Cloud Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html#ec-cookies)
* 有限的範圍。Cookie 的範圍必須限於單一網站或應用程式。[瀏覽器 Cookie](https://experienceleague.adobe.com/docs/analytics/technotes/cookies/cookies.html#third-party-cookie-limitations)
* 匿名。將 IP 位址的最後一個八位元匿名。[一般帳戶設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
* 隱藏報表中的訪客 ID。預設情況下，無法在 Adobe Workspace 和 Adobe Reports and Analytics 中看見訪客 ID。訪客 ID 可在「資料摘要」和 Data Warehouse 中取得。對資料摘要和 Data Warehouse 的存取權可透過 [Admin Console 中的存取權限](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html)加以限制 和[資料摘要欄位參考資料](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html#columns%2C-descriptions%2C-and-data-types)
* 地理位置參數。和郵遞區號層級比起來，地理位置可能比較不精確。[郵遞區號選項](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=zh-Hant)和[一般帳戶設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* 設定「選擇加入」選項。選擇加入服務可讓您設定訪客通訊協定，以判斷您是否可在使用者造訪網站時，在使用者的裝置或瀏覽器上設定Cookie。 [「選擇加入」服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* 防止資料共用。若要防止與 Adobe Audience Manager 共用資料，請使用[隱私報告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)的`opt.dmp`內容變數，以封鎖點擊共用。
* 存取和刪除能力。利用 Privacy Service 存取和刪除請求。[Analytics 及 Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=zh-Hant)

## 資料收集的其他注意事項

適用於以下其他注意事項：

* Adobe Analytics 在美國、英國和新加坡經營資料處理中心，以便為所有客戶提供在區域中收集、處理和儲存資料的靈活性。設定Adobe Analytics的初始設定時，客戶可以選擇所需的資料處理中心位置。 客戶的資料最終會儲存在其核心Analytics產品的所選地區。
* 請考慮收集 Analytics 變數中的選擇加入狀態，以便針對分段、虛擬報告套裝或路由傳送到個別端點來區分選擇加入的資料與選擇退出的資料。
* 未經事先同意，不得在網站或應用程式外部進行任何測量，例如，不進行場外活動、電子郵件活動或 iFrame。
* 未經同意，不允許收集變數中的個人資訊。[根據使用者同意控制 Experience Cloud 活動](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html#implementing-opt-in-on-the-page)
* 資料僅用於產生匿名統計資料，而不能與其他資料合併使用。
* 資料不用於交互參照的動作。
* 未收集 GPS 地理位置資料。
* 當徵得一般使用者同意後，可以修改上述設定並放寬限制。

>[!IMPORTANT]
>
>本檔案並非作為法律或法規建議，也不構成本Adobe的任何保證或合約承諾。 我們鼓勵客戶就與本主題相關的事宜尋求有關客戶法律及法規義務的獨立法律建議。


如需詳細資訊，請參閱 [CNIL Cookie 豁免](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications)網站。

