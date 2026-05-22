---
description: 了解有關使用者同意在裝置或瀏覽器上儲存或讀取非必要 Cookie 的準則和建議。
title: CNIL 關於使用者同意和 Cookie 的準則是什麼？
feature: Data Governance
role: Admin
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
TQID: https://experienceleague.adobe.com/DNqDZWOm1buhq-vLG3io11v-s-7SAXfb6W3A9VAOtXw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 769
ht-degree: 91%

---

# CNIL 同意豁免

2020 年 10 月 1 日，法國資料保護局 (「CNIL」) 發布了其 Cookie 指南 (以下簡稱「指南」) 的修訂版，以及有關取得使用者同意在使用者的裝置或瀏覽器上儲存或讀取非必要 Cookie 和類似技術的最終建議 (以下簡稱「建議」)。

本指南對同意要求提供了有限的豁免 (以下簡稱「同意豁免」)。 同意豁免適用於 Analytics Cookie，其目的僅限於代表 Web 發行者測量網站或應用程式的客群。 該指南規定，若要套用同意豁免，必須滿足以下條件：

* 最多保留 25 個月的資料。  您可以在[!UICONTROL 「Analytics >]>[!UICONTROL &#x200B; 管理員] > [!UICONTROL 資料管控]」下查看目前的資料保留設定。  [資料保留](/help/technotes/data-retention.md)
* 在 ECID 中停用協力廠商 Cookie。 [disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=zh-Hant#id-service-api)、[disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=zh-Hant#id-service-api) 和 [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=zh-Hant#id-service-api)
* 13 個月的 Cookie 限制。  您可以使用 `cookieLifetime` 變數覆寫 Analytics Cookie 期限。 CX Enterprise Cookie （包括Analytics和ECID）可延長每次造訪的Cookie到期日。  若要設定靜態、非滾動的Cookie有效期，您可以：(1)撰寫自訂程式碼，設定刪除Cookie的日期，或(2)使用您的CMP控制Cookie重設的日期。  [cookieLifetime](/help/implement/vars/config-vars/cookielifetime.md)和[CX Enterprise Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=zh-Hant#ec-cookies)
* 有限的範圍。 Cookie 的範圍必須限於單一網站或應用程式。 [瀏覽器 Cookie](/help/technotes/cookies/cookies.md#third-party-cookie-limitations)
* 匿名。 將 IP 位址的最後一個八位元匿名。 [一般帳戶設定](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
* 隱藏報表中的訪客 ID。  預設情況下，無法在 Adobe Workspace 和 Adobe Reports and Analytics 中看見訪客 ID。  訪客 ID 可在「資料摘要」和 Data Warehouse 中取得。  資料摘要和 Data Warehouse 的存取權可透過 [Admin Console 的存取權限](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=zh-hant)和[資料摘要欄位參考資料](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)加以限制
* 地理位置參數。 和郵遞區號層級比起來，地理位置可能比較不精確。 [郵遞區號選項](/help/implement/vars/page-vars/zip.md)和[一般帳戶設定](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
* 設定「選擇加入」選項。  「選擇加入」服務讓您可以設定訪客通訊協定，以確定使用者在造訪您的網站時，是否可以在他們的裝置或瀏覽器上設定 Cookie。 [「選擇加入」服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hant)
* 防止資料共用。  若要防止與 Adobe Audience Manager 共用資料，請使用[隱私報告](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md)的`opt.dmp`內容變數，以封鎖點擊共用。
* 存取和刪除能力。 利用 Privacy Service 存取和刪除請求。 [Analytics 及 Privacy Service](gdpr.md)

## 資料收集的其他注意事項

適用於以下其他注意事項：

* Adobe Analytics 在美國、英國和新加坡經營資料處理中心，以便為所有客戶提供在區域中收集、處理和儲存資料的靈活性。 在配置 Adob&#x200B;&#x200B;e Analytics 的初始設定時，客戶可以選取他們想要的資料處理中心地點。 客戶的資料最終會儲存在他們為核心 Analytics 產品所選取的區域內。
* 請考慮收集 Analytics 變數中的選擇加入狀態，以便針對分段、虛擬報告套裝或路由傳送到個別端點來區分選擇加入的資料與選擇退出的資料。
* 未經事先同意，不得在網站或應用程式外部進行任何測量，例如，不進行場外活動、電子郵件活動或 iFrame。
* 未經同意，不允許收集變數中的個人資訊。 [根據使用者同意控制CX Enterprise活動](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html?lang=zh-Hant#implementing-opt-in-on-the-page)
* 資料僅用於產生匿名統計資料，而不能與其他資料合併使用。
* 資料不用於交互參照的動作。
* 未收集 GPS 地理位置資料。
* 當徵得一般使用者同意後，可以修改上述設定並放寬限制。

>[!IMPORTANT]
>
>本文件並不是要做為法律或監管建議，也不構成 Adobe 的任何保證或契約承諾。 我們鼓勵客戶針對此主題事務的相關法律和監管義務問題尋求獨立的法律建議。

如需詳細資訊，請參閱 [CNIL Cookie 豁免](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications)網站。
