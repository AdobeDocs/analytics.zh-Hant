---
description: 「管理」裡報表套裝「一般帳戶設定」的欄位說明。
title: 一般帳戶設定
topic: Admin tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
translation-type: tm+mt
source-git-commit: d4ecb31e7a79546c97207772e9df3eb4d673c35f
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 89%

---


# 一般帳戶設定

「管理員」中報表套裝「一般帳戶設定」的欄位說明。

**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 一般帳戶設定」]**

這些設定包含基本報表套裝功能的編輯選項，例如名稱與時區。

| 選項 | 說明 |
|--- |--- |
| 網站標題 | 識別您的網站。請提供每個報表套裝唯一的網站標題。 |
| 基礎 URL | 指定報表套裝的主要網站。基本 URL 不會影響反向連結篩選。請改用[內部 URL 篩選器](/help/admin/admin/internal-url-filter-admin.md)。 |
| 時區 | 判斷與您的報告資料相關的日期和時間。變更動態報表套裝上的時區，會在報告資料中產生尖峰或間隙。為了降低影響，Adobe 建議在非尖峰時刻變更時區，以免出現資料偏差。例如，如果您在下午 3:00 將報表套裝時區從中部時間改為太平洋時間，則報表套裝的目前時間便會變為太平洋時間下午 1:00。由於報告已收集了 1:00 的資料，因此報告會在下午 1:00 至 3:00 之間顯示一段流量尖峰。此外，如果您在下午 3:00 將報表套裝時區從中部改為東部，則報表套裝的目前時間會變為東部下午 4:00。報告在變更時間的當天下午 3:00 至 4:00 之間，將不會顯示任何資料。 |
| 預設頁面 | 若您的[!UICONTROL 「最受歡迎頁面」]報表含有 URL 而非頁面名稱，此設定可防止多個 URL 代表同一頁面。例如，URL `https://example.com` 和 `https://example.com/index.html` 通常是指同一頁面。您可移除預設檔案名稱，使這兩個 URL 均顯示為 `https://example.com`。若保留為空白，則會從 URL 中移除下列檔案名稱：index.htm、index.html、index.cgi、index.asp、default.htm、default.html、default.cgi、default.asp、home.htm、home.html、home.cgi 與 home.asp。要完全停用檔案名稱移除，請輸入一個絕不會出現在 URL 中的值。 |
| 將 IP 位址的最後八位數字取代為 0 | 移除最後八位元是在點擊完成任何處理之前完成，包括在IP篩選／排除之前、在檢查機器人規則之前、在地域劃分查閱之前等。 因此，最後八位數字被 0 取代，而 IP 排除規則應更新為符合最後為零的 IP 位址。符合 * 應符合 0。例如，IP 位址 11.22.33.44 會變更為 11.22.33.0。地域劃分資料不會像使用整個 IP 位址一樣準確。具體來說，城市準確度會比國家或地區準確度受到更大的影響。機器人規則和 VISTA 規則都會受影響，因為它們無法使用整個 IP 位址。此外，基於 IP 的處理規則 (包括行銷管道規則和報表套裝處理規則) 也會受到此設定影響。 <br> **注意**：2019 年 1 月後，在倫敦資料中心新建的所有報表套裝都會預設啟用這項設定，但僅限啟用從 Admin Console 所列範本複製而來的報表套裝設定。若報表套裝的設定是複製自其他報表套裝，則會繼承所選報表套裝的所有設定。 |
| IP 模糊化 | 將 IP 位址轉變為無法辨識的字串，實際上是將其從 Adobe 資料儲存區中移除。啟用「IP 模糊化」後，原始的 IP 位址將會永久遺失。  <br> **注意**：Analytics 中每一處的 IP 位址都會模糊處理，包括 Data Warehouse。不過，Target 中的 IP 設定則另外控制，因此此設定不會影響 Target。<br> 如果啟用IP模糊化，則所有需要的處理（包括IP篩選／排除、機器人規則和地域劃分查閱）都會在IP位址模糊化之前完成。啟用IP模糊化時，您不需要變更任何項目。<ul><li>勾選&#x200B;**「停用」**&#x200B;會在資料中保留 IP 位址。</li><li>勾選「模糊化IP位址」會將IP變更為兩個冒號，後面接著雜湊值（例如`::1932023538`）。****</li><li>勾選&#x200B;**「移除 IP 位址」**`::X.X.X.X`，便會在地理查閱後，將資料中的 IP 位址更換為 </li></ul>**注意**：此設定要能正常運作，可能需要變更自訂[機器人規則](/help/admin/admin/bot-removal/bot-rules.md)或 [IP 排除](/help/admin/admin/exclude-ip.md)。 |
| 交易 ID 儲存 | 讓您能夠使用「[交易 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)」資料來源。 |
| 啟動 Ad Hoc Analysis | 指出在 Ad Hoc Analysis 是否將該報表套裝顯示為可用的報表套裝。使用此設定限制哪些報表套裝要顯示為 Ad Hoc Analysis 的選項。例如，您可停用 Ad Hoc Analysis 的開發和 QA 報表套裝。 |
| 啟用 Data Warehouse | 前往「Analytics > 工具 > Data Warehouse」底下啟用 Data Warehouse UI。 |
