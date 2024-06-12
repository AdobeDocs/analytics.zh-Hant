---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6349edc65b953ce7f41d5a5990c8afd6efa20d8d
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 57%

---

# 最新 Adobe Analytics 版本注意事項 (2024 年 6 月)

**上次更新**：2024年6月12日

這些發行說明涵蓋2024年6月12日到7月的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **自由表格的下拉式選單中提供多個篩選器時，請選取這些篩選器** | 當多個篩選器以下拉式選單形式新增至自由表格時，自由表格的使用者現在可以一次選取多個篩選器。 自由表格會經過篩選，加入任何選取的篩選器。 過去，使用者只能在篩選器下拉式選單中一次選取一個篩選器。<p>（請遵循檔案連結。） |  | 2024年6月19日 |
| **工作區專案的目錄** | 專案現在有新的目錄可用。 目錄提供的連結可讓使用者快速跳至專案內的面板和視覺效果。 目錄可為個別專案或特定使用者的所有專案啟用。<p>（請遵循檔案連結。） |  | 2024年6月19日 |
| **在自由表格中建立維度專案的超連結** | 您可以為一或多個維度專案建立超連結，以便在Analysis Workspace的自由格式表格內點選這些專案。 <p>您可以為具有URL值的維度專案建立超連結，或為具有非URL值的維度專案建立自訂URL。</p><p>您可以使用變數，為多個維度專案建立動態自訂URL。 變數可參考維度專案的值，也可以參考劃分維度。</p><p>（請遵循檔案連結。）<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | 2024年6月19日 |
| **用於控制帳戶和位置 (用來匯出和匯入) 的管理員設定** | 新 [位置管理員中的「管理員設定」索引標籤](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only) 可讓管理員控制使用者是否可以建立和編輯帳戶與位置。 這些設定適用於使用者 [設定雲端匯入和匯出帳戶](/help/components/locations/configure-import-accounts.md) 和 [設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md). <p>管理員也可以限制使用者能夠建立和使用的帳戶類型 (如 Google Cloud Platform、Azure RBAC、Amazon S3 等)。</p><p>先前任何使用者都可以建立、編輯和使用所有類型帳戶的帳戶和位置。</p> | 2024 年 6 月 12 日 | 2024 年 6 月 30 日 |
| **共用帳戶和位置 (用於匯出和匯入)** | 使用者現在可以將其建立的帳戶和位置提供給組織中的所有使用者。只有帳戶和位置擁有者以及系統管理員才能編輯和刪除帳戶與位置。<p>先前，帳戶和位置只能由建立它們的使用者使用。</p><p>當使用者[設定雲端匯入和匯出帳戶](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/locations/configure-import-accounts)和[設定雲端匯入和匯出位置](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/locations/configure-import-locations)時，將可使用這些設定。 </p> | 2024 年 6 月 12 日 | 2024 年 6 月 30 日 |
| **Activity Map 可使用更少 Web SDK 伺服器呼叫** | 目前，Activity Map 連結事件被視為是其本身事件並會產生額外費用。此增強功能會產生一些連結事件，並將這些事件封裝至下一個點擊中，類似於 AppMeasurement 處理事件的方式。 <p>(更新的後續文件連結)</p> | 公開 Beta 版將於 2024 年 6 月 19 日開始 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正下列分類問題：AN-347682、AN-348396、AN-348625、AN-348668、AN-348926、AN-348936、AN-349040、AN-349191、AN-349195、AN-349443、AN-349697、AN-349758、AN-349862、AN-350051、AN-350054、AN-350208、AN-350497、AN-350525、AN-351067、AN-、AN-
* 已修正下列Data Warehouse問題：AN-346862、AN-349409、AN-349926、AN-350629、AN-350996
* 修正下列資料摘要問題：AN-346727、AN-348282、AN-348334、AN-348725、AN-348726、AN-348823、AN-349081、AN-349207、AN-349307、AN-349539、AN-349710、AN-349729、AN-349742、AN-349878、AN-349943、AN-350527；
* 修正以下資料來源問題：AN-350038
* 已修正下列Analysis Workspace問題：AN-342953、AN-346346、AN-349590、AN-349717、AN-350057、AN-350697、AN-350904
* 已修正下列Report Builder問題：AN-348903；AN-350691
* 修正以下 A4T 問題：AN-347690；AN-350853

### Analytics 其他修正

AN-346470、AN-346850、AN-347227、AN-348145、AN-348564、AN-349001、AN-349008、AN-349211、AN-349719、AN-350523；

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **13 個月的儲存有效期`cust_visids`** | 2024 年 5 月 22 日 | 即將發行的 Analytics Hit 處理引擎 (**預計於 2024 年 7 月發行**) 將開始強制執行 13 個月的 `cust_visids` 儲存有效期。如果報告套裝已啟用「啟用訪客聯繫」，則此設定用於尋找 `cust_visid` 是否有點擊時無 `cust_visid` 的 `visid_high/visid_low value`。目前，`visid_high/visid_low` 的 `cust_visid` 對應不會過期。在此版本中，如果自點擊時 `visid_high/visid_low` 有 `cust_visid` 以來已過去 13 個月或更長時間，對應會過期。 |
| **ISO 區域更新** | 2024 年 5 月 10 日 | Adobe 將於 2022 年 6 月 10 日執行 2022 ISO 區域更新。 預計此版本後將會有較小的地區資訊 (區域) 更新。 |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.26.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2024 年舊版發行說明](/help/release-notes/2024.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。
