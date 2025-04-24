---
product: analytics
audience: end-user
user-guide-title: Analytics 轉存指南
breadcrumb-title: 轉存指南
user-guide-description: 了解如何使用資料摘要匯出原始資料，以及如何使用 Data Warehouse 擷取試算表輸出資料。了解如何使用 FTP 和 SFTP 傳輸檔案。
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: ht
source-wordcount: '279'
ht-degree: 100%

---


# Adobe Analytics 轉存指南 {#export}

+ [Analytics 轉存指南](home.md)
+ [Analytics 版本注意事項](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
+ Analytics 資料摘要 {#analytics-data-feed}
   + [資料摘要概觀](analytics-data-feed/data-feed-overview.md)
   + [建立資料摘要](analytics-data-feed/create-feed.md)
   + [管理資料摘要](analytics-data-feed/df-manage-feeds.md)
   + [管理資料摘要工作](analytics-data-feed/df-manage-jobs.md)
   + 資料摘要內容  {#data-feed-contents}
      + [資料摘要內容概觀](analytics-data-feed/c-df-contents/datafeeds-contents.md)
      + [計算量度](analytics-data-feed/c-df-contents/datafeeds-calculate.md)
      + [資料欄參考](analytics-data-feed/c-df-contents/datafeeds-reference.md)
      + [頁面事件查閱](analytics-data-feed/c-df-contents/datafeeds-page-event.md)
      + [動態查詢](analytics-data-feed/c-df-contents/dynamic-lookups.md)
      + [銷售 eVar 查閱](analytics-data-feed/c-df-contents/merchandising-evar-lookup.md)
      + [特殊字元](analytics-data-feed/c-df-contents/datafeeds-spec-chars.md)
      + [延遲送達點擊](analytics-data-feed/c-df-contents/late-arriving-hits.md)
   + [資料摘要常見問答集](analytics-data-feed/df-faq.md)
   + [資料摘要最佳做法](analytics-data-feed/data-feeds-best-practices.md)
   + [資料摘要的疑難排解](analytics-data-feed/troubleshooting.md)
+ Data Warehouse {#data-warehouse}
   + [Data Warehouse 概觀](data-warehouse/data-warehouse.md)
   + [新增 Data Warehouse 使用者群組](data-warehouse/t-dw-group.md)
   + 建立 Data Warehouse 請求 {#dw-create-request}
      + [建立 Data Warehouse 請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)
      + [一般設定](/help/export/data-warehouse/create-request/dw-general-settings.md)
      + [建置您的報告](/help/export/data-warehouse/create-request/dw-request-build-report.md)
      + [報告目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
      + [報告選項](/help/export/data-warehouse/create-request/dw-request-report-options.md)
      + [排程選項](/help/export/data-warehouse/create-request/dw-request-scheduling.md)
      + [通知電子郵件](/help/export/data-warehouse/create-request/dw-request-email.md)
   + [要求傳送時間](data-warehouse/delivery-time.md)
   + [Tableau 資料檔案](data-warehouse/t-tableau.md)
   + [依量度排序](data-warehouse/sorting-by-metric.md)
   + [管理 Data Warehouse 請求](data-warehouse/data-warehouse-requests-manage.md)
   + [Data Warehouse 支援的元件](data-warehouse/component-support.md)
   + [Data Warehouse 最佳作法](data-warehouse/data-warehouse-bp.md)
+ FTP 和 SFTP {#ftp-and-sftp}
   + [透過 Adobe Experience Cloud 使用 FTP 和 SFTP](ftp-and-sftp/ftp-overview.md)
   + 設定 Adobe 託管的 FTP 帳戶  {#set-up-ftp-accounts}
      + [設定 FTP 帳戶 - 概觀](ftp-and-sftp/c-set-up-ftp-accounts/ftp-accounts.md)
      + [分類](ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)
      + [資料來源](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)
      + [資料摘要](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)
      + [Data Warehouse 傳遞的報表](ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)
      + [Report Builder 傳遞的報表](ftp-and-sftp/c-set-up-ftp-accounts/ftp-arb-reports.md)
      + [工程技術服務參與 FTP](ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md)
   + [FTP 限制和資料保留](ftp-and-sftp/ftp-limits.md)
   + [刪除 FTP 資料和 FTP 帳戶](ftp-and-sftp/ftp-delete.md)
   + [還原已刪除的 FTP 資料和 FTP 帳戶](ftp-and-sftp/ftp-restore.md)
   + [升級 Adobe FTP 伺服器](ftp-and-sftp/ftp-upgrade.md)
   + [使用被動式 FTP 模式](ftp-and-sftp/ftp-passive.md)
   + [FTP 處理時間](ftp-and-sftp/ftp-processing.md)
   + 安全檔案傳輸通訊協定 {#secure-file-transfer-protocol}
      + [SFTP 服務升級 - 常見問答集](ftp-and-sftp/c-sftp/sftp-upgrade.md)
      + [安全檔案傳輸通訊協定 - 概觀](ftp-and-sftp/c-sftp/ftp-sftp.md)
      + [使用 SFTP 連線至 Adobe FTP 帳戶](ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
      + [使用 SFTP 傳送 Adobe 資料至外部 FTP 帳戶](ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)
      + [傳送 Data Warehouse 請求至 SFTP 伺服器](ftp-and-sftp/c-sftp/ftp-sftp-dw.md)
      + [不使用密碼透過 SFTP 連線至 Adobe](ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
+ [Analysis Workspace 下載](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html)
+ [Adobe Analytics API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)
+ [Report Builder](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/report-builder/rb-overview)
