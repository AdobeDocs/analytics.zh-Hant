---
description: 從網站、行動應用程式收集或使用網站服務 API 或資料來源上傳的資料會儲存在 Adobe 的 Data Warehouse。這些原始點按流資料形成 Adobe Analytics 所使用的資料集。
keywords: 點按資料流；資料摘要；資料摘要；資料摘要
title: Analytics 資料摘要總覽
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 0916ef4ddc2ca65f01721f4d79d7af825dcf50e3
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 83%

---

# Analytics 資料摘要總覽

>[!AVAILABILITY]
>
>此頁面上說明的某些目的地型別處於版本的有限測試階段，可能尚未在您的環境中提供。 當該功能供一般用途時，此備註將被刪除。有關 Analytics 發佈流程的資訊，請參閱 [Adobe Analytics 功能發佈](/help/release-notes/releases.md)。

資料摘要是從 Adobe Analytics 中取得原始資料的有力方式。這類原始資料可用於 Adobe 以外的其他平台，供組織任意使用。資料會在每小時結束時以小時的批量傳送，或在每天結束時以當天的批量傳送。

## 先決條件

在使用資料摘要之前，請確認您符合下列所有需求。

* 可傳送資料至 Adobe 資料收集伺服器的有效實作。另請參閱 [驗證和發佈實作](/help/implement/launch/validate-publish-prod.md) （在實施指南中）。
* 您的帳戶為 Analytics 產品管理員，或者屬於具有資料摘要存取權的產品設定檔。
* 在Amazon S3、Google Cloud Platform、Azure RBAC或Azure SAS上設定的貯體。
* （舊版：舊版FTP和SFTP目的地型別僅需使用此功能）擁有可用的FTP站台和憑證（您的組織提供的FTP憑證）。

## 建議的資料摘要資源

1. 使用您的 Adobe ID 認證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
3. 從頂端導覽列中前導覽至管理員 > 資料摘要。
4. 按一下[!UICONTROL 「新增」]。隨後顯示的新頁面中包含三個主要類別: [!UICONTROL 摘要資訊]、[!UICONTROL 目的地]和[!UICONTROL 資料欄定義]。
5. 填寫[!UICONTROL 摘要資訊]欄位 。
   * 名稱: 任意所需名稱，例如「測試資料摘要」。
   * 報表套裝: 選取所需報表套裝。
   * 完成時收到通知的電子郵件: 請輸入您的電子郵件。
   * 摘要間隔: 選擇所需間隔 (每小時或每日)。
   * 延遲處理: 可保留為[!UICONTROL 無延遲]。
   * 開始和結束日期: 將數天前的日期選為開始日期，然後將今天設為結束日期。
6. 填寫[!UICONTROL 目的地]欄位。
   * 類型: FTP
   * 主機: 輸入所需 FTP 目的地 URL。例如, `ftp://ftp.omniture.com`。
   * 路徑: 可留空
   * 使用者名稱: 輸入要登入 FTP 網站的使用者名稱。
   * 密碼和確認密碼: 輸入要登入 FTP 網站的密碼。
7. 填寫[!UICONTROL 資料欄定義]。
   * 在下拉式清單中選取最新的「所有Adobe Columns」範本。
   * 壓縮格式: Gzip
   * 封裝類型: 多個檔案
   * 資訊清單: 無檔案
8. 按一下右上方的[!UICONTROL 儲存]。
9. 儲存後，歷史資料的處理程序就會開始。資料完成一天量的處理作業時，檔案會放在 FTP 網站上。
10. 請使用 Windows Explorer 或專用的 FTP 用戶端登入 FTP 網站。
11. 將壓縮的資料摘要檔案下載到您的本機電腦。
12. 使用可支援 `.tar.gz` 副檔名的程式來解壓縮壓縮檔案。
13. 按您的偏好在試算表或資料庫應用程式中開啟 `hit_data.tsv` 檔案，以便查看當天的原始資料。

## 下一步

瞭解取得資料摘要的基本工作流程後，您即可與組織內的團隊合作，將原始資料儲存或收錄至資料庫。

* [資料摘要最佳作法](/help/export/analytics-data-feed/data-feeds-best-practices.md)：建立和管理資料摘要的最佳作法。
* [建立資料摘要](create-feed.md)：建立資料摘要的技術詳細資訊，詳細說明個別欄位
* [管理資料摘要](df-manage-feeds.md)：深入了解如何導覽資料摘要介面
* [資料摘要內容](c-df-contents/datafeeds-contents.md)：了解壓縮檔案內容 <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [資料欄定義](c-df-contents/datafeeds-reference.md)：所有可用欄的完整清單.
* 資料摘要介面影片導覽:

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* 有關如何尋找您的資料摘要 ID 的影片：

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)