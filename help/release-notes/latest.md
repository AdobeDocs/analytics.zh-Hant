---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 4168dc9579950cad02725242aa97e07721c66978
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 62%

---

# 目前的 Adobe Analytics 發行說明 (2023 年 5 月)

**上次更新日期**：2023 年 5 月 8 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## Adobe Analytics 中的新功能或更新功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **非生產沙箱的回填** | 在非生產沙箱中建立 Analytics 來源連接器資料流時，非生產沙箱中的回填將限制為 3 個月。生產沙箱將維持 13 個月。 | 不適用 | 2023 年 4 月 26 日 |
| **專案連結共用 (不需登入)** | 您現在可以與無 Adobe Analytics 存取權的人員共用 Analysis Workspace 專案的唯讀連結。這包括與組織外部人員，或組織內未布建Adobe Analytics的人員共用。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link)<p>此功能預設為啟用，系統管理員可以停用此功能。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023年5月3日 | 2023 年 6 月 |
| **更新Analytics控制面板應用程式（行動應用程式）的首頁畫面** | 全新更新的首頁畫面可讓您在一個整合的計分卡清單中檢視所有計分卡。  如果您透過一次登入存取多個組織，組織中的所有計分卡都將可在單一清單中使用。 | 不適用 | 2023 年 5 月 10 日 |
| **排序Analysis Workspace中的元件** | 在Analysis Workspace的左側邊欄或「資料字典」中檢視元件時，現在提供新的「排序」選項。 您可以依建議（最常使用的）、字母或類別（類型）來排序元件。<p>過去，您只能搜尋或篩選元件。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=en)</p> | 不適用 | 2023 年 5 月 10 日 |
| **從自由表格中刪除包含動態維度的列** | 在Analysis Workspace的自由表格中，您現在可以使用x圖示快速刪除包含動態維度的特定列。 執行此動作時，會自動套用「不等於」篩選規則。<p>以前，刪除包含動態維度的列的唯一方式是在「篩選」對話方塊中手動建立規則。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=en)</p> | 不適用 | 2023 年 5 月 10 日 |
| **在面板中新增視覺效果的新按鈕** | Analysis Workspace中每個面板底部現在都有新按鈕，可讓您快速新增視覺效果。 <p>過去，將視覺效果新增至面板的唯一方法是從左側邊欄拖曳視覺效果、複製或複製現有視覺效果，或建立空白麵板。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#add-visualizations-to-a-panel)</p> | 不適用 | 2023年5月17日 |
| **深層連結（行動應用程式）** | 可讓使用者傳送計分卡的連結，以直接將他們導向至應用程式中的計分卡專案。 這可讓您更輕鬆共用專案，並提升技術水準較低的受眾的參與度。 | 待定 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

AN-312098;AN-318309;AN-316675;AN-318173;AN-310359;AN-317613;AN-318836;AN-315744;AN-311772;AN-318719;AN-314074;AN-316651<!--"Verified" status-->;AN-318602;AN-315961;AN-317534;AN-318607;AN-316498;AN-316648;AN-318244;AN-317747;AN-318432;AN-318231;AN-317590;AN-318415;AN-318154;AN-316647;N-314417;AN-317614;AN-317725;AN-318114;AN-317876;AN-318052;AN-317966;AN-316477;AN-318036;AN-317931;AN-318045;AN-316246;AN-317281;AN-317879;AN-308077;AN-317708;AN-316115;AN-315963

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **注意：Adobe Analytics資料摘要和倫敦資料中心Data Warehouse輸出使用的新IP** | 2023 年 4 月 27 日 | 若是倫敦資料中心的客戶有資料摘要請求和/或Data Warehouse報表傳送至FTP/SFTP服務，您應將下列IP位址範圍新增至防火牆設定，以允許存取： <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |
| **裝置查詢流程現在使用協力廠商進行所有裝置查詢** | 2023 年 3 月 3 日 | 2023 年 3 月 2 日，我們推出了用戶端提示支援，更新了裝置查詢流程以使用協力廠商進行所有裝置查詢。先前，協力廠商只用於進行行動裝置查詢。而在此次推出的內容中，部分桌面作業系統誤標記了「Mobile」文字 (例如，「Mobile OS X 10.15.7」而不是「OS X 10.15.7」)。<p>在 Adobe 4 月版中，我們將更正這些名稱。Analytics 和 CJA 報告將追溯更新，因為它們的報告是根據記錄為事件資料的 ID 來查詢作業系統名稱。一旦 ID 對應的查詢值更新，所有的報告都會修正，包括歷史資料。對於[!UICONTROL 資料摘要]客戶，如果您在報告時使用類似的查詢程序，則變更會具有追溯力。但是，如果您將作業系統值儲存在事件資料中，則只會更新未來的報告。如需詳細資料，請參閱[作業系統](/help/components/dimensions/operating-systems.md)。 |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **日本功能型手機追蹤服務終止** | 2023 年 3 月 21 日 | 僅適用於日本客戶：日本功能型手機追蹤服務 (mod_ktrack) 將於 **2023 年 5 月下旬**&#x200B;終止。 對於所造成的不便，我們深表歉意，但請您卸載或停用安裝在 Apache 伺服器上的模組。請參閱[本文件](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf)的第 27 和 28 頁深入了解。 |
| **[!DNL Reports & Analytics]** EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。<p>在 2023 年 12 月 31 日，我們將終止許多關聯的 Reports and Analytics 功能，包括但不限於：排程報表、資料擷取和 DL 報表。2023 年 12 月 31 日之後，將不再傳送任何排程報表。在&#x200B;**2023 年 4 月**，任何排程在 2023 年 12 月 31 日之後到期的報表將自動更新並恢復到 2023 年 12 月 31 日到期。此外，您不能再排程 2023 年 12 月 31 日之後的未來報表。 |
| **[!UICONTROL 人員]量度生命週期結束** | 2023 年 3 月 9 日 | 隨著 [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html) 淘汰不用，Device Co-op 相關的人員量度已不再相關。2023 年 5 月 8 日，我們將移除[!UICONTROL 人員]量度。屆時，我們會將其資料重新導向至[!UICONTROL 不重複訪客]量度，以防止專案、區段和計算量度中斷。<p>**請注意**：與[[!UICONTROL 跨裝置分析相連結的人員]量度](/help/components/metrics/people.md)不受本公告影響。 |
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
