---
product: analytics
audience: admin
user-guide-title: Analytics 管理員指南
breadcrumb-title: 管理指南
user-guide-description: 了解 Analytics 管理工作，例如在 Experience Cloud Admin Console 中管理使用者和產品、設定報告套裝等。
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 99%

---


# Adobe Analytics 管理員指南 {#admin}

+ [Analytics管理指南](home.md)
+ [Analytics 發行說明](https://experienceleague.adobe.com/zh-hant/docs/analytics/release-notes/latest)
+ Adobe Admin Console  {#admin-console}
   + [概觀](admin-console/home.md)
   + [Adobe Analytics 的第一個管理指南](admin-console/first-admin-guide.md)
   + [Adobe Analytics 中的管理員角色](admin-console/admin-roles-in-analytics.md)
   + Analytics 工具權限摘要 {#permissions}
      + [Adobe Analytics 產品設定檔](admin-console/permissions/product-profile.md)
      + [報告套裝工具的產品設定檔權限](admin-console/permissions/report-suite-tools.md)
      + [Analytics 工具的產品設定檔權限](admin-console/permissions/analytics-tools.md)
+ Analytics 管理員工具 {#admin-tools}
   + [管理員工具概觀](tools/c-admin-tools.md)
   + [程式碼管理員](tools/code-manager-admin.md)
   + [Analytics 庫存](tools/analytics-inventory.md)
   + [資料來源](tools/data-sources.md)
   + [依 IP 位址排除](tools/exclude-ip.md)
   + [記錄檔](tools/logs.md)
   + 報告活動管理器 {#reporting-activity-manager}
      + [概觀](tools/reporting-activity-manager/reporting-activity-overview.md)
      + [檢視報告活動](tools//reporting-activity-manager/reporting-activity.md)
      + [取消報告請求](tools/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + 元件移轉  {#component-migration}
      + [準備移轉](tools/component-migration/prepare-component-migration.md)
      + [移轉工作流程](tools/component-migration/component-migration.md)
   + 報告套裝管理員 {#manage-report-suites}
      + 編輯報告套裝的設定值  {#edit-report-suite}
         + 一般 {#report-suite-general}
            + [一般帳戶設定](tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
            + [內部 URL 篩選器](tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)
            + [自訂行事曆](tools/manage-rs/edit-settings/general/custom-calendar.md)
            + 付費搜尋偵測 {#paid-search-detection}
               + [付費搜尋偵測概觀](tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)
               + [設定付費搜尋偵測](tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)
            + 處理規則 {#processing-rules}
               + [概觀](tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
               + [介面](tools/manage-rs/edit-settings/general/processing-rules/pr-interface.md)
               + [檢視歷史記錄](tools/manage-rs/edit-settings/general/processing-rules/pr-view-history.md)
               + [複製規則](tools/manage-rs/edit-settings/general/processing-rules/pr-copy.md)
               + [可供使用的維度和量度](tools/manage-rs/edit-settings/general/processing-rules/pr-variables.md)
               + [使用案例](tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)
            + 機器人規則 {#bot-removal}
               + [移除機器人](tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md)
               + [了解和設定機器人規則](tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)
               + [常見的機器人簽名](tools/manage-rs/edit-settings/general/bot-removal/bot-signatures.md)
               + [排除機器人的方法](tools/manage-rs/edit-settings/general/bot-removal/bot-exclusion-methods.md)
            + [隱私權設定](tools/manage-rs/edit-settings/general/privacy-settings.md)
            + [時間戳記設定](tools/manage-rs/edit-settings/general/timestamp-optional.md)
            + 伺服器端轉送功能 {#server-side-forwarding}
               + [伺服器端轉送概觀](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
               + [GDPR/ePrivacy 法規遵循與伺服器端轉送](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)
               + [伺服器端轉送需求](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-requirements.md)
               + [伺服器端轉送資料和程式碼參考](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-reference.md)
               + [如何確認您的伺服器端轉送實作情形](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)
               + [伺服器端轉送常見問題](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)
         + 流量 {#traffic-variables}
            + [流量變數](tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
            + [流量分類](tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md)
            + [自訂報告說明](tools/manage-rs/edit-settings/c-traffic-variables/custom-desc-admin.md)
         + 轉換 {#conversion-variables}
            + [轉換變數](tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)
            + [尋找方法](tools/manage-rs/edit-settings/conversion-var-admin/finding-methods.md)
            + [轉換分類](tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)
            + 不重複訪客變數 {#unique-visitor-variable}
               + [指定不重複訪客變數](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [使用案例 - 擷取訪客 ID](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [成功事件](tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)
            + [分類階層](tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)
            + [清單變數](tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)
            + [銷售 eVar](tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md)
         + 行銷管道 {#marketing-channels}
            + [行銷管道管理員](tools/manage-rs/edit-settings/marketing-channels/c-channels.md)
            + [行銷管道處理規則](tools/manage-rs/edit-settings/marketing-channels/c-rules.md)
            + [行銷管道分類](tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md)
            + [行銷管道期限](tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md)
         + 流量管理 {#traffic-management}
            + [概觀](tools/manage-rs/edit-settings/c-traffic-management/traffic-management.md)
            + [排程尖峰](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md)
            + [永久流量](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-permanent.md)
         + [預設量度](tools/manage-rs/edit-settings/default-metrics.md)
         + 應用程式管理 {#app-management}
            + [應用程式報告](tools/manage-rs/edit-settings/app-reporting.md)
            + [應用程式分類](tools/manage-rs/edit-settings/app-classifications.md)
         + [媒體管理](tools/manage-rs/edit-settings/media-management.md)
         + [Activity Map](tools/manage-rs/edit-settings/activity-map.md)
         + [AEM](tools/manage-rs/edit-settings/adobe-experience-manager.md)
         + [Adobe Campaign](tools/manage-rs/edit-settings/adobe-campaign.md)
         + [隱私權報告](tools/manage-rs/edit-settings/privacy-reporting.md)
         + Document Cloud 管理 {#doc-cloud-mgt}
            + [使用 Adobe Analytics 設定 Document Cloud](tools/manage-rs/edit-settings/document-cloud-mgt.md)
            + [設定 Document Cloud 報告](tools/manage-rs/edit-settings/document-cloud-config.md)
         + [Advertising Analytics 設定](tools/manage-rs/edit-settings/advertising-analytics-config.md)
         + 即時 {#real-time-reports}
            + [即時報表概觀](tools/manage-rs/edit-settings/realtime/realtime.md)
            + [即時報表設定](tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)
            + [支援的即時量度和維度](tools/manage-rs/edit-settings/realtime/realtime-metrics.md)
      + [管理報告套裝](tools/manage-rs/report-suites-admin.md)
      + [全域報告套裝](tools/manage-rs/rollup-report-suite.md)
      + [儲存報告套裝搜尋](tools/manage-rs/t-report-suite-saved-search.md)
      + [下載報告套裝設定值](tools/manage-rs/t-download-rs-settings.md)
      + 新的報告套裝  {#c-new-report-suite}
         + [建立報告套裝](tools/manage-rs/new-rs/t-create-a-report-suite.md)
         + [建立報告套裝群組](tools/manage-rs/new-rs/t-create-rs-group.md)
         + [新的報告套裝 - 設定](tools/manage-rs/new-rs/new-report-suite.md)
         + [並非從來源報告套裝複製的設定](tools/manage-rs/new-rs/settings-not-copied-from-rs.md)
      + 報告套裝範本  {#report-suite-templates}
         + [報告套裝範本概觀](tools/manage-rs/rs-templates/report-suite-templates.md)
         + [整合入口網站](tools/manage-rs/rs-templates/aggregator-portal.md)
         + [商務](tools/manage-rs/rs-templates/commerce-admin.md)
         + [內容與媒體](tools/manage-rs/rs-templates/content-media.md)
         + [預設範本](tools/manage-rs/rs-templates/default-rs-template.md)
         + [金融服務](tools/manage-rs/rs-templates/financial-services.md)
         + [工作入口網站](tools/manage-rs/rs-templates/job-portal.md)
         + [銷售機會開發](tools/manage-rs/rs-templates/lead-generation.md)
         + [支援媒體](tools/manage-rs/rs-templates/support-media.md)
   + 公司設定 {#company-settings}
      + [公司設定概觀](tools/company/c-company-settings.md)
      + [安全管理員](tools/company/security-manager.md)
      + [網路服務](tools/company/web-services-admin.md)
      + [Report Builder 報表](tools/company/report-builder-reports-admin.md)
      + [單一登入](tools/company/single-signon-admin.md)
      + [隱藏報告套裝](tools/company/c-hide-report-suites.md)
      + [偏好設定管理器](tools/company/preferences-manager.md)
      + [擱置中的動作](tools/company/pending-actions-admin.md)
      + [功能存取層級](tools/company/feature-access-levels.md)
   + 加上隱私標籤 {#privacy-labeling}
      + [概觀](tools/privacy-labeling/labeling-overview.md)
      + [Analytics 元件的資料隱私權標籤](tools/privacy-labeling/labels.md)
      + [檢視/管理報告套裝的隱私標籤](tools/privacy-labeling/view-settings.md)
      + [標籤最佳做法](tools/privacy-labeling/best-practices.md)
      + [標籤範例](tools/privacy-labeling/examples.md)
      + [命名空間](tools/privacy-labeling/namespaces.md)
   + 伺服器呼叫使用量 {#server-call-usage}
      + [伺服器呼叫使用量概觀](tools/server-call-usage/overage-overview.md)
      + [檢視目前伺服器呼叫使用量](tools/server-call-usage/server-call-usage-dashboard.md)
      + [檢視報告套裝使用量](tools/server-call-usage/report-suite-usage.md)
      + [伺服器呼叫使用量警報](tools/server-call-usage/scu-alerts.md)
      + [伺服器呼叫使用量常見問題](tools/server-call-usage/overage-faq.md)
   + 使用者和產品管理 (舊版) {#user-product-management}
      + [使用者和產品管理 (舊版)](tools/user-management/user-management.md)
      + [管理舊版使用者帳戶、資產和截止期限](tools/user-management/users-assets.md)
      + 將使用者移轉至 Adobe Admin Console  {#migrate-users}
         + [Analytics 使用者移轉至 Admin Console](tools/user-management/user-migration/c-migration-tool.md)
         + [移轉 Adobe ID 的 Analytics 使用者帳戶](tools/user-management/user-migration/t-migrate-users.md)
         + [移轉 Enterprise ID 與 Federated ID 的 Analytics 使用者帳戶](tools/user-management/user-migration/migrate-enterprise.md)
         + [停用舊版登入](tools/user-management/user-migration/t-disable-legacy-login.md)
         + [受移轉影響的 API](tools/user-management/user-migration/developer.md)
+ [管理員 API](c-admin-api/c-admin-api.md)
+ [Adobe Analytics 1.4 API 終止更新常見問題](c-admin-api/c-admin-14-api-eol.md)

