---
product: analytics
audience: admin
user-guide-title: Analytics 管理員指南
breadcrumb-title: 管理指南
user-guide-description: 了解 Analytics 管理工作，例如在 Experience Cloud Admin Console 中管理使用者和產品、設定報表套裝等。
source-git-commit: 869b44b826de5cb35d13000133092397cb16ccaa
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 98%

---


# Adobe Analytics 管理員指南 {#admin}

+ [Analytics 管理員指南](home.md)
+ [Analytics 版本注意事項](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
+ Adobe Admin Console {#admin-console}
   + [概觀](admin-console/home.md)
   + [Adobe Analytics 的第一個管理指南](admin-console/first-admin-guide.md)
   + [Adobe Analytics 中的管理員角色](admin-console/admin-roles-in-analytics.md)
   + Analytics 工具權限摘要{#permissions}
      + [Adobe Analytics 產品設定檔](admin-console/permissions/product-profile.md)
      + [報表套裝工具的產品設定檔權限](admin-console/permissions/report-suite-tools.md)
      + [Analytics 工具的產品設定檔權限](admin-console/permissions/analytics-tools.md)
+ Analytics 管理員工具{#admin-tools}
   + [管理員工具概觀](admin/c-admin-tools.md)
   + [程式碼管理員](admin/code-manager-admin.md)
   + [資料來源](admin/data-sources.md)
   + [依 IP 位址排除](admin/exclude-ip.md)
   + [記錄檔](admin/logs.md)
   + 報告活動管理員 {#reporting-activity-manager}
      + [概觀](admin/reporting-activity-manager/reporting-activity-overview.md)
      + [檢視報告活動](admin//reporting-activity-manager/reporting-activity.md)
      + [取消報告請求](admin/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + 元件移轉 {#component-migration}
      + [準備移轉](admin/component-migration/prepare-component-migration.md)
      + [移轉工作流程](admin/component-migration/component-migration.md)
   + 報告套裝管理員 {#manage-report-suites}
      + 編輯報表套裝的設定值 {#edit-report-suite}
         + 一般 {#report-suite-general}
            + [一般帳戶設定](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [內部 URL 篩選器](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + [自訂行事曆](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + 付費搜尋偵測 {#paid-search-detection}
               + [付費搜尋偵測總覽](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [設定付費搜尋偵測](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + 處理規則 {#c-processing-rules}
               + [處理規則總覽](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)
               + 處理規則 {#c-processing-rules-configuration}
                  + [處理規則的運作方式](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
                  + [建立處理規則](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
                  + [檢視作用中的處理規則](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
                  + [檢視處理規則記錄](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
                  + [還原處理規則](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
                  + [複製處理規則至其他報表套裝](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
                  + [可用於處理規則的維度](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rule-dimensions.md)
               + 處理規則範例 {#processing-rules-examples}
                  + [處理規則的範例](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
                  + [從查詢字串參數填入行銷活動 ID](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
                  + [從產品總覽頁面設定產品檢視事件](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
                  + [串連類別和頁面名稱以新增子類別](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
                  + [將 eVar 值複製至 Prop 以判斷路徑](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
                  + [清除報表中的值](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
                  + [使用查詢字串參數填入內部搜尋詞](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
                  + [複製內容資料變數至 eVar](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
                  + [使用內容資料變數設定事件](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
                  + [從點擊中移除事件](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
               + [處理規則提示與秘訣](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-tips.md)
            + 機器人規則 {#bot-removal}
               + [移除機器人](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [了解和設定機器人規則](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [常見的機器人簽名](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [排除機器人的方法](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [隱私權設定](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [時間戳記設定](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + 伺服器端轉送功能 {#server-side-forwarding}
               + [伺服器端轉送總覽](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [GDPR/ePrivacy 法規遵循與伺服器端轉送](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [伺服器端轉送需求](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [伺服器端轉送資料和程式碼參考](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [如何確認您的伺服器端轉送實施情形](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [伺服器端轉送常見問題](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + 流量 {#traffic-variables}
            + [流量變數](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [流量分類](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [自訂報告說明](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + 轉換 {#conversion-variables}
            + [轉換變數](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [尋找方法](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + [轉換分類](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + 不重複訪客變數 {#unique-visitor-variable}
               + [指定不重複訪客變數](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [使用案例 - 擷取訪客 ID](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + 成功事件 {#success-events}
               + [成功事件總覽](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
               + [設定成功事件](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/t-success-events.md)
               + [關於變更事件類型](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md)
            + [分類階層](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [清單變數](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [銷售 eVar](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
         + 行銷管道 {#marketing-channels}
            + [行銷管道管理員](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
            + [行銷管道處理規則](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
            + [行銷管道分類](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
            + [行銷管道有效期](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
         + 流量管理 {#traffic-management}
            + [概觀](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [排程尖峰](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [永久流量](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [預設量度](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
         + 應用程式管理 {#app-management}
            + [應用程式報告](admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md)
            + [應用程式分類](admin/c-manage-report-suites/c-edit-report-suites/app-classifications.md)
         + [媒體管理](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
         + [Activity Map](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
         + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
         + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
         + [隱私權報告](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
         + Document Cloud 管理{#doc-cloud-mgt}
            + [使用 Adobe Analytics 設定 Document Cloud](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-mgt.md)
            + [設定 Document Cloud 報告](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-config.md)
         + [Advertising Analytics 設定](admin/c-manage-report-suites/c-edit-report-suites/advertising-analytics-config.md)
         + 即時 {#real-time-reports}
            + [即時報表總覽](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [即時報表設定](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [支援的即時量度和維度](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
      + [管理報告套裝](admin/c-manage-report-suites/report-suites-admin.md)
      + [全域報告套裝](admin/c-manage-report-suites/rollup-report-suite.md)
      + [儲存報表套裝搜尋](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [下載報表套裝設定值](admin/c-manage-report-suites/t-download-rs-settings.md)
      + 新的報表套裝 {#c-new-report-suite}
         + [建立報表套裝](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [建立報表套裝群組](admin/c-manage-report-suites/c-new-report-suite/t-create-rs-group.md)
         + [新的報表套裝 - 設定](admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
         + [並非從來源報表套裝複製的設定](admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
      + 報表套裝範本 {#report-suite-templates}
         + [報表套裝範本總覽](admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
         + [整合入口網站](admin/c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
         + [商務](admin/c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
         + [內容與媒體](admin/c-manage-report-suites/c-report-suite-templates/content-media.md)
         + [預設範本](admin/c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
         + [金融服務](admin/c-manage-report-suites/c-report-suite-templates/financial-services.md)
         + [工作入口網站](admin/c-manage-report-suites/c-report-suite-templates/job-portal.md)
         + [銷售機會開發](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
         + [支援媒體](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
   + 公司設定 {#company-settings}
      + [公司設定總覽](admin/company/c-company-settings.md)
      + [安全管理員](admin/company/security-manager.md)
      + [網路服務](admin/company/web-services-admin.md)
      + [Report Builder 報表](admin/company/report-builder-reports-admin.md)
      + [單一登入](admin/company/single-signon-admin.md)
      + [隱藏報告套裝](admin/company/c-hide-report-suites.md)
      + [偏好設定管理器](admin/company/preferences-manager.md)
      + [擱置中的動作](admin/company/pending-actions-admin.md)
      + [功能存取層級](admin/company/feature-access-levels.md)
   + 資料控管隱私權標籤 {#data-governance}
      + [Adobe Analytics 資料隱私權工作流程](admin/c-data-governance/an-gdpr-workflow.md)
      + [常見問題](admin/c-data-governance/gdpr-faq.md)
      + 資料標記 {#data-labels}
         + [Analytics 元件的資料隱私權標籤](admin/c-data-governance/data-labeling/gdpr-labels.md)
         + [標籤報表套裝資料](admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
         + [檢視/管理報告套裝的隱私標籤](admin/c-data-governance/data-labeling/gdpr-view-settings.md)
         + [標籤最佳做法](admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)
         + [標籤範例](admin/c-data-governance/data-labeling/gdpr-labeling-example.md)
         + [命名空間](admin/c-data-governance/data-labeling/gdpr-namespaces.md)
      + [ID 擴增](admin/c-data-governance/gdpr-id-expansion.md)
      + [CNIL 同意豁免](admin/c-data-governance/cnil-consent-exemption.md)
   + 伺服器呼叫使用量 {#server-call-usage}
      + [伺服器呼叫使用量總覽](admin/c-server-call-usage/overage-overview.md)
      + [檢視目前伺服器呼叫使用量](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [檢視報表套裝使用量](admin/c-server-call-usage/report-suite-usage.md)
      + [伺服器呼叫使用量警報](admin/c-server-call-usage/scu-alerts.md)
      + [伺服器呼叫使用量常見問題](admin/c-server-call-usage/overage-faq.md)
   + 使用者和產品管理 (舊版) {#user-product-management}
      + [使用者和產品管理 (舊版)](admin/user-management2/user-management.md)
      + [管理舊版使用者帳戶、資產和到期日](admin/user-management2/users-assets.md)
      + 將使用者移轉至 Adobe Admin Console {#migrate-users}
         + [Analytics 使用者移轉至 Admin Console](admin/user-management2/user-migration/c-migration-tool.md)
         + [移轉 Adobe ID 的 Analytics 使用者帳戶](admin/user-management2/user-migration/t-migrate-users.md)
         + [移轉 Enterprise ID 與 Federated ID 的 Analytics 使用者帳戶](admin/user-management2/user-migration/migrate-enterprise.md)
         + [停用舊版登入](admin/user-management2/user-migration/t-disable-legacy-login.md)
         + [受移轉影響的 API](admin/user-management2/user-migration/developer.md)
+ [管理員 API](c-admin-api/c-admin-api.md)

