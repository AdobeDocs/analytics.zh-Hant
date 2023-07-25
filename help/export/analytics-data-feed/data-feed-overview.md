---
description: 從網站、行動應用程式收集或使用網站服務 API 或資料來源上傳的資料會儲存在 Adobe 的 Data Warehouse。這些原始點按流資料形成 Adobe Analytics 所使用的資料集。
keywords: 點按資料流；資料摘要；資料摘要；資料摘要
title: Analytics 資料摘要總覽
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 84bdeb5d502e46c922fc5123fcdd5b6819426c0e
workflow-type: ht
source-wordcount: '314'
ht-degree: 100%

---

# Analytics 資料摘要總覽

資料摘要是從 Adobe Analytics 中取得原始資料的有力方式。這類原始資料可用於 Adobe 以外的其他平台，供組織任意使用。資料會在每小時結束時以小時的批量傳送，或在每天結束時以當天的批量傳送。

## 先決條件

在使用資料摘要之前，請確認您符合下列所有需求。

* 可傳送資料至 Adobe 資料收集伺服器的有效實作。請參閱實作指南中的[驗證和發佈實作](/help/implement/launch/validate-publish-prod.md)。
* 您的帳戶為 Analytics 產品管理員，或是您的帳戶屬於具有資料摘要存取權的產品設定檔。
* 在 Amazon S3、Google Cloud Platform、Azure RBAC 或 Azure SAS 上設定的貯體。
* (舊版：僅有舊版 FTP 和 SFTP 目標類型需要) 準備好 FTP 網站和認證 (由您組織提供的 FTP 認證。)

## 後續步驟

以下資源可幫助您了解取得資料摘要的基本工作流程。了解基本工作流程之後，您就可以與組織內的團隊合作，將原始資料儲存或收錄至資料庫。

* [資料摘要最佳實務](/help/export/analytics-data-feed/data-feeds-best-practices.md)：建立和管理資料摘要的最佳實務。
* [建立資料摘要](create-feed.md)：建立資料摘要的技術詳細資訊，詳細說明個別欄位
* [管理資料摘要](df-manage-feeds.md)：深入了解如何導覽資料摘要介面
* [資料摘要內容](c-df-contents/datafeeds-contents.md)：了解壓縮檔案內容 <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [資料欄定義](c-df-contents/datafeeds-reference.md)：所有可用欄的完整清單。
* 資料摘要介面影片導覽：

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* 有關如何尋找您的資料摘要 ID 的影片：

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)