---
title: Adobe Analytics 技術文件更新
description: Adobe Analytics 文件集的重大更新。
short-title: Analytics documentation updates
feature: Release Notes
exl-id: fe8e3c4c-6782-46f7-8e28-4f8f54807788
mini-toc-levels: 3
source-git-commit: a0b2fba6696b7caec510be30909cfbb4b5618521
workflow-type: ht
source-wordcount: '6443'
ht-degree: 100%

---

# Adobe Analytics 技術文件更新

Adobe Analytics 文件集自 2019 年 1 月起的內容更新。

* 如需 [!UICONTROL Customer Journey Analytics] 的相關資訊，請前往[此處](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html)。
* 如需有關串流媒體收集的資訊，請參閱[在 Analytics 中測量音訊和影片](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html)。

## 主要文件更新的詳細資訊

### 2025 {#year2025}

| 功能 | 說明 |
| --- | --- |
| **2025 年 7 月** | |
| 偵錯工具 | 有關如何在 Analysis Workspace 中啟用、使用和停用專案偵錯工具的新文章。 |
| 審閱和更新 | 審閱和更新 Analysis Workspace 文件。在適當的情況下，此文件現在與 Analysis Workspace 的 Customer Journey Analytics 文件同步。 |
| **2025 年 6 月** | |
| 新的快速鍵動作 | 現在，您可以使用 Analysis Workspace 新的鍵盤快速鍵，在專案中上下[移動 Workspace 面板](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md#move-panel-actions)。 |
| **2025 年 3 月** |  |
| Analytics 庫存 | [Analytics 庫存](https://experienceleague.adobe.com/zh-hant/docs/analytics/admin/admin-tools/analytics-inventory)提供您的 Adobe Analytics 環境全面概觀，包括專案和元件的數量、報告套裝、使用者等資訊。 |
| Customer Journey Analytics 升級指南 | 讓您產生從 Adobe Analytics 升級到 Customer Journey Analytics 的[逐步指南](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations?lang=en#recommended-upgrade-steps-for-most-organizations)。 |
| 釐清 Data Warehouse 匯出中的日期格式 | Data Warehouse 匯出中以時間為基礎的維度值採用非標準日期格式。新增資訊，說明如何解讀 Data Warehouse 匯出中的日期值。 <p>請參閱 [Data Warehouse元件支援](/help/export/data-warehouse/component-support.md)中的[以不同方式支援的維度 (非標準日期格式)](/help/export/data-warehouse/component-support.md#dimensions-supported-in-a-different-way-non-standard-date-formatting)。</p> |
| 更新有關 IP 排除項目的資訊 | 新增資訊，說明 [IP 排除項目](/help/admin/admin/exclude-ip.md)最多可能需要 5 分鐘才能生效，以及變更僅適用於新的相符項目 (在設定排除項目之前擷取的資料不受影響)。 <p>也更新內容版面以改善可讀性。</p> |
| **2025 年 2 月** |  |
| 暫停和重新啟用資料摘要的相關更新資訊 | 當[暫停及重新啟用資料摘要](/help/export/analytics-data-feed/df-manage-feeds.md#activate-a-data-feed)時，已釐清即時摘要的行為。在摘要暫停到重新啟用期間不會進行資料處理。 |
| 調整交易 ID 保留期 | 90 天的交易 ID 保留期已延長至 25 個月交易 ID 變數可唯一識別交易，因此點擊可繫結至透過資料來源上傳的資料。在[此處](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/vars/page-vars/transactionid?lang=en)和[此處](https://experienceleague.adobe.com/zh-hant/docs/analytics/import/data-sources/transactionid?lang=en)了解更多資訊。 |
| 直播 API：用戶端實作 | 使用[直播用戶端實作](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/)以使用直播資料。 |
| 分類 API 更新內容 | 您現在可以[從伺服器移除個別的分類欄位或金鑰](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/)。這是使用 DELETE 方法刪除整個分類資料集的替代方法。 |
| **2025 年 1 月** |  |
| 資料摘要 API 參考文件 | [資料摘要 API 的參考文件](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs)現已可供使用。 |
| 全新 Report Builder 排程功能的全新文檔 | [排程功能](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/report-builder/schedule-reportbuilder)不僅能讓您安排新的 Report Builder 活頁簿。此外在轉換舊版活頁簿時，也能讓您獲取舊版已排程任務的中繼資料。 |
| Analysis Workspace 中報告 (也稱為範本) 的改進 | 報告 (也稱為[範本](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/templates/use-templates?lang=en)) 現在提供了各種改善功能： |


### 2024 {#year2024}

| 功能 | 說明 |
| --- | --- |
| **2024 年 10 月** |  |
| 有關 Analysis Workspace Performance 請求因素的新資訊 | [Analysis Workspace 效能最佳化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)文章中的新[請求因素](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md#request-factors)部分介紹了如何處理請求以及影響處理時間的各種因素。 |
| 新的 Report Builder | Mac、Windows 和 Web 瀏覽器支援的簡化 Report Builder 增益集的[新文件](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/report-builder/rb-overview)。 |
| **2024 年 8 月** | |
| 警報管理器 | 簡化了有關 [警報管理器](/help/components/c-alerts/alert-manager.md) 的文件。清晰度和準確性的更新。 |
| **2024 年 7 月** | |
| 成功事件 | 簡化了有關[成功事件](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)的文件。清晰度和準確性的更新。 |
| 管理位置時，必須至少選取一個帳戶類型 | 釐清了管理員[限制用於匯出和匯入的帳戶類型](/help/components/locations/locations-manager.md#limit-the-account-types-that-are-available-to-users)時，必須至少選取一個帳戶類型。 |
| 已新增快速計算量度的相關資訊。 | 已更新[量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md)中的資訊，以釐清這兩者之間的差異：[在計算量度產生器中建立的計算量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects)，[在單一專案中作為快速計算量度建立的計算量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)。也新增更多有關如何建立快速計算量度的詳細資料。<p>在計算量度產生器中建立的計算量度可在元件清單中使用，並可套用到整個組織的專案，而作為快速計算量度建立的計算量度只能在建立它們的專案中使用。</p><p>也更新[建立量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)中的資訊以做出類似的釐清。</p> |
| 將 threads.net 新增至「推薦者類型」維度 | 將 threads.net 新增至[「推薦者類型」維度](/help/components/dimensions/referrer-type.md)中使用的社交網路清單。 |
| 已更新管理資料摘要的文件 | 已更新[管理資料摘要](/help/export/analytics-data-feed/df-manage-feeds.md)中的資訊以改善明確度。 <p>更新包括：</p><ul><li>為各種任務建立單獨章節，使資訊更易於瀏覽和使用。</li><li>已新增有關重新啟動之即時摘要行為變更的資訊。這些變更目前為「有限可用性」的狀態，尚未提供給所有客戶使用。</li><li>已新增表示資料摘要必須為「使用中」狀態才能刪除。</li> |
| 已更新常見錯誤訊息 | 對[常見錯誤訊息](/help/analyze/analysis-workspace/workspace-faq/error-messages.md)進行了小幅更新。 |
| **2024 年 6 月** | |
| 已更新提及串流媒體功能的產品名稱 | 提及用來收集串流媒體資料並將其顯示在 Analysis Workspace 的串流媒體功能集時，出現「媒體分析」和「串流媒體」之處已替換為「串流媒體收集附加元件」和「串流媒體收集」等名稱。 <p>這些更新可在 Adobe Analytics 文件以及[串流媒體收集文件](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-overview)中找到。</p> |
| 已改善的警報文件 | 更新並改善有關警報的文件。這些更新包括有關[建立警報](/help/components/c-alerts/alert-builder.md)、[管理警報](/help/components/c-alerts/alert-manager.md)的資訊，和[概觀資訊](/help/components/c-alerts/intellligent-alerts.md)。 |
| 已棄用 `cookieDomainPeriods` | 現在，AppMeasurement 會自動偵測要設定 Cookie 的正確網域，因此已棄用 [`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md) 變數。 |
| 停用 Data Connectors 文件 | 將 Data Connectors 生命週期終止頁面移至[停產產品](https://experienceleague.adobe.com/zh-hant/docs/discontinued/using/data-connectors)。 |
| **2024 年 5 月** | |
| 在資料摘要和 Data Warehouse 中透過 Google Cloud Platform 使用組織原則限制時的必要資訊 | 將 Adobe 擁有的 Google Cloud Platform 組織 ID 新增至[資料摘要](/help/export/analytics-data-feed/create-feed.md)和 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) 文件中。 <p>只有當組織在 Google Cloud Platform 中使用[組織原則限制](https://cloud.google.com/storage/docs/org-policy-constraints)時才需要此資訊。</p> |
| 有關將元件新增至專案的文件 | 新增了有關如何[將各種類型的元件新增至 Analysis Workspace 中的專案](/help/analyze/analysis-workspace/components/use-components-in-workspace.md)的一般資訊。 |
| 更新了 Advertising Analytics 文件 | 根據 [Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-workflow.md) 使用者介面的更新內容更新了文件。 |
| 將 XDM 物件變數明確地對應到內容資料變數 | 記錄了[使用 XDM 物件變數對應來明確設定內容資料變數](/help/implement/aep-edge/xdm-var-mapping.md#explicit-mapping)的功能。 |
| 關於從 Adobe Analytics 升級到 Customer Journey Analytics 的新文件 | 對於從 Adobe Analytics 升級到 Customer Journey Analytics 的組織來說，根據組織目前的 Adobe Analytics 實作和長期目標，有多種升級選項和許多需要牢記的考量事項。<p>現在提供新的文件資源來協助您更加瞭解：</p><ul><li>存在的各種升級路徑</li><li>根據組織目前的 Adobe Analytics 實作可以使用哪些升級路徑</li><li>每種升級路徑的優點和缺點</li><li>每個升級路徑的逐步操作指導</li><li>處理歷史資料的考量事項</li><li>及更多內容！</li></ul><p>[開始升級到 Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted)。</p> |
| 關於自訂日期範圍的更新文件 | 與[建立自訂日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md)相關的最新螢幕擷圖與程序，以利符合目前的產品特徵與設計。 |
| **2024 年 4 月** | |
| 與分類集中的「所有者」相關的文件已移除 | 「所有者」篩選器和欄已從[分類集管理員](/help/components/classifications/sets/manage/set-manager.md)中移除，「所有者」欄位已從[分類集設定](/help/components/classifications/sets/manage/settings.md)中移除。 <p>文件已更新以刪除此篩選器、欄和欄位。</p> |
| 刪除了文件中有關設定雲端匯入和匯出位置的可摺疊區段 | 刪除了[設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md)中的可摺疊區段，可獲得說明雲端帳戶類型的資訊。 |
| **2024 年 3 月** | |
| AppMeasurement 更新 | [發行說明](/help/implement/appmeasurement-updates.md) - AppMeasurement 更新 v2.26.0。<br/>包括對 [`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md) 設定變數文件的參考和更新。 |
| 關於「使用於」欄的使用情況資訊，僅從 2023 年 9 月開始提供。 | 澄清[專案登陸頁面](/help/analyze/landing.md)上的「**使用於**」欄的使用情況資訊只能追溯到 2023 年 9 月。 |
| **2024 年 2 月** | |
| 有關管理 Data Warehouse 請求的資訊更新 | 澄清依預設使用者只能查看他們在[管理 Data Warehouse 請求](/help/export/data-warehouse/data-warehouse-requests-manage.md)時所建立的請求。 |
| 專案共用文件更新 | 新增有關如何[檢視共用專案](/help/analyze/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you)的資訊。<p>同時也簡化有關[共用個別或多個專案](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role)的資訊。</p> |
| 新增權限要求，可將檔案上傳到 Data Warehouse 和資料摘要中的 Azure SAS 和 Azure RBAC | 新增當[設定 Data Warehouse 目標](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)以及[當設定資料摘要目標](/help/export/analytics-data-feed/create-feed.md)時，將檔案上傳至 Azure SAS 和 Azure RBAC 的明確權限要求。 |
| 新增權限要求，可將檔案上傳到 Data Warehouse 和資料摘要中的 Amazon S3 和 GCP 貯體 | 新增當[設定 Data Warehouse 目標](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)以及[當設定資料摘要目標時](/help/export/analytics-data-feed/create-feed.md)將檔案上傳到 Amazon S3 和 Google Cloud Platform 貯體的 Cloud Platform 的明確權限要求。 |
| **2024 年 1 月** | |
| 元件移轉適用於個別 IMS 組織 | 澄清[元件移轉](/help/admin/admin/component-migration/component-migration.md)不支援跨 IMS 組織的移轉。 |
| 澄清某些資訊僅供管理員使用 | 新增了一些資訊，說明[計算量度管理器](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)和[區段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md)內所述的「上次使用」和「使用於」欄位僅供系統管理員使用。 |
| 媒體平均分鐘觀眾數文件更新 | 已更新[「媒體平均分鐘觀眾數」面板](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)中的資訊，以改善內容清晰度。<p>改善部份包括：</p> <ul><li>改進資訊編排方式</li><li>新增指示任務型資訊的步驟</li></ul> |

### 2023 {#year2023}

| 功能 | 說明 |
| --- | --- |
| **2023 年 12 月** | |
| 改進機器人規則文件 | 已更新[了解和設定機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)中的資訊，以改善明確度。<p>改善項目包括：</p> <ul><li>更新文章標題，使其更能說明內容</li><li>改進資訊編排方式</li><li>新增指示任務型資訊的步驟</li><li>新增有關上傳機器人規則時 CSV 檔案需求的更多詳細資料</li></ul> |
| 新的「報告」區段 | 增加新的「報告」區段，其中包含有關[使用範本](/help/analyze/analysis-workspace/templates/use-templates.md)和[建立公司範本](/help/analyze/analysis-workspace/templates/create-templates.md)的資訊。 |
| 更新了異常偵測和貢獻分析文件 | 異常偵測和貢獻分析的文件以前位於 Virtual Analyst 區段中。以下是所做的變更： <ul><li>術語 Virtual Analyst 已從文件中刪除。</li><li>「[異常偵測](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)」的區段直接移至 Analysis Workspace 區段下方。</li><li>貢獻分析文件已合併到異常偵測文件中。</li></ul> |
| 「Attribution IQ」變更為「歸因」 | 將整份文件中所有出現的「Attribution IQ」變更為「[歸因](/help/analyze/analysis-workspace/attribution/overview.md)」。 |
| **2023 年 11 月** | |
| Activity Map 啟動/啟用主題的更新 | 新增 [Web SDK](/help/analyze/activity-map/getting-started.md) (手動及透過 Adobe Experience Platform 標記擴充功能) 內容。 |
| **2023 年 10 月** | |
| 報告活動管理員新增了記錄資訊 | 新增了以下資訊：「報告活動管理員」中[報告活動的任何取消和後續限制](/help/admin/admin/reporting-activity-manager/reporting-activity-cancel-requests.md)都會在[記錄](/help/admin/admin/logs.md)中擷取。 |
| Data Warehouse 元件支援更新 | 新增一些 Data Warehouse 可用元件，並移除其他可用元件。這些變更反映在 [Data Warehouse 的元件支援](/help/export/data-warehouse/component-support.md)。 <ul><li>新增對造訪深度維度的支援 (移除不支援維度清單的造訪深度)</li><li>移除對參與率量度的支援 (新增不支援量度清單的參與率量度)</li><li>新增對以下時間型維度的支援：年、季、月、週、日、小時和分鐘 (移除不支援維度清單中這些維度) <p>之前，Data Warehouse 唯有在選取「詳細程度」的情況下，才會在自由表格的第一欄支援這些維度。現在一律支援這些維度。</p><p>但使用這些維度時，日期輸出不是使用標準格式。年份依 1900 年位移，月份從零開始。</li></ul> |
| **2023 年 9 月** | |
| 已更新「媒體播放時間」面板的文章結構 | 已移除名為「媒體播放時間」的資料夾，並將該資料夾的內容合併為一篇文章：[「媒體播放時間」面板](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md)。 <p>此變更會更符合其他面板的文件。</p> |
| 開始使用內容增強功能 | 已新增概觀管理員、分析師、一般使用者和開發人員的關鍵入門任務和資源等資訊。現已提供以下新文章： <ul><li>[快速入門 (依照角色)](/help/analyze/get-started/get-started-by-role.md)</li><li>[了解 Analytics 介面](/help/analyze/get-started/analytics-interface.md)<li>[使用案例](/help/analyze/get-started/use-cases.md)</li></ul> |
| 改善串流媒體收集的報告文件 | 重新整理串流媒體收集指南之「報告」區段中的一些內容，包括將 API 文件合併到其自有區段中，以及調整一些文章的順序。 <p>將媒體工作區範本文章重命名為 [Workspace 媒體報告](https://experienceleague.adobe.com/docs/media-analytics/using/media-reports/media-workspace-templates.html)，以與產品內的名稱保持一致。 </p> |
| **2023 年 8 月** | |
| 資料摘要釐清 | 更新[開始和結束日期的定義](/help/export/analytics-data-feed/create-feed.md)，以釐清在處理歷史資料的資料摘要時，您可以將開始日期設定為收集資料之前的任何日期。 |
| Adobe Experience Platform Edge Network 資料處理 | 已新增內容說明 Adobe Analytics 如何[處理來自 Edge Network 的資料](../implement/aep-edge/overview.md)。 |
| 「媒體播放時間」面板 | 已更新[媒體播放時間面板](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md)的內容以提高可讀性。 |
| 已移動關於管理已排程專案的內容 | 在「Analytics 元件指南」中建立了一篇新文章，名為[已排程專案](/help/components/scheduled-projects-manager.md)。此內容之前位於「Analytics 工具指南」的[已排程的專案](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md)文章中。 |
| 比較實作方法 | 已更新比較不同實作方法的文件。[了解更多](../implement/prepare/comparison.md) |
| 澄清資料摘要的 SFTP 設定不需要 Adobe 客戶服務 | 在[使用 SFTP 將 Adobe 資料傳送到外部 FTP 帳戶](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)中，澄清不需要求助 Adobe 客戶服務即可為資料摘要設定 SFTP。 <p>同時，新增注意事項，表示不再建議使用 SFTP，客戶在設定資料摘要時應使用雲端目的地。</p> |
| 串流媒體收集的文件改善 | 已針對串流媒體收集進行以下文件改善： <ul><li>已更新[一般概觀](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html)避免混淆，並新增與 Customer Journey Analytics 相關的資訊。</li><li>已更新[實作概觀](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html)，明確區分邊緣實作和僅限 Analytics 實作。還新增圖表，說明各種實作方式。</li><li>已新增 [Edge 實作](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/edge-recommended/prerequisites-edge.html)和[僅限 Analytics 實作](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/analytics-only/prerequisites-analytics.html)專用的先決條件。還更新了[一般先決條件](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/prereqs.html)。</li><li>已更新文章[取得 Media SDK、使用標記的擴充功能和 OTT SDK](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/download-sdks.html) 中的圖表，以新增&#x200B;*支援的解決方案*&#x200B;和&#x200B;*實作方法*&#x200B;的新欄。</li><li>已簡化文件中[實作](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html)區域文章的內容和組織。這包括用邊緣實作和僅限 Analytics 實作，對實作加以分類。</li><li>已刪除[追蹤](https://experienceleague.adobe.com/docs/media-analytics/using/tracking/track-core-overview.html)下不需要的額外階層，並在本區段中新增已更改 URL 的重新導向。</li><ul> |
| **2023 年 7 月** | |
| Adobe Experience Platform Edge Network API | 新增可更全面說明何時與如何使用 [Adobe Experience Platform Edge Network API](../implement/aep-edge/api/overview.md) 透過 Adobe Analytics 實作資料收集的文件。例如，在桌面應用程式、IoT 裝置、機上盒中透過 Adobe Analytics 實作資料收集。 |
| 全球公司 ID | 以文件說明針對您登入的 Analytics 公司，[如何找到全球公司 ID](../admin/admin/company/web-services-admin.md)。Analytics 2.0 API 需要此 ID。 |
| 已更新 FTP 大小限制 | 已將預設 [FTP 資料儲存空間限制](/help/export/ftp-and-sftp/ftp-limits.md)變更為 100 GB。 |
| 新的 AppMeasurement 變數 | 變數 `decodeLinkParameters` 會配合邊緣案例，在這種情況下，實作會在連結追蹤變數中對多位元組字元進行編碼。[了解更多](../implement/vars/config-vars/decodelinkparameters.md) |
| 設定雲端帳戶儲存位置以擷取分類資料 | 您現在可以管理用來進行分類集自動化的雲端帳戶儲存位置。[了解更多](/help/components/locations/configure-import-accounts.md) |
| 資料修復篩選器增強功能 | 資料修復新增了三項篩選增強功能。[了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) |
| **2023 年 6 月** | |
| 分類集的新功能 | [分類集](/help/components/classifications/sets/overview.md)有多項新功能更新：<ul><li>**合併**：將多項分類集合併為單一的分類集。合併的分類集可以像其他分類集一樣使用，也可以在 Customer Journey Analytics 中做為查詢資料集。[了解更多](../components/classifications/sets/consolidations/manage.md)</li><li>**規則**：根據分類集中的規則自動對值進行分類。[了解更多](../components/classifications/sets/manage/rules.md)</li><li>**自動匯入**：從雲端儲存空間目的地自動匯入分類資料。[了解更多](../components/classifications/sets/manage/schema.md)</li></ul> |
| 計算量度更新 | 已對和計算量度相關的各種文章進行更新，包括更新螢幕擷取畫面和程序中的步驟。進行這些變更是為了使文件和目前的 Adobe Analytics 功能保持一致。 |
| 資料摘要匯出的安全目標 | 現在可以將資料摘要傳送到以下雲端儲存空間目標：<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>不再建議使用以前提供的目標 (FTP、SFTP、S3 和 Azure Blob)。[了解更多](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html) |
| Workspace 中的機器人報告 | 機器人報告現在可在 Analysis Workspace 中取得。此功能附帶幾個新增項目：<ul><li>新維度：[機器人名稱](/help/components/dimensions/bot-name.md)</li><li>兩個新量度：[機器人頁面檢視次數](/help/components/metrics/bot-page-views.md)和[機器人發生次數](/help/components/metrics/bot-occurrences.md)。</li><li>一個新的計算量度範本：[機器人頁面檢視次數比率](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>新的工作區報告：機器人報告</li></ul>新維度和量度會包含從 2023 年 3 月開始回填的資料。 |
| **2023 年 5 月** | |
| 深度連結 (行動應用程式) 文件 | 可讓使用者傳送計分卡連結，這些連結會直接導向應用程式中的計分卡專案。[了解更多](/help/analyze/mobile-app/create-scorecard.md#shareable-link) |
| Analytics 儀表板應用程式 (行動應用程式) 更新首頁的文件 | 更新的首頁可讓您在一個綜合計分卡清單中檢視所有計分卡。[了解更多](/help/analyze/mobile-app/executive.md#use-dashboards) |
| Spectrum 圖示 | 如情況適合，可將文件中使用者介面的螢幕擷圖以對 [Adobe 的 Spectrum 設計系統](https://spectrum.adobe.com/page/icons/)中同等圖示的參照取代。 |
| 報告活動管理員 | 更新了這個 beta 文件，尤其是有關[檢視個別報告套裝的報告活動](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html#view-reporting-activity-for-individual-report-suites)的章節。 |
| Analysis Workspace 概觀 | 更新 [Analysis Workspace 概觀](/help/analyze/analysis-workspace/home.md)以包含更多一般概觀資訊和相關內容的連結。 |
| 建立專案 | 建立新文章，其中詳細說明如何在 Analysis Workspace [建立專案](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)。 |
| 排序左側邊欄中的元件 | 左側邊欄內新增關於元件清單排序的資訊。請參閱[元件概觀](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)中的「搜尋、篩選和排序元件清單」一節。 |
| 從自由格式表格中刪除包含動態維度的列 | 已新增如何使用 x 圖示快速刪除包含動態維度的特定列的資訊。請參閱[篩選和排序表格](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的「從表格中快速排除特定列」一節。 |
| 在面板中新增視覺效果的按鈕 | 已在 Analysis Workspace 中每個面板底部新增有關新按鈕的資訊，讓您可快速新增視覺效果。請參閱[視覺效果概觀](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)中的「將視覺效果新增到面板」一節。 |
| **2023 年 4 月** | |
| 轉移使用者資產並設定帳戶期限 | 新增有關如何[轉移使用者資產並設定帳戶期限](/help/admin/admin/user-management2/users-assets.md)的資訊。 |
| Adobe Analytics 2.0 API 的 2 個新端點指南 | <ul><li>[Analytics 維度 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)</li><li>[Analytics 量度 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/metrics/)</li></ul> |
| 專案區段 (臨時和快速區段) | 簡化了專案區段的文件，並刪除重複資訊。建立臨時區段的步驟現在已經和下列步驟相結合，用於[建立快速區段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)。 |
| 動態查詢 | 新增更多關於[動態查詢](/help/export/analytics-data-feed/c-df-contents/dynamic-lookups.md)的資訊。以前，只有行動屬性的資訊，這是幾個動態查詢之一。 |
| **2023 年 3 月** | |
| Web SDK 支援 Activity Map | 更新「[實作 Adobe Analytics](/help/implement/home.md)」。 |
| 流量變數 (props) 概觀 | 新增區段和逐步程序以說明和改善文章內容。合併了標題為「啟用流量變數報告」一文中的內容，並移除了該文章。請參閱[流量變數 (props) 概觀](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)。 |
| 內部 URL 篩選器 | 新增區段和逐步程序以說明和改善文章內容。請參閱[內部 URL 篩選器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。 |
| 在行動計分卡中建立資料故事 | [資料故事](/help/analyze/mobile-app/create-scorecard.md#create-data-stories)是圍繞中心主題或量度建置的支援資料點、業務內容和相關量度的集合。 |
| 預設計算量度 | 已新增說明 [Adobe 提供的預設計算量度](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)的內容。 |
| 資料字典 | <p>為資料字典新增了新文件，包括[概觀](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)、[檢視](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md)、[編輯 ](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)，以及[監視](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md)資料字典。</p><p>已更新[新增元件說明](/help/analyze/analysis-workspace/components/add-component-descriptions.md)中的資訊，以說明資料字典功能。</p> |
| 專案連結共用 (不需登入) | <p>已更新現有文件，說明如何與無權存取 Analysis Workspace 的人員共用專案的唯讀連結。</p> <p>已更新使用者文件，包括[共用專案](/help/analyze/analysis-workspace/curate-share/share-projects.md)和[建立可共用連結](/help/analyze/analysis-workspace/curate-share/shareable-links.md)。</p> <p>已將管理員選項新增至[偏好設定](/help/analyze/analysis-workspace/user-preferences.md)。</p> |
| **2023 年 2 月** | |
| 實作 | 已更新有關如何[為網路和行動裝置實作 Adobe Analytics](../implement/home.md) 的內容。 |
| Workspace 行事曆和日期範圍 | 更新內容以說明相對日期範圍、公式計算更新和行事曆 UI 變更。查看[關於相對面板日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)。 |
| Mobile 計分卡 | 新文件部分會說明如何顯示和隱藏比較日期範圍。請參閱 Customer Journey Analytics 中的「[顯示比較日期範圍](/help/analyze/mobile-app/create-scorecard.md)」。 |
| 1.4 API | [Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/) 已徹底重寫，現已發佈在 Adobe Developer 上。 |
| 跨實作類型追蹤 | 已更新使用範例[追蹤不同的實作類型](../implement/use-cases/cross-type-implementation.md)，以符合 Experience Cloud ID 服務。 |
| **2023 年 1 月** | |
| 篩選和排序表格 | 已更新[篩選和排序表格](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的內容 (包括新增過程和說明可用選項)。重新命名本文的「分頁、篩選和排序表格」。 |
| 資料夾 | [檔案夾管理](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)的專用頁面。 |
| 使用者偏好設定 | 「[偏好設定](/help/analyze/analysis-workspace/user-preferences.md)」現在提供許多其他使用者偏好設定。 |
| 專案自動儲存 | 更新內容以加入「[儲存專案](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)」中的自動儲存功能。 |
| 登陸頁面 | 全新[登陸頁面更新](/help/analyze/landing.md) |

### 2022 {#year22}

| 功能 | 說明 |
| --- | --- |
| **2022 年 11 月** | |
| 同意管理變數 | [同意管理選擇加入](/help/components/dimensions/cm-opt-in.md)和[同意管理選擇退出](/help/components/dimensions/cm-opt-out.md)的專屬頁面。 |
| 多貨幣重新整理 | [多貨幣支援](/help/implement/vars/config-vars/currencycode.md)頁面已更新。 |
| **2022 年 10 月** |  |
| Data Workbench | [生命週期結束公告](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) |
| 用戶端提示 | 新的[概觀和常見問題集](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html)。 |
| 關鍵量度摘要 | 新的[關鍵量度摘要](/help/analyze/analysis-workspace/visualizations/key-metric.md)視覺化主題。 |
| 分類集 | 新的使用者[分類集](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html)體驗提供管理分類和規則的單一介面，可提升客戶擁有的分類資料的可見度。 |
| 行動應用程式：自訂詳細資料檢視 | 新的[自訂詳細資料檢視](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html)主題。 |
| VISTA | 說明[VISTA 規則](/help/technotes/vista.md)基本概念的新頁面。 |
| **2022 年 9 月** | |
| 組合圖 | 在[組合圖](/help/analyze/analysis-workspace/visualizations/combo-charts.md)視覺化上的新主題。 |
| 更新外掛程式 | 更新版本的 [getvalonce](/help/implement/vars/plugins/getvalonce.md) 實作外掛程式。 |
| 新的設定變數 | 有關 [collectHighEntropyUserAgentHints](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) 的文件 |
| 高平圴資訊量的用戶端提示 | 有關 Adobe 如何在使用者代理程式之外使用[用戶端提示](/help/technotes/client-hints.md)來確定裝置資訊的新主題。 |
| 處理順序 | 匯總了各種說明頁面以提供有關[處理順序](/help/technotes/processing-order.md)的單一說明主題 |
| **2022 年 8 月** | |
| XDM 中用於 Edge 集合的清單變數支援 | 讓使用 Web SDK 收集資料的客戶能使用 XDM 來指定清單變數內容。[了解更多](../implement/vars/page-vars/list.md#list-variables-using-the-web-sdk) |
| 設定產品字串變數時，為 Edge 集合使用 XDM 中的 SKU 欄位 | 讓使用 Web SDK 收集資料的客戶能使用 SKU 值在產品變數中設定產品欄位。[了解更多](../implement/vars/page-vars/products.md#products-using-the-web-sdk) |
| **2022 年 6 月** |  |
| XDM 中用於 Edge 集合的銷售變數 | 有關 [XDM 中用於 Edge 集合的銷售變數支援](/help/components/dimensions/evar-merchandising.md)的文件 |
| Experience Platform Edge 文件 | 透過 [Web SDK](/help/implement/aep-edge/web-sdk/overview.md)、[Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md) 和 [Edge API](/help/implement/aep-edge/api/overview.md) 發表在 Adobe Analytics 實作上的新文章。 |
| 已更新的流量視覺化文件 | 根據[新的 UI](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) |
| 有關以行動計分卡共用註解的文件 | 您可以[在行動計分卡上顯示在工作區中建立的註解](/help/analyze/analysis-workspace/components/annotations/mobile-annotations.md)。 |
| **2022 年 5 月** | |
| 透過 Edge Network 填入生命週期維度和量度 | 傳送至 Edge Network 的行動生命週期資料現在會出現在 Analytics 報告中。如需瞭解哪些 XDM 欄位對應到現有的行動生命週期報告，請參閱[分析變數對應](/help/implement/aep-edge/xdm-var-mapping.md)。 |
| **2022 年 4 月** | |
| Adobe Analytics 登陸頁面更新 | 更新[工作區/Reports &amp; Analytics 聯合登陸頁面](/help/analyze/landing.md)，可改善可用性並方便瀏覽。 |
| 「[!UICONTROL 頁面摘要]」面板的新主題 | [頁面摘要面板](/help/analyze/analysis-workspace/c-panels/page-summary.md) |
| 「[!UICONTROL 下一個/前一個項目]」面板的新主題 | [下一個/前一個維度項目面板](/help/analyze/analysis-workspace/c-panels/next-previous.md) |
| **2022 年 3 月** | |
| 有關受支援的 HTTPS 加密演算法的新主題 | 為加密安全等級設定為「高度」的客戶提供支援的 HTTPS 加密演算法。 |
| 有關工作區中註解的新文件 | [工作區中的註解](/help/analyze/analysis-workspace/components/annotations/overview.md)讓您能夠有效地將內容相關的資料細微差別和深入解析傳達給您的組織。 |
| Adobe Analytics 登陸頁面更新 | [更新](/help/analyze/landing.md)工作區/Reports &amp; Analytics 聯合登陸頁面，可改善可用性並方便瀏覽。 |
| 「[!UICONTROL 下一個項目]」或「[!UICONTROL 上一個項目]」工作區面板 | 此面板可讓您瀏覽您所選維度項目之後或之前的項目。 |
| 「[!UICONTROL 頁面摘要]」工作區面板 | 此面板可為您選擇的頁面提供深入分析。 |
| 有關暫停較舊排程報告的新主題 | 自 **2022 年 4 月 15 日**&#x200B;起生效，Adobe 打算暫停所有建立日期超過兩年的排程報告。 |
| **2022 年 2 月** | |
| 行動計分卡專案預覽模式 | [預覽模式](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#preview)允許您在儲存並共用計分卡之前預覽體驗。 |
| API 專案端點 | 使用 API 新增、編輯或刪除 Analysis Workspace 專案。[了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) |
| 有關暫停較舊已排程 Report Builder 工作的最新主題 | **自 2022 年 4 月 15 日起**，Adobe 打算[暫停所有建立日期超過兩年的已排程 Report Builder 工作](/help/analyze/legacy-report-builder/r-arb-scheduled-reports.md)。 |

### 2021 {#year2021}

| 功能 | 說明 |
| --- | --- |
| **2021 年 10 月** |  |
| 2021 年 10 月 21 日 | 有關 Analysis Workspace 中[快速區段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html)的新文件。 |
| 2021 年 10 月 21 日 | 有關 Analysis Workspace 中[花費的媒體播放時間](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/media-playback-timespent/media-playback-time-spent.html)面板的新文件。 |
| 2021 年 10 月 7 日 | 有關[行動計分卡視覺效果](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#apply-visualizations)的新文件 |
| **2021 年 8 月** |  |
| 2021 年 8 月 18 日 | 已修改最上層結構，並將其整合成單一[登陸頁面](https://experienceleague.adobe.com/docs/analytics.html) |
| 2021 年 8 月 18 日 | 有關 [A4T 和虛擬報告套裝](/help/components/vrs/vrs-a4t.md)的新主題 |
| 2021 年 8 月 18 日 | 有關[歸因最佳做法](/help/analyze/analysis-workspace/attribution/best-practices.md)的新主題 |
| 2021 年 8 月 5 日 | 有關[計算重複執行個體數](https://experienceleague.adobe.com/docs/analytics/components/metrics/count-repeat-instances.html)的新主題 |
| 2021 年 8 月 5 日 | 已更新有關[範本](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-download-saint-data.html)、[瀏覽器匯入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html)和[瀏覽器匯出](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-export.html)的分類文件，以指示哪些選項不適用於已啟用「新分類架構」的報告套裝。 |
| 2021 年 8 月 2 日 | 已更新多個頁面，以反映 [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html) 的品牌重塑 |
| **2021 年 7 月** |  |
| 2021 年 7 月 23 日 | 有關[銷售 eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html) 的全新深入探討 |
| 2021 年 7 月 15 日 | 已新增有關新 [Adobe Analytics 登陸頁面](/help/analyze/landing.md)的文件 |
| **2021 年 6 月** |  |
| 2021 年 6 月 15 日 | 已更新[行銷管道最佳做法](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html) |
| 2021 年 6 月 3 日 | 已更新文件，以便為[資料摘要實作](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html)和[此處](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html#BucketOwnerFullControl)提供更好的說明。 |
| 2021 年 5 月 25 日 | 已更新有關[報告中 eVar 區分大小寫情況](https://experienceleague.adobe.com/docs/analytics/components/dimensions/evar.html)的文件。 |
| 2021 年 5 月 13 日 | [Data Warehouse API 要求](https://developer.adobe.com/analytics-apis/docs/1.4/guides/reporting/data-warehouse/)的更新。這類要求現在支援「小時」。 |
| **2021 年 3 月** | |
| 2021 年 3 月、4 月 | Adobe Analytics 儀表板[執行指南](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/executive.html)和[組織者指南](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html)的更新 |
| 2021 年 3 月 25 日 | 有關「[!UICONTROL 元件] > [!UICONTROL 使用者偏好設定]」頁面的新文件。這可讓您為使用者管理 [!UICONTROL Analysis Workspace] 設定及其相關元件。「[!UICONTROL 使用者偏好設定]」會套用到所有新的專案和面板。<br>**注意：**&#x200B;以下設定已移至「[!UICONTROL 使用者偏好設定]」頁面：<ul><li>報告設定：千位分隔符號 (現在稱為&#x200B;_數字格式_)</li><li>報告設定：CSV 分隔符號</li><li>Workspace 專案：說明 > 啟用秘訣</li><li>Workspace 專案：空白面板 _使用此面板開始新專案_&#x200B;選項</li></ul> |
| 2021 年 3 月 25 日 | [!UICONTROL 直方圖智慧值區預測]會藉由自動識別資料分配的正確寬度和值區數，協助處理高基數度量的直方圖。對於低基數度量，此視覺化效果的行為模式與先前相同。 |
| 2021 年 3 月 25 日 | [資料修復 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) 更新 (URL、查詢字串、@ 符號等項目的篩選功能) |
| 2021 年 3 月 25 日 | 新的[使用記錄 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/usage-logs.md) 文件 |
| **2021 年 2 月** | |
| 2021 年 2 月 4 日 | 元件選擇：[!UICONTROL 工作區]中的所有拖放區域已新增 [!UICONTROL Quick Insights] 中的下拉/拖放區域元件。這項增強功能可讓您從相容元件的下拉式清單中挑選項目，或繼續將該空間當做拖放區域使用。 |
| **2021 年 1 月** | |
| 2021 年 1 月 14 日 | 已在 Analytics 儀表板文件中新增語言選擇選項。 |
| 2021 年 1 月 14 日 | 已新增有關如何藉由參照公用影像 URL 將影像新增至工作區專案的文件。 |
| 2021 年 1 月 14 日 | 已合併工作區視覺效果的來源和設定管理員：視覺效果的[!UICONTROL 資料來源]管理員 (點) 和設定管理員 (齒輪) 已合併為單一彈出視窗，以便您能輕鬆地從相同位置管理來源和設定。 |

### 2020 {#year2020}

| 功能 | 說明 |
| --- | --- |
| **2020 年 12 月** | |
| 2020 年 12 月 7 日 | 已修改所有相關頁面，以包含或替代 &quot;adobedc.net&quot; 端點。 |
| 2020 年 12 月 8 日 | 工作區中「[建立新專案](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html)」頁面的更新。 |
| **2020 年 11 月** | |
| 2020 年 11 月 24 日 | 工作區中「[面板概觀](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)」頁面的更新。 |
| 2020 年 11 月 24 日 | 新的實作審核文件： <ul><li>[完整實作審核](https://experienceleague.adobe.com/docs/analytics/implementation/review/full-review.html)</li><li>[重點實作審核](https://experienceleague.adobe.com/docs/analytics/implementation/review/focused-review.html)</li></ul> |
| 2020 年 11 月 24 日 | 已更新 Analysis Workspace 的「[視覺效果概觀](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)」頁面。 |
| 2020 年 11 月 12 日 | 有關[繼承的 Adobe Analytics 實作](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/existing-implementation.html)的新頁面。 |
| 2020 年 11 月 2 日 | 已更新有關[用於分類的 FTP](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html) 的文件。 |
| **2020 年 10 月** | |
| 2020 年 10 月 23 日 | 工作區線條視覺效果：[移動平均趨勢線選項](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/line.html)：此設定已新增到[!UICONTROL 線條]視覺效果趨勢線設定。移動平均也稱為滾動平均，它會使用特定數量的資料點 (取決於&#x200B;**[!UICONTROL 期間]**&#x200B;選擇)、求取其平均值，並將平均值當做線條中的某個點。 |
| 2020 年 10 月 23 日 | 工作區的[效能說明頁面](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html)會顯示影響專案效能的不同因素，以及最佳化秘訣的連結。 |
| 2020 年 10 月 23 日 | 已在 Adobe Analytics 儀表板文件中新增增強功能。現在，在工作區中建立行動計分卡時，計分卡的樣式會與應用程式相符。 |
| **2020 年 9 月** | |
| 2020 年 9 月 17 日 | [下載單一維度的 50K 個項目](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html#download-items)：您現在可以在自由表格中下載單一維度的 50,000 個項目，並套用區段和篩選條件。如此一來，您就能存取 Analysis Workspace 以外超過 400 列的資料。 |
| 2020 年 9 月 17 日 | [線條視覺效果的增強功能](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/line.html)： <ul><li>您可以顯示或隱藏任何[!UICONTROL 線條]視覺效果的 X 軸與 Y 軸。當 [!UICONTROL 線條] 視覺化效果較為精簡時，這項功能可說相當實用。</li><li>您可以在任何線條視覺化效果上覆蓋最小值和最大值標籤，以迅速突顯量度的高低值。</li><li>您可以在任何線條視覺化效果上覆蓋不同的迴歸趨勢線，以便輕鬆查看資料趨勢。選項包括[!UICONTROL 線性]、[!UICONTROL 對數]、[!UICONTROL 指數]、[!UICONTROL 冪]和[!UICONTROL 二次方程式]。</li></ul> |
| 2020 年 9 月 17 日 | 已在工作區中新增日期範圍：我們已新增 5 個日期範圍，好讓您可以選擇以下日期範圍，並排除不完整的當天資料：過去 7 天、過去 14 天、過去 30 天、過去 60 天、過去 90 天 |
| 2020 年 9 月 17 日 | 有關[工作區中媒體同時檢閱者面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers.html)的新文件 |
| **2020 年 8 月** | |
| 2020 年 8 月 31 日 | 已在 Cross-Device Analytics 中的[欄位式銜接文件](https://experienceleague.adobe.com/docs/analytics/components/cda/field-based-stitching.html)中新增增強功能。 |
| **2020 年 7 月** | |
| 2020 年 7 月 21 日 | [Cross-Device Analytics](/help/components/cda/overview.md) 的主要更新和修訂項目。新增[依欄位彙整](/help/components/cda/field-based-stitching.md)。 |
| 2020 年 7 月 16 日 | 工作區中的新日期範圍預設集。新增 4 個日期範圍：([!UICONTROL 本週/本月/本季/今年 [不包括今天]])。這可讓您選擇不包括今天部分資料的日期範圍。 |
| **2020 年 6 月** | |
| 2020 年 6 月 25 日 | 工作區中 [Quick Insights 面板](/help/analyze/analysis-workspace/c-panels/quickinsight.md)的新文件。它為 Analysis Workspace 的非分析師和新使用者提供指引，讓他們了解如何快速輕鬆地解答業務問題。 |
| 2020 年 6 月 25 日 | 工作區中 [Analytics for Target 面板](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)的新文件。它可讓您輕鬆自信地分析您的 Adobe Target 活動和體驗。 |
| 2020 年 6 月 18 日 | 有關[歸因：演算法歸因](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/algorithmic.html)的新文件 |
| 2020 年 6 月 18 日 | 有關[歸因：自訂回顧期間](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html#lookback-windows)的新文件 |
| 2020 年 6 月 18 日 | 有關共用工作區專案的[專案角色](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html)的新文件。共用工作區專案時，您現在可以根據您希望收件者擁有的專案體驗，將收件者置於下列三個專案角色之一：編輯、複製和檢視。 |
| 2020 年 6 月 18 日 | 有關[「僅供檢視」工作區專案](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/view-only-projects.html)的新文件。專案能以「可供檢視」狀態和使用者共用。當「檢視」收件者開啟共用專案時，獲得的專案體驗限制較嚴格，除了沒有左側欄，互動也會受限。 |
| 2020 年 6 月 18 日 | 有關共用工作區專案的[專案角色](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html)的新文件。共用工作區專案時，您現在可以根據您希望收件者擁有的專案體驗，將收件者置於下列三個專案角色之一：編輯、複製和檢視。 |
| 2020 年 6 月 18 日 | 有關[「共同編輯」工作區專案](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html)的新文件。新增至「可編輯」角色的收件者可在已與其共用的專案中執行儲存作業。無論管理員或非管理人員都適用。 |
| **2020 年 5 月** |  |
| 2020 年 5 月 31 日 | 有關[大量資料插入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) 的新文件 |
| 2020 年 5 月 21 日 | 有關 [Adobe Analytics 儀表板](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html)的新文件 |
| 2020 年 5 月 21 日 | 有關 Analysis Workspace 的[協助工具改良](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/aw-accessibility.html)的新文件，包括改良的鍵盤導覽、色彩比對和螢幕助讀程式支援。 |
| **2020 年 4 月** |  |
| 2020 年 4 月 28 日 | 新增[「內容速度」](/help/components/metrics/content-velocity.md)量度的文件。 |
| 2020 年 4 月 16 日 | 有關如何從空白狀態自動建立[!UICONTROL 自由表格]的文件。以前您必須先新增自由表格，無法直接將元件拖放到空白專案或空白面板中。現在，您可以直接將元件拖放至空白的專案或面板，由系統自動以建議的格式為您建立自由表格。此外，新版也已改善混合元件類型 (例如維度和量度) 一併放入空白[!UICONTROL 自由表格]時的處理方式。 |
| **2020 年 3 月** |  |
| 2020 年 3 月 12 日 | 為[將區段發佈至 Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-publish.md) 新增更新內容。 |
| 2020 年 3 月 12 日 | 更新 CDA 編結延遲。 |
| 2020 年 3 月 12 日 | 對工作區中多個報告套裝的支援。您現在可以將多個報告套裝的資料匯入同一個專案以並排檢視。[了解更多...](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) |
| 2020 年 3 月 12 日 | 工作區中的培訓教學課程範本。這個全新的標準範本會逐步引導您了解常用術語，以及在工作區中初次建立分析的步驟。若新使用者的清單中沒有其他專案，這會顯示為「新增專案」模組中的標準範本，取代目前現有的範例專案。[了解更多...](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) |
| **2020 年 2 月** |  |
| 2020 年 2 月 27 日 | 新增 [Adobe Analytics Labs](/help/analyze/labs.md) 的文件。 |
| 2020 年 2 月 25 日 | 新增 [`useLinkTrackSessionStorage`](/help/implement/vars/config-vars/uselinktracksessionstorage.md) 變數。 |
| 2020 年 2 月 20 日 | 使用 Cross-Device Analytics 的組織適用的新工作區範本。此範本顯示 CDA 如何有效地將造訪結合在一起，並說明 CDA 專屬的維度和量度。需使用 CDA 的報告套裝。如需詳細資訊，請參閱[設定 Cross-Device Analytics](/help/components/cda/setup.md)。 |
| 2020 年 2 月 20 日 | 工作區中的全新快速鍵：<ul><li>摺疊/展開所有面板：`alt + m`</li><li>摺疊/展開作用中的面板：`alt + ctrl + m`</li><li>搜尋左側邊欄：`ctrl + /`</li><li>移至下一個面板：`alt + Right Key`</li><li>移至上一個面板：`alt + Left Key`</li></ul>[了解更多...](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html) |
| 2020 年 2 月 20 日 | 工作區增強功能： <ul><li>現在於 Workspace 中置入面板或視覺效果時，左側邊欄會自動切換為元件，使工作流程更加順暢。</li><li>現在可對範本元件執行操作 (例如加上標記、標示為我的最愛、核准)。</li><li>篩選後得到的量度和區段清單提供 + 按鈕，方便您在找不到所需內容時用來新增元件。</li></ul> |
| 2020 年 2 月 20 日 | 已在「說明」選單中新增工作區偵錯程式，好讓您更順暢地啟用它來偵錯工作區請求。[了解更多...](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md) |
| 2020 年 2 月 18 日 | 新增 [`writeSecureCookies`](/help/implement/vars/config-vars/writesecurecookies.md) 變數。 |
| 2020 年 2 月 12 日 | 更新及重新整理[行銷管道](/help/components/c-marketing-channels/c-getting-started-mchannel.md)文件。 |
| 2020 年 2 月 12 日 | 已在[這個工作區頁面](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html)中新增快速鍵 |
| 2020 年 2 月 7 日 | 更新[設定 Cross-Device Analytics](/help/components/cda/setup.md) 及[常見問題集](/help/components/cda/faq.md) |
| 2020 年 2 月 4 日 | 徹底重寫[實作使用者指南](/help/implement/home.md)。 |
| 2020 年 1 月 22 日 | 更新「自由表格」頁面，加入新[自由表格產生器](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)的相關資訊。 |
| **2020 年 1 月** | |
| 2020 年 1 月 24 日 | 工作區中「[列設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/column-row-settings/table-settings.html#cja-workspace)」頁面的更新。 |
| 2020 年 1 月 16 日 | 有關[自由表格產生器](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html)的新文件。啟用「表格產生器」後，許多維度、劃分、量度和區段都可直接拖放使用，方便建立可回答更複雜商業問題的表格。資料不會立即更新，而是在您確定要建立的表格並點擊&#x200B;**[!UICONTROL 「建立」]**&#x200B;後，資料才會更新，為您節省寶貴時間。此外，這項功能也提供以下輔助功能：<ul><li>**預覽**：演算實際資料前，您可以先預覽表格格式。</li><li>**彈性的表格列與劃分設定**：您可以針對每個維度列設定列與劃分層級。以前，Workspace 的預設內容只有在資料回傳後才能變更。</li><li>**依位置劃分**：您可以設定維度列，一律&#x200B;_依位置劃分_&#x200B;而非&#x200B;_依特定項目_&#x200B;劃分 (預設)。</li><li>**手動靜態列排序**：您可以手動排序靜態列，讓表格列能依您的需求顯示。以前，靜態列只能依量度欄或字母順序排序。</li></ul> |
| 2020 年 1 月 13 日 | 新增 [Adobe Analytics 與瀏覽器 Cookie](/help/technotes/cookies/cookies.md)。 |
| 2020 年 1 月 13 日 | 已修改「[我該使用哪種 Adobe Analytics 工具呢](/help/analyze/get-started/which-analytics-tool.md)」頁面。 |

### 2019 {#year2019}

| 功能 | 說明 |
| --- | --- |
| 2020 年 12 月 19 日 | 已將預設 [FTP 資料儲存空間限制](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-limits.html)變更為 10 GB。 |
| 2019 年 11 月 29 日 | 編修[資料摘要文件](/help/export/analytics-data-feed/data-feed-overview.md) |
| 2019 年 11 月 25 日 | 有關「強制 IP 登入限制」服務終止的新主題。 |
| 2019 年 11 月 21 日 | 針對 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html) 建立的文件 |
| 2019 年 11 月 21 日 | 已更新 [Audience Analytics 工作流程常見問題集](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html)來指示直播串流中的可用性。 |
| 2019 年 10 月 25 日 | 已更新「[Adobe Analytics 重要概念](/help/technotes/terms.md)」頁面。 |
| 2019 年 10 月 10 日 | 自由格式表格總計的更新：這類表格現在包含兩個總計：**[!UICONTROL 表格總計]**&#x200B;和&#x200B;**[!UICONTROL 總和]**。表格總計列計入套用的[報告篩選器](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.html)。以前只有區段會影響總計。[深入了解](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html)<br/>此外，**[!UICONTROL 「顯示總計」]**&#x200B;和&#x200B;**[!UICONTROL 「顯示總量」]**&#x200B;選項已新增至&#x200B;**[!UICONTROL 「欄設定」]**。<br/>自由表格總計經過此變更後，相依的視覺效果也會隨之更新 (例如連結的&#x200B;**[!UICONTROL 摘要數字]**&#x200B;視覺效果)，以及匯出的 CSV 和 PDF 資料。 |
| 2019 年 10 月 10 日 | 在工作區中，輕鬆地移除「未指定 (無)」的功能已新增為報告篩選的選項。 |
| 2019 年 10 月 10 日 | 在工作區中，紫色的粒度元件 (分鐘、小時、天、週、月、季、年) 已過時。如果您先前已使用其中一個紫色時間元件，則&#x200B;**不需要採取任何動作**。<br/>透過這項變更，紫色&#x200B;**[!UICONTROL 時間]**&#x200B;區段也已重新命名為&#x200B;**[!UICONTROL 日期範圍]**。 |
| 2019 年 10 月 1 日 | 有關[工作區總計](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/workspace-totals.html#cja-workspace)的新文件。 |
| 2019 年 9 月 28 日 | [Javascript 實作的設定變數](/help/implement/vars/config-vars/configuration-variables.md)的相關新文章 |
| 2019 年 9 月 19 日 | 已修改分段文件來說明[邏輯群組容器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-sequential-build.html#logic-group-containers)。 |
| 2019 年 9 月 12 日 | [跨裝置分析](/help/components/cda/overview.md)的新文件 |
| 2019 年 9 月 12 日 | 更新[計算量度總計](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html)文件。 |
| 2019 年 8 月 28 日 | [Analytics 專用漸進式網頁應用程式](/help/technotes/pwa.md)的相關新文章 |
| 2019 年 8 月 8 日 | 新增[計算量度總計](/help/components/c-calcmetrics/cm-totals.md)文章 |
| 2019 年 8 月 8 日 | 進一步釐清[啟用時間戳記的作業資料](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md) |
| 2019 年 8 月 8 日 | 在工作區中，Adobe 將靜態下拉式篩選器中可放置的項目數上限從 50 個增加到 200 個。此增強功能適合多種使用案例，例如將所有國家/區域 (195) 新增至篩選條件，或新增所有美國州和省 (52)。 |
| 2019 年 8 月 2 日 | [Analytics 字彙表](/help/technotes/terms.md)重大更新 |
| 2019 年 7 月 22 日 | [Analysis Workspace 範本](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)文件新增「Magento：行銷和商務」範本。 |
| 2019 年 7 月 18 日 | 更新[「同類群組表格」設定](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。 |
| 2019 年 7 月 18 日 | 在工作區的左側欄中，使用者現在可以選擇「_顯示過去 18 個月的項目_」。之前，回顧期間的上限為 6 個月。這能讓您更加輕鬆地與去年或最多 18 個月前的頁面或行銷活動進行比較。 |
| 2019 年 7 月 18 日 | 有關 Analysis Workspace 中稱為[「Magento：行銷和商務」](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html)的全新工作區範本的文件。此範本是專為 Magento 電子商務客戶所設計，但所有零售商都可使用此範本來取得有關其商務活動的獨特分析。 |
| 2019 年 6 月 13 日 | 已在工作區中的左側欄搜尋中新增立即可用的篩選器。除了您今天看到的項目 (維度、量度、已批准等)，新增了新的篩選器，包括計算量度、客戶屬性、eVar、Prop、影片等，讓您能夠輕鬆找到您需要的元件。 |
| 2019 年 6 月 4 日 | 全新指南撰寫完成，標題為[從協力廠商的分析平台改用 Adobe Analytics](/help/technotes/ga-to-aa/home.md)。 |
| 2019 年 5 月 30 日 | 編修[資料摘要欄參考資訊](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)。 |
| 2019 年 5 月 9 日 | 已在「流量」視覺效果中新增設定：「包含重複執行個體」。請參閱[流量設定](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) |
| 2019 年 4 月 11 日 | 工作區最佳化增強功能的最佳做法：效能最佳化 |
| 2019 年 4 月 11 日 | 更新 [Workspace 效能最佳化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)。 |
| 2019 年 3 月 14 日 | 大幅更新區域資料收集。 |
| 2019 年 2 月 7 日 | 微幅更新[一般帳戶設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)中的「將 IP 位址的最後八位數字取代為 0 」和「IP 模糊化」設定。 |
| 2019 年 2 月 1 日 | 大幅更新 [getPercentPageViewed](../implement/vars/plugins/getpercentpageviewed.md) 實作外掛程式。 |
| 2019 年 1 月 17 日 | [同類群組分析](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) - 同類群組分析的重大改良可讓您：<ul><li>分別套用區段包含和回訪量度。 </li><li>顯示流失率而非保留率。</li><li>顯示延時表格 (包含事件前後經過的時間)。</li><li>自訂同類群組維度 (根據 eVar 將訪客分組，而非僅根據時間)。</li><li>執行滾動式同類群組計算：根據先前時段 (而非原始同類群組) 計算保留率/流失率。 </li><li>在包含與回訪欄位中新增多個量度，並套用區段。(不支援計算量度)</li></ul> |
| 2019 年 1 月 17 日 | [檢視密度](/help/analyze/analysis-workspace/build-workspace-project/view-density.md)。此新設定可減少左側邊欄、自由表格和同類群組表格的垂直邊框間距，讓您在單一畫面上查看更多資料。您可透過「專案 > 專案資訊與設定」，存取此設定。 |
| 2019 年 1 月 17 日 | [支援歸因中的多值變數](/help/analyze/analysis-workspace/attribution/overview.md)。Analytics 的部分維度可包含單一點擊的多個數值，例如 listVar、產品變數、清單 prop 或銷售 eVar。Analysis Workspace 可讓您將歸因套用至這些點擊層級變數。 |
