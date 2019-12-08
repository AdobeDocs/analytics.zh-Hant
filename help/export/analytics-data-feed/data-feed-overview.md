---
description: 從網站、行動應用程式收集或使用網站服務 API 或資料來源上傳的資料會儲存在 Adobe 的 Data Warehouse。這些原始點按流資料形成 Adobe Analytics 所使用的資料集。
keywords: clickstream;data feed;datafeed;Data Feed
title: Analytics 資料摘要概觀
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Analytics 資料摘要概觀

資料饋送是從Adobe Analytics中取得原始資料的強大方式。 此原始資料可用於Adobe以外的其他平台，供貴組織自行決定使用。 資料會在每小時結束時以每小時批傳送，或在每天結束時以每日批傳送。

## 必備條件

在使用資料饋送之前，請確定您符合下列所有需求。

* FTP網站和認證方便使用。 資料饋送只能傳送至伺服器目的地。 您的組織通常會提供FTP認證。 Adobe可根據您的要求，提供FTP位置少量儲存空間。 請連絡客戶服務以要求資料饋送的FTP目的地。
* 傳送資料至Adobe資料收集伺服器的正常實作。 請參 [閱「實作使用指南」中的](../../implement/implement-with-launch/validate-publish-prod.md) 「在Launch中驗證和發佈實作」。
* 您的帳戶是Analytics產品管理員，或您的帳戶屬於具有資料饋送存取權的產品設定檔。

## 開始使用的步驟

1. 使用您的 Adobe ID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
3. 在頂端導覽列中，導覽至「管理&gt;資料饋送」。
4. 按一下[!UICONTROL 「新增」]。新頁面會出現，其中包含三個主要類別：摘 [!UICONTROL 要資訊]、 [!UICONTROL 目標]、 [!UICONTROL 資料欄定義]。
5. 填寫動態消 [!UICONTROL 息資訊欄] 。
   * 名稱：任何所需的名稱，例如「測試資料饋送」。
   * 報表套裝：選取所要的報表套裝。
   * 完成時以電子郵件寄送：輸入您的電子郵件。
   * 饋送間隔：選擇所需的間隔（每小時或每日）。
   * 延遲處理：可以保留為「 [!UICONTROL 無延遲」]。
   * 開始和結束日期：選擇數天前和今天的開始日期作為結束日期。
6. 填寫「目 [!UICONTROL 標] 」欄位。
   * 類型：FTP
   * 主機：輸入所要的FTP目標URL。 例如, `ftp://ftp.omniture.com`.
   * 路徑：可留空
   * 使用者名稱：輸入要登入FTP網站的使用者名稱。
   * 密碼和確認密碼：輸入登入FTP網站的密碼。
7. 填寫資 [!UICONTROL 料欄定義]。
   * 在下拉式清單中選取最新的「所有Adobe欄」範本。
   * 壓縮格式：Gzip
   * 封裝類型：多個檔案
   * 資訊清單：無檔案
8. 按一 [!UICONTROL 下右上] 方的「儲存」。
9. 儲存後，歷史資料處理就會開始。 當資料處理完成一天時，檔案會放在FTP網站上。
10. 使用Windows檔案總管或專用的FTP用戶端登入FTP網站。
11. 將壓縮的資料饋送檔案下載到您的本機電腦。
12. 使用支援副檔名的程式來解壓縮壓 `.tar.gz` 縮檔案。
13. 在您的試 `hit_data.tsv` 算表或資料庫應用程式中開啟檔案，以查看當天的原始資料。

## 下一步

瞭解取得資料饋送的基本工作流程後，即可與組織內的團隊合作，將原始資料儲存或收錄至資料庫。

* [建立資料饋送](create-feed.md):建立資料饋送的技術詳細資訊，詳細說明個別欄位
* [管理資料饋送](df-manage-feeds.md):進一步瞭解如何導覽資料饋送介面
* [資料饋送內容](c-df-contents/datafeeds-contents.md):瞭解壓縮檔案內容
* [資料欄定義](c-df-contents/datafeeds-reference.md):所有可用欄的完整清單

## 其他資源

視訊導覽資料饋送介面：

> [!VIDEO](https://www.youtube.com/watch?v=m_fb--gNtR4)
