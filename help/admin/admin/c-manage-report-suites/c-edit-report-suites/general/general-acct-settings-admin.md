---
description: 「管理」裡報表套裝「一般帳戶設定」的欄位說明。
title: 一般帳戶設定
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 83%

---

# 一般帳戶設定

「管理員」中報表套裝「一般帳戶設定」的欄位說明。

**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 一般帳戶設定」]**

這些設定包含基本報表套裝功能的編輯選項，例如名稱與時區。


>[!BEGINSHADEBOX]

檢視![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [設定一般帳戶設定](https://video.tv.adobe.com/v/332330/?quality=12&learn=on){target="_blank"}以取得示範影片。

>[!ENDSHADEBOX]

| 選項 | 說明 |
|--- |--- |
| 網站標題 | 識別您的網站。請提供每個報表套裝唯一的網站標題。 |
| 基礎 URL | 指定報表套裝的主要網站。基本 URL 不會影響反向連結篩選。請改用[內部URL篩選器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。 |
| 時區 | 判斷與您的報告資料相關的日期和時間。變更動態報表套裝上的時區，會在報告資料中產生尖峰或間隙。為了降低影響，Adobe 建議在非尖峰時刻變更時區，以免出現資料偏差。例如，如果您在下午 3:00 將報表套裝時區從中部時間改為太平洋時間，則報表套裝的目前時間便會變為太平洋時間下午 1:00。由於報告已收集了 1:00 的資料，因此報告會在下午 1:00 至 3:00 之間顯示一段流量尖峰。此外，如果您在下午 3:00 將報表套裝時區從中部改為東部，則報表套裝的目前時間會變為東部下午 4:00。報告在變更時間的當天下午 3:00 至 4:00 之間，將不會顯示任何資料。 |
| 預設頁面 | 若您的[!UICONTROL 「最受歡迎頁面」]報表含有 URL 而非頁面名稱，此設定可防止多個 URL 代表同一頁面。例如，URL `https://example.com` 和 `https://example.com/index.html` 通常是指同一頁面。您可移除預設檔案名稱，使這兩個 URL 均顯示為 `https://example.com`。若保留為空白，則會從 URL 中移除下列檔案名稱：index.htm、index.html、index.cgi、index.asp、default.htm、default.html、default.cgi、default.asp、home.htm、home.html、home.cgi 與 home.asp。要完全停用檔案名稱移除，請輸入一個絕不會出現在 URL 中的值。 |
| 將 IP 位址的最後八位數字取代為 0 | 啟用時，會將IP位址的最後八位數字取代為零。 地理相關報表在填入前就會發生這種情況，因此可能影響這些報表的準確性。 |
| IP 模糊化 | 將 IP 位址轉變為無法辨識的字串，實際上是將其從 Adobe 資料儲存區中移除。啟用「IP模糊化」後，原始IP位址會永久遺失。<br> **注意**：Analytics 中每一處的 IP 位址都會模糊處理，包括 Data Warehouse。不過，Target 中的 IP 設定則另外控制，因此此設定不會影響 Target。<br>如果啟用 IP 模糊化功能，所有必需進行的處理 (包括 IP 篩選/排除、機器人規則和地域劃分查詢) 會在模糊化 IP 地址之前完成。 啟用 IP 模糊化功能時無需變更任何內容。<ul><li>勾選&#x200B;**「停用」**&#x200B;會在資料中保留 IP 位址。</li><li>查看&#x200B;**模糊化 IP 位址**&#x200B;將 IP 變更為兩個冒號後列有雜湊值 (例如，`::1932023538`)。</li><li>勾選&#x200B;**「移除 IP 位址」**`::X.X.X.X`，便會在地理查閱後，將資料中的 IP 位址更換為 </li></ul>**注意**：此設定可能需要變更自訂[機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)或[IP排除](/help/admin/admin/exclude-ip.md)。<br> **注意**：使用網頁SDK收集的資料可以透過[資料流設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hant#@advanced-options)在Edge Network套用IP模糊化。 如果對Edge Network套用IP模糊化，則到達Analytics時就已經經過模糊化。 此模糊化會影響機器人規則和地理查閱。 |
| 交易 ID 儲存 | 讓您能夠使用「[交易 ID](/help/import/data-sources/transactionid.md)」資料來源。 |
| 啟用 Data Warehouse | 前往「Analytics > 工具 > Data Warehouse」底下啟用 Data Warehouse UI。 |
| 郵遞區號選項 | 讓您指定郵遞區號，而不是使用由我們的地理 IP 查詢產生的任何內容。 |
| 多位元組字元支援 | 多位元組字元支援可使用 UTF-8 儲存報告套裝中的字元。系統收到報告時就會將您網頁資料的字元集轉換為 UTF-8 字元集，因此您可以在行銷報告中使用任何語言。聯絡您的 Adobe 帳戶團隊或客戶服務，以變更現有報告套裝的多位元組字元支援。 |
| 已啟用 | 指定是否啟用此報表套裝。 |
| 基本貨幣 | 允許您為此報表套裝指定基本[貨幣](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/currencycode.html?lang=zh-Hant)。 |
| 組織 ID | 與您佈建的 Experience Cloud 公司相關聯的 ID。 此 ID 是 24 個字元的英數字串，後面接著 (而且必須包含) @AdobeOrg。 |
