---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d00ae976a7e7de2fad7f5c214c2bbf39644c9a08
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 85%

---

# 目前的 Adobe Analytics 發行說明 (2023 年 6 月)

**上次更新日期**：2023 年 7 月 10 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 版本重點 {#highlights}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **設定雲端帳戶存放區位置以擷取分類資料** | 您現在可以管理用於分類集自動化的雲端帳戶儲存位置。<p>[了解更多](/help/components/classifications/importer/configure-import-accounts.md)</p> |  | 2023 年 7 月 10 日 |
| **資料修復篩選增強功能** | 「資料修復」新增了三項篩選改善功能：<ul><li>依一個變數篩選以修改第二個變數。 例如，如果 `eVar2` 包含「@」，然後刪除 `eVar3`.</li><li>篩選數值或非數值</li><li>使用AND套用多個篩選器。 例如，其中 `eVar2="a"` 和 `eVar3="b"`</li></ul>[了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 2023 年 6 月 21 日 | 2023 年 7 月 12 日 |
| **專案連結共用 (不需登入)** | 您現在可以與無 Adobe Analytics 存取權的人員共用 Analysis Workspace 專案的唯讀連結。這包括與組織外的人員或組織內未佈建 Adobe Analytics 的人員共用。[了解更多](../analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)<p>此功能預設為啟用，系統管理員可以停用。[了解更多](../analyze/analysis-workspace/user-preferences.md#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 7 日 |
| **分類集的新功能** | [分類設定](/help/components/classifications/sets/overview.md) 已更新幾項新功能：<ul><li>**合併**：將「分類設定」合併至單一的「整合分類設定」。 整合的分類設定可以像其他分類設定一樣使用，或當作Customer Journey Analytics中的查詢資料設定使用。 [了解更多](../components/classifications/sets/consolidations/manage.md)</li><li>**規則**：根據「分類設定」中的規則自動分類值。 [了解更多](../components/classifications/sets/manage/rules.md)</li><li>**自動匯入**：自動從雲端儲存空間目的地匯入分類資料。 [了解更多](../components/classifications/sets/manage/schema.md)</li></ul> | | 2023 年 6 月 7 日 |
| **新的 AppMeasurement 變數** | 變數 `doubleEncodeLinkParameters` 會配合邊緣案例，在這種情況下，實作會在連結追蹤變數中對多位元組字元進行編碼。大多數實作不需要定義此變數。[了解更多](../implement/vars/config-vars/doubleencodelinkparameters.md) |  | 2023 年 6 月 7 日 |
| **資料摘要匯出的安全目標** | 現在可以將資料摘要傳送到以下雲端儲存空間目標：<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>不再建議使用以前提供的目標 (FTP、SFTP、S3 和 Azure Blob)。[了解更多](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=zh-Hant) | 2023 年 6 月 12 日 | 2023 年 7 月 15 日 |
| **Workspace 中的機器人報告** | 機器人報告現在可在 Analysis Workspace 中取得。此功能附帶幾個新增項目：<ul><li>新維度：[機器人名稱](/help/components/dimensions/bot-name.md)</li><li>兩個新量度：[機器人頁面檢視次數](/help/components/metrics/bot-page-views.md)和[機器人發生次數](/help/components/metrics/bot-occurrences.md)。</li><li>一個新的計算量度範本：[機器人頁面檢視次數比率](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>新的工作區報告：機器人報告</li></ul>新維度和量度會包含從 2023 年 3 月開始回填的資料。 |  | 2023 年 6 月 7 日 |

{style="table-layout:auto"}

## 其他新功能或更新功能 {#other}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **從自由格式表格中刪除包含動態維度的列** | 在 Analysis Workspace 的自由格式表格中，您現在可以使用 x 圖示快速刪除包含動態維度的特定列。執行時，會自動套用「永遠排除項目」篩選規則。<p>以前，想要刪除包含動態維度的列，唯一的方法是在「篩選器」對話框中手動建立規則。[了解更多](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 不適用 | 2023 年 5 月 17 日 |
| **在面板中新增視覺效果的新按鈕** | 現在，Analysis Workspace 每個面板的底部都有一個新按鈕，可讓您快速新增視覺效果。 <p>以前，將視覺效果新增到面板的唯一方法是從左側邊欄拖放視覺效果、複製現有的視覺效果，或者建立空白面板。[了解更多](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 不適用 | 2023 年 5 月 17 日 |
| **深度連結 (行動應用程式)** | 可讓使用者傳送計分卡連結，這些連結會直接導向應用程式中的計分卡專案。這使得共用專案和提高技術能力較低對象的參與度變得更加容易。[了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | 不適用 | 2023 年 5 月 17 日 |
| **動態下拉式篩選器** | 我們正在引進一種新類型的下拉式篩選器，它會根據面板報告範圍內的資料和其他下拉式篩選器中的值來決定可用值。按住[!UICONTROL 轉移]同時將維度拖入面板投放區中，即可使用動態下拉式篩選器。按住[!UICONTROL 轉移]同時將維度項目的群組拖入面板投放區中，靜態下拉式篩選器則維持不變。[了解更多](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 2023 年 6 月 14 日 |
| **更新的分析學習頁面** | Adobe Analytics 登陸頁面上的「學習」索引標籤現在包含以下增強功能：<ul><li>改進的設計可在單次頁面上顯示更多學習內容和改進的導覽功能</li><li>根據經驗等級 (初學者、中階和進階) 量身打造學習內容的能力</li></ul>[了解更多](/help/analyze/landing.md) | 2023 年 6 月 27 日 | 2023 年 6 月 30 日 |
| **在 Analysis Workspace 中排序元件** | 現在，在 Analysis Workspace 的左側邊欄或資料字典中查看元件時，可以使用新的「排序」選項。您可以按「建議」(最常用)、「字母順序」或「類別」(類型) 來排序元件。<p>以前，您只能搜尋或篩選元件。[了解更多](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | 不適用 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

-311878；-313968；AN-314130；AN-315701；AN-315761；AN-316613；AN-317563；AN-318829；AN-319009；AN-319043；AN-319066；AN-；AN-；AN-319166；AN-319245；AN-319271；AN-319381；AN-319391；AN-319482；AN-319621；AN-319637；AN-319676；AN-320176；AN-320221；AN-320225；AN-320286；AN-320312；AN-320316；AN-320449；AN-320477；AN-320492；AN-320538；AN-320556；AN-320569；AN-320679；AN-320684；AN-320786；AN-320802；AN-320811；AN-320812；AN-320815；AN-321032；AN-321033；AN-321070；AN-321096；AN-321105；AN-321122；AN-321337；

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **37 個月到期的購買 ID 和事件 ID (事件序列化)** | 2023 年 5 月 25 日 | 即將推出的 Analytics Hit 處理引擎版本，目標是在 **2023 年 6 月下旬或 2023 年 7 月上旬**&#x200B;將開始強制執行 37 個月到期的購買 ID 和事件 ID (事件序列化)。目前，購買 ID 和事件 ID 在 Adob&#x200B;&#x200B;e Analytics 中為永不過期。看到/使用購買 ID 或事件 ID 後，則未來無論何時若有任何點擊，都會使該購買或事件標記為重複。隨著新處理引擎版本的推出：<ul><li>購買 ID 和事件 ID 會一律在 37 個月後到期。</li><li>如果從看到購買 ID 或事件 ID 以來已經有 37 個月，則不再將其視為重複購買或事件。</li><li> 如果您「重複使用」購買 ID 或事件 ID 已經超過 37 個月，則它們即不再被視為重複。</li></ul> |
| **移轉至Adobe I/OOAuth伺服器對伺服器認證** | 2023 年 5 月 11 日 | 使用Adobe I/OJWT憑證的Adobe Analytics API和Livestream客戶必須移轉至Adobe I/OOAuth伺服器對伺服器憑證，遷移方式為 **2025年1月1日**. 如需更多詳細資料和時間表，請參閱下表中的生命週期結束通知。 |
| **倫敦資料中心的 Adobe Analytics 資料摘要和 Data Warehouse 輸出所使用的新 IP** | 2023 年 4 月 27 日 | 倫敦資料中心的客戶若有傳遞到 FTP/SFTP 服務的資料摘要要求和/或 Data Warehouse 報告，這即與其相關。為了允許存取，應將以下 IP 位址新增到您的防火牆設定中： <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉至Adobe I/OOAuth伺服器對伺服器認證** | 2023 年 5 月 11 日 | 使用Adobe I/OJWT憑證的Adobe Analytics API和Livestream客戶必須移轉至Adobe I/OOAuth伺服器對伺服器憑證，遷移方式為 **2025年1月1日**. Adobe I/O自2024年5月1日起不允許建立新的JWT認證。 使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用OAuth的新舊應用程式實作指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。<p>在 2023 年 12 月 31 日，我們將終止許多關聯的 Reports and Analytics 功能，包括但不限於：排程報表、資料擷取和 DL 報表。2023 年 12 月 31 日之後，將不再傳送任何排程報表。在&#x200B;**2023 年 4 月**，任何排程在 2023 年 12 月 31 日之後到期的報表將自動更新並恢復到 2023 年 12 月 31 日到期。此外，您不能再排程 2023 年 12 月 31 日之後的未來報表。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為 Reports &amp; Analytics EOL 的一部分，[!UICONTROL 發佈清單]預定在 **2023 年 12 月**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有[!UICONTROL 發佈清單]，來傳送或排程 [!UICONTROL Analysis Workspace] 專案。 |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hant)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.23.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。
