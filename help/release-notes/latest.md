---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 49c4acb38a96b5fd6a8cd25258628adc9a68074c
workflow-type: tm+mt
source-wordcount: '1426'
ht-degree: 53%

---

# 目前的 Adobe Analytics 發行說明 (2023 年 6 月)

**上次更新日期**：2023 年 6 月 1 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 版本重點 {#highlights}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **專案連結共用 (不需登入)** | 您現在可以與無 Adobe Analytics 存取權的人員共用 Analysis Workspace 專案的唯讀連結。這包括與組織外的人員或組織內未佈建 Adobe Analytics 的人員共用。[了解更多](../analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)<p>此功能預設為啟用，系統管理員可以停用。[了解更多](../analyze/analysis-workspace/user-preferences.md#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 7 日 |
| **分類集的新功能** | [分類設定](/help/components/classifications/sets/overview.md) 已更新幾項新功能：<ul><li>**合併**：將「分類設定」合併至單一的「整合分類設定」。 整合的分類設定可以像其他分類設定一樣使用，或當作CJA中的查詢資料設定使用。 [了解更多](../components/classifications/sets/consolidations/manage.md)</li><li>**規則**：根據「分類設定」中的規則自動分類值。 [了解更多](../components/classifications/sets/manage/rules.md)</li><li>**自動匯入**：自動從雲端儲存空間目的地匯入分類資料。 [了解更多](../components/classifications/sets/manage/schema.md)</li></ul> | | 2023 年 6 月 7 日 |
| **新增AppMeasurement變數** | 變數 `doubleEncodeLinkParameters` 因應實施在連結追蹤變數中編碼多位元組字元的邊緣案例。 大部分實施不需要定義此變數。 [了解更多](../implement/vars/config-vars/doubleencodelinkparameters.md) |  | 2023 年 6 月 7 日 |
| **資料摘要匯出的安全目的地** | 資料摘要現在可以傳送至下列雲端儲存目的地：<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>不再建議使用先前可用的目的地（FTP、SFTP、S3和Azure Blob）。 [了解更多](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=zh-Hant) |  | 2023 年 6 月 12 日 |
| **工作區中的機器人報告** | 機器人報告現在可在Analysis Workspace中使用。 此功能隨附幾個新增功能：<ul><li>新維度： [機器人名稱](/help/components/dimensions/bot-name.md)</li><li>兩個新量度： [機器人頁面檢視](/help/components/metrics/bot-page-views.md) 和 [機器人發生次數](/help/components/metrics/bot-occurrences.md).</li><li>新的計算量度範本： [機器人頁面檢視比率](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>新的工作區報表：機器人報表</li></ul>新維度和量度包含從2023年3月開始回填的資料。 |  | 7,2023 年 6 月 |

{style="table-layout:auto"}

## 其他新功能或更新功能 {#other}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **從自由格式表格中刪除包含動態維度的列** | 在 Analysis Workspace 的自由格式表格中，您現在可以使用 x 圖示快速刪除包含動態維度的特定列。這麼做時，會自動套用「一律排除專案」篩選規則。<p>以前，想要刪除包含動態維度的列，唯一的方法是在「篩選器」對話框中手動建立規則。[了解更多](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 不適用 | 2023 年 5 月 17 日 |
| **在面板中新增視覺效果的新按鈕** | 現在，Analysis Workspace 每個面板的底部都有一個新按鈕，可讓您快速新增視覺效果。 <p>以前，將視覺效果新增到面板的唯一方法是從左側邊欄拖放視覺效果、複製現有的視覺效果，或者建立空白面板。[了解更多](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 不適用 | 2023 年 5 月 17 日 |
| **深度連結 (行動應用程式)** | 可讓使用者傳送計分卡連結，這些連結會直接導向應用程式中的計分卡專案。這使得共享專案和提高技術水平較低的對象參與度變得更加容易。[了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | 不適用 | 2023 年 5 月 17 日 |
| **動態下拉式篩選器** | 我們正在引入一種新型別的下拉式篩選器，它會根據面板報告範圍內的資料和其他下拉式篩選器中的值來決定可用的值。 您可以透過將維度拖曳至面板空投區，同時按住I鍵，使用動態下拉篩選器 [!UICONTROL Shift]. 靜態下拉式篩選器保持不變，方法是將一組維度專案拖曳至面板空投區，同時按住 [!UICONTROL Shift]. [了解更多](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 2023 年 6 月 14 日 |
| **已更新Analytics學習頁面** | Adobe Analytics登陸頁面上的「學習」標籤現在包含下列增強功能：<ul><li>改良設計，可透過改良的導覽在單一頁面上顯示更多學習內容</li><li>能夠依體驗層級（初級、中級和進階）個人化學習內容</li></ul>[了解更多](/help/analyze/landing.md) |  | 30,2023 年 6 月 |
| **在 Analysis Workspace 中排序元件** | 現在，在 Analysis Workspace 的左側邊欄或資料字典中查看元件時，可以使用新的「排序」選項。您可以按「建議」(最常用)、「字母順序」或「類別」(類型) 來排序元件。<p>以前，您只能搜尋或篩選元件。[了解更多](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | 不適用 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

-311878；-313968；AN-314130；AN-315701；AN-315761；AN-316613；AN-317563；AN-318829；AN-319009；AN-319043；AN-319066；AN-；AN-；AN-319166；AN-319245；AN-319271；AN-319381；AN-319391；AN-319482；AN-319621；AN-319637；AN-319676；AN-320176；AN-320221；AN-320225；AN-320286；AN-320312；AN-320316；AN-320449；AN-320477；AN-320492；AN-320538；AN-320556；AN-320569；AN-320679；AN-320684；AN-320786；AN-320802；AN-320811；AN-320812；AN-320815；AN-321032；AN-321033；AN-321070；AN-321096；AN-321105；AN-321122；AN-321337；

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **購買ID和事件ID （事件序列化）37個月到期** | 25,2023 年 5 月 | 即將發行的Analytics點選處理引擎將在中鎖定發行 **2023年6月下旬或2023年7月初**，將開始強制執行「購買ID」和「事件ID」 （事件序列化）的有效期37個月。 目前，購買ID和事件ID在Adobe Analytics中永不過期。 一旦「購買ID」或「事件ID」被看見/使用，無論何時該購買或事件都會標示為重複，任何未來的點選皆然。 透過新的處理引擎版本：<ul><li>購買ID和事件ID一律會在37個月後過期。</li><li>如果自顯示購買ID或事件ID以來已過37個月，則不再視為重複購買或事件。</li><li> 如果您在37個月之前「重複使用」購買ID或事件ID，則不再視為重複專案。</li></ul> |
| **移轉至AdobeIO OAuth伺服器對伺服器認證** | 2023 年 5 月 11 日 | 使用AdobeIO JWT憑證的Adobe Analytics API和Livestream客戶必須透過以下方式移轉至AdobeIO OAuth伺服器對伺服器憑證： **2025年1月1日**. 如需詳細資訊和時間表，請參閱下表中的生命週期結束通知。 |
| **倫敦資料中心Adobe Analytics資料摘要和Data Warehouse輸出使用的新IP** | 2023 年 4 月 27 日 | 這關係到倫敦資料中心的客戶，這些客戶擁有傳送至FTP/SFTP服務的資料摘要請求和/或Data Warehouse報表。 下列IP位址範圍應新增至您的防火牆設定，以允許存取： <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉至AdobeIO OAuth伺服器對伺服器認證** | 2023 年 5 月 11 日 | 使用AdobeIO JWT憑證的Adobe Analytics API和Livestream客戶必須透過以下方式移轉至AdobeIO OAuth伺服器對伺服器憑證： **2025年1月1日**. 自2024年5月1日起，AdobeIO不允許建立新的JWT憑證。 使用JWT的客戶必須建立新的OAuth伺服器對伺服器認證，或將其現有的JWT認證移轉至OAuth伺服器對伺服器認證。 客戶也必須更新其使用者端應用程式，以使用新的OAuth伺服器對伺服器認證。 <ul><li>[從服務帳戶(JWT)憑證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的OAuth伺服器對伺服器認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
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
