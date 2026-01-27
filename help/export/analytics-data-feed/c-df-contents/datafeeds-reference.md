---
description: 說明資料摘要中欄的表格資料。
keywords: 資料摘要；欄
subtopic: data feeds
title: 資料欄參考
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '3690'
ht-degree: 100%

---

# 資料欄參考

參閱本頁內容，了解各欄包含哪些資料。大部分實施不會用到每一欄，因此在決定要將哪些欄包含在資料摘要匯出中時，可參考此頁面。

>[!IMPORTANT]
>
>對於所有欄位 (例如定義為 255 個字元的欄位)，資料摘要可能會因為字串中多了字元逸出值而傳送額外的字元。如果您的實施經常會傳送超過字元限制的值，請注意可能是這些可能的額外字元所致。

## 欄、說明和資料類型

>[!NOTE]
>
>大多數欄包含類似的欄，其前置詞為 `post_`。後置欄包含伺服器端邏輯、處理規則和 VISTA 規則之後的值。Adobe 建議在大多數情況下使用後置欄。如需詳細資訊，請參閱[資料摘要常見問題](../df-faq.md)。

此表格先前的更新內容可在本頁面的 [GitHub 提交歷史記錄](https://github.com/AdobeDocs/analytics.zh-Hant/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)中找到。

| 欄名稱 | 欄說明 | 資料類型 |
| --- | --- | --- |
| **`accept_language`** | 列出所有接受的語言，如影像要求中的 Accept-Language HTTP 標頭所示。 | char(20) |
| **`adload`** | 媒體廣告載入 | varchar(255) |
| **`aemassetid`** | 對應於一組 Adobe Experience Manager Assets 的資產 ID (GUID) 的多值變數。增加曝光事件。 | text |
| **`aemassetsource`** | 確認資產事件的來源。用於 Adobe Experience Manager。 | varchar(255) |
| **`aemclickedassetid`** | Adobe Experience Manager 資產的資產 ID。增加點按事件。 | varchar(255) |
| **`browser`** | 代表瀏覽器的數值 ID。請參考`browser.tsv`查詢表。 | int unsigned |
| **`browser_height`** | [瀏覽器高度](/help/components/dimensions/browser-height.md)維度。 | smallint unsigned |
| **`browser_width`** | [瀏覽器寬度](/help/components/dimensions/browser-width.md) | smallint unsigned |
| **`c_color`** | 調色盤的位元深度。用於計算[色階](/help/components/dimensions/color-depth.md)維度的一部分。AppMeasurement 使用 JavaScript 函數`screen.colorDepth()`。 | char(20) |
| **`campaign`** | [追蹤程式碼](/help/components/dimensions/tracking-code.md)維度。 | varchar(255) |
| **`carrier`** | Adobe Advertising 整合變數。指定行動電信業者。`carrier.tsv` [動態查詢](dynamic-lookups.md)的索引鍵值。 | varchar(100) |
| **`ch_hdr`** | 透過 HTTP 請求標頭收集的用戶端提示。 | text |
| **`ch_js`** | 透過使用者代理用戶端提示 JavaScript API 收集的用戶端提示。 | text |
| **`channel`** | [網站區段](/help/components/dimensions/site-section.md)維度。 | varchar(100) |
| **`clickmaplink`** | Activity Map 連結 | varchar(255) |
| **`clickmaplinkbyregion`** | Activity Map 連結 (依地區) | varchar(255) |
| **`clickmappage`** | Activity Map 頁面 | varchar(255) |
| **`clickmapregion`** | Activity Map 地區 | varchar(255) |
| **`code_ver`** | 用於編譯及傳送影像要求的 API 或客戶端 SDK 版本。 | char(16) |
| **`color`** | 以`c_color`欄的值為基礎的色階 ID。請參考`color_depth.tsv`查詢表。 | smallint unsigned |
| **`connection_type`** | 代表連線類型的數值 ID。[連線類型](/help/components/dimensions/connection-type.md)維度。請參考`connection_type.tsv`查詢表。 | tinyint unsigned |
| **`cookies`** | [Cookie 支援](/help/components/dimensions/cookie-support.md)維度。<br>Y：啟用<br>N：停用<br>U：未知 | char(1) |
| **`country`** | 代表訪客所屬國家的數值 ID。請參考`country.tsv`查詢表。 | smallint unsigned |
| **`ct_connect_type`** | 和`connection_type`欄相關。最常見的值是 LAN/Wifi、行動電信業者和數據機。 | char(20) |
| **`curr_factor`** | 決定貨幣的小數位數，並用於貨幣轉換。例如，美元使用兩位小數，因此此欄的值為 `2`。 | tinyint |
| **`curr_rate`** | 交易發生時的匯率。Adobe 與 XE 合作，以確定當日的匯率。 | decimal(24,12) |
| **`currency`** | 交易期間使用的貨幣代碼。使用 [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) 設定。 | char(8) |
| **`cust_hit_time_gmt`** | 僅限啟用時間戳記的報告套裝。時間戳記根據 UNIX® 時間隨點擊傳送。 | int |
| **`cust_visid`** | 自訂的訪客 ID，如果使用 [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 設定。 | varchar(255) |
| **`customer_perspective`** | 判斷該點擊是否為行動裝置背景點擊。如需更多資訊，請參閱[情境感知工作階段](/help/components/vrs/vrs-mobile-visit-processing.md)。 | tinyint unsigned |
| **`daily_visitor`** | 一個標幟，用來判斷該點擊是否為新的每日訪客。 | tinyint unsigned |
| **`dataprivacyconsentoptin`** | [同意管理選擇加入](/help/components/dimensions/cm-opt-in.md)維度。每個點擊可以有多個值，以垂直號 (`\|`) 分隔。有效值包括 `DMP` 和 `SELL`。 | varchar(100) |
| **`dataprivacyconsentoptout`** | [同意管理選擇退出](/help/components/dimensions/cm-opt-out.md)維度。每個點擊可以有多個值，以垂直號 (`\|`) 分隔。有效值包括 `SSF`、`DMP` 和 `SELL`。 | varchar(100) |
| **`dataprivacydmaconsent`** | 用來識別是否已獲得同意的一個值，確認同意將來自 Adobe Analytics 的資料透過 Adobe Advertising 發送給第三方廣告提供商 (如 Google)。如需詳細資訊，請參閱[廣告同意](/help/components/dimensions/ad-consent.md)。 | varchar(100) |
| **`date_time`** | 可讀格式的點擊時間，根據報告套裝的時區而定。 | 日期時間 |
| **`domain`** | [網域](/help/components/dimensions/domain.md)維度。根據訪客的網路存取點。 | varchar(100) |
| **`duplicate_events`** | 列出每個被視為重複的事件。 | varchar(255) |
| **`duplicate_purchase`** | 一個標幟，用來判斷此點擊的購買事件是否因為重複而被忽略。 | tinyint unsigned |
| **`duplicated_from`** | 僅用於包含點擊複製 VISTA 規則的報告套裝。指出從中複製點擊的報告套裝。 | varchar(40) |
| **`ef_id`** | `ef_id`用於 Adobe Advertising 整合。 | varchar(255) |
| **`evar1 - evar250`** | 自訂變數 1-250。用於[eVar](/help/components/dimensions/evar.md)維度。每個組織使用 eVar 的方式不同。有關您的組織如何填入各自 eVar 的更多資訊，最佳參考來源是您組織特定的[解決方案設計文件](/help/implement/prepare/solution-design.md)。 | varchar(255) |
| **`event_list`** | 用逗號分隔的數值 ID 列表，代表在該點擊上觸發的事件。包含預設事件和[自訂事件 1-1000](/help/components/metrics/custom-events.md)。使用`event.tsv`查詢。 | text |
| **`exclude_hit`** | 一個標幟，用來判斷該點擊是否被排除在報告之外。此`visit_num`欄不會因排除的點擊而遞增。<br>1：未使用。屬於已報廢功能。<br>2：未使用。屬於已報廢功能。<br>3：已不再使用。用戶代理排除<br>4：依據 IP 位址的排除<br>5：遺失重要點擊資訊，例如`page_url`、`pagename`、`page_event`、或者`event_list`<br>6：JavaScript 沒有正確處理點擊<br>7：特定帳戶的排除，例如在 Vista 規則中<br>8：未使用。替代帳戶特定排除。<br>9：未使用。屬於已報廢功能。<br>10：無效的貨幣代碼<br>11：僅時間戳記報告套裝上遺失時間戳記的點擊，或非時間戳記報告套裝上包含時間戳記的點擊<br>12：未使用。屬於已報廢功能。<br>13：未使用。屬於已報廢功能。<br>14：不符合 Analytics 點擊的 Target 點擊<br>15：目前未使用。<br>16：不符合 Analytics 點擊的 Advertising Cloud 點擊 | tinyint unsigned |
| **`first_hit_page_url`** | 訪客的第一個 URL。 | varchar(255) |
| **`first_hit_pagename`** | [原始進入頁面](/help/components/dimensions/entry-dimensions.md)維度。訪客的原始進入頁面名稱。 | varchar(100) |
| **`first_hit_ref_domain`** | [原始反向連結網域](/help/components/dimensions/original-referring-domain.md)維度。根據`first_hit_referrer`而定。訪客的第一個反向連結網域。 | varchar(100) |
| **`first_hit_ref_type`** | 代表訪客接觸的第一個反向連結之類型的數值 ID。請參考`referrer_type.tsv`查詢表。 | tinyint unsigned |
| **`first_hit_referrer`** | 訪客的第一個反向連結 URL。 | varchar(255) |
| **`first_hit_time_gmt`** | 訪客初次點擊的時間戳記 (根據 UNIX® 時間)。 | int |
| **`geo_city`** | 點擊的來源城市名稱，以 IP 為準。用於[城市](/help/components/dimensions/cities.md)維度。 | char(32) |
| **`geo_country`** | 點擊的來源國家/地區縮寫，以 IP 為準。用於[國家/地區](/help/components/dimensions/countries.md)維度。 | char(4) |
| **`geo_dma`** | 點擊的來源人口統計區域的數值 ID，以 IP 為準。用於 [美國 DMA](/help/components/dimensions/us-dma.md) 維度。 | int unsigned |
| **`geo_region`** | 點擊的來源州或地區名稱，以 IP 為準。用於[地區](/help/components/dimensions/regions.md)維度。 | char(32) |
| **`geo_zip`** | 點擊來源的郵遞區號 (根據 IP 位址)。協助填入[郵遞區號](/help/components/dimensions/zip-code.md)維度。另請參閱`zip`。 | varchar(16) |
| **`hit_source`** | 該點擊的來源。點擊來源 1、2 和 6 需計費。<br>1：沒有時間戳記的標準影像要求<br>2：具有時間戳記的標準影像要求<br>3：具有時間戳記的即時資料來源上傳<br>4：未使用<br>5：通用資料來源上傳<br>6：完整處理資料來源上傳<br>7：TransactionID 資料來源上傳<br>8：不再使用；舊版 Adobe Advertising Cloud 資料來源 <br>9：已不再使用；Adobe Social 摘要量度<br>10：使用 Audience Manager 伺服器端轉送 | tinyint unsigned |
| **`hit_time_gmt`** | Adobe 資料收集伺服器收到點擊的時間戳記 (根據 UNIX® 時間)。 | int |
| **`hitid_high`** | 搭配 `hitid_low` 使用來識別點擊。 | bigint unsigned |
| **`hitid_low`** | 搭配 `hitid_high` 使用來識別點擊。 | bigint unsigned |
| **`hourly_visitor`** | 一個標幟，用來判斷該點擊是否來自新的每小時訪客。 | tinyint unsigned |
| **`ip`** | IPv4 位址，根據影像請求 HTTP 標頭。與 `ipv6` 互斥；如果此欄包含非模糊 IP 位址，`ipv6` 為空白。 | char(20) |
| **`ipv6`** | 壓縮的 IPv6 位址 (若有)。與 `ip` 互斥；如果此欄包含非模糊 IP 位址，`ip` 為空白。 | varchar(40) |
| **`j_jscript`** | 瀏覽器支援的 JavaScript 版本。 | char(5) |
| **`java_enabled`** | [[!UICONTROL Java 已啟用]](/help/components/dimensions/java-enabled.md)。<br>Y：啟用 <br>N：停用 <br>U：未知 | char(1) |
| **`javascript`** | JavaScript 版的查詢 ID，以 `j_jscript` 為依據。請參考`javascript_version`查詢表。 | tinyint unsigned |
| **`language`** | 代表訪客語言的數值 ID。請參考`languages.tsv`查詢表。 | smallint unsigned |
| **`last_hit_time_gmt`** | 先前點擊的時間戳記 (根據 UNIX® 時間)。用於計算[[!UICONTROL 和上次造訪間隔天數]](/help/components/dimensions/days-since-last-visit.md)維度。 | int |
| **`last_purchase_num`** | [客戶忠誠度](/help/components/dimensions/customer-loyalty.md)維度。訪客之前已購買的次數。<br>0：沒有先前購買 (非客戶) <br>1：先前購買 1 次 (新客戶) <br>2：先前購買 2 次 (回頭客戶) <br>3：先前購買 3 次以上 (忠實客戶) | int unsigned |
| **`last_purchase_time_gmt`** | 用於[[!UICONTROL 和上次購買間隔天數]](/help/components/dimensions/days-since-last-purchase.md)維度。上次進行購買的時間戳記 (根據 UNIX® 時間)。對於首次購買和之前未購買的訪客，此值為 `0`。 | int |
| **`latlon1`** | 位置 (10 公里以內) | varchar(255) |
| **`latlon23`** | 位置 (100 公尺以內) | varchar(255) |
| **`latlon45`** | 位置 (1 公尺以內) | varchar(255) |
| **`mc_audiences`** | 訪客所屬的 Audience Manager 區段 ID 清單。`post_mc_audiences` 欄會將分隔符號變更為 `--**--`。 | text |
| **`mcvisid`** | Experience Cloud 訪客 ID。由兩個連接的 64 位數組成，並填入至 19 位的 128 位數。 | varchar(255) |
| **`mobile_id`** | 如果使用者使用行動裝置，則為裝置的數值 ID。`mobile_attributes.tsv` [動態查詢](dynamic-lookups.md)的索引鍵值。 | int |
| **`mobileaction`** | 行動動作。在行動裝置實施中呼叫 `trackAction` 時自動收集。允許應用程式中的自動動作路徑。 | varchar(100) |
| **`mobileappid`** | 行動應用程式 ID。以下列格式儲存應用程式名稱和版本：`[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | 用於 Apteligent 資料連接器。Apteligent 中使用的應用程式 ID。 | varchar(255) |
| **`mobileappperformancecrashid`** | 用於 Apteligent 資料連接器。Apteligent 中使用的當機 ID。 | varchar(255) |
| **`mobileappstoreobjectid`** | 用於 [!DNL Appfigures] 資料連接器。應用程式商店物件 ID。 | varchar(255) |
| **`mobilebeaconmajor`** | 行動服務主要信標 | varchar(100) |
| **`mobilebeaconminor`** | 行動服務次要信標 | varchar(100) |
| **`mobilebeaconproximity`** | 行動服務鄰近地區信標 | varchar(255) |
| **`mobilebeaconuuid`** | 行動服務信標 UUID | varchar(100) |
| **`mobilecampaigncontent`** | 顯示連結之內容的名稱或 ID。由「行動應用程式贏取」填入。 | varchar(255) |
| **`mobilecampaignmedium`** | 行銷媒體，例如橫幅或電子郵件。由「行動應用程式贏取」填入。 | varchar(255) |
| **`mobilecampaignname`** | 行銷活動名稱，亦儲存於行銷活動變數中。由「行動應用程式贏取」填入。 | varchar(255) |
| **`mobilecampaignsource`** | 原始反向連結，例如電子報或社交媒體網路。由「行動應用程式贏取」填入。 | varchar(255) |
| **`mobilecampaignterm`** | 您要對此贏取追蹤的付費關鍵字或其他詞語。由「行動應用程式贏取」填入。 | varchar(255) |
| **`mobiledayofweek`** | 應用程式啟動的工作日數。 | varchar(255) |
| **`mobiledayssincefirstuse`** | 自應用程式初次執行以來的天數。 | varchar(255) |
| **`mobiledayssincelastuse`** | 自應用程式上次執行以來的天數。 | varchar(255) |
| **`mobiledeeplinkid`** | 從內容資料變數`a.deeplink.id`中收集。用於贏取報表中，作為行動贏取連結的識別碼。 | varchar(255) |
| **`mobiledevice`** | 行動裝置名稱。在 iOS 上，儲存為以逗號分隔的兩碼字串。第一個數字代表裝置世代，第二個數字代表裝置系列。 | varchar(255) |
| **`mobilehourofday`** | 定義一天當中啟動應用程式的時段。請依照 24 小時數字格式。 | varchar(255) |
| **`mobileinstalldate`** | Mobile 安裝日期。提供使用者初次開啟行動應用程式的日期。 | varchar(255) |
| **`mobilelaunchnumber`** | 每次啟動行動應用程式時增加 1。 | varchar(255) |
| **`mobilemessagebuttonname`** | 從內容資料變數`a.message.button.id`中收集。用於應用程式內傳訊，以識別關閉訊息的按鈕。 | varchar(100) |
| **`mobilemessageid`** | 應用程式內訊息 ID | varchar(255) |
| **`mobilemessageonline`** | 線上應用程式內訊息 | varchar(255) |
| **`mobilemessagepushoptin`** | 從內容資料變數`a.push.optin`中收集。當使用者選擇加入推播訊息時，設為「true」；否則，值為「false」。 | varchar(255) |
| **`mobilemessagepushpayloadid`** | 從內容資料變數`a.push.payloadid`中收集。用於推播訊息中，作為裝載識別碼。 | varchar(255) |
| **`mobileosversion`** | 行動服務作業系統版本 | varchar(255) |
| **`mobileplaceaccuracy`** | 從內容資料變數`a.loc.acc`中收集。指出 GPS 在採集時的準確度 (以公尺為單位)。 | varchar(255) |
| **`mobileplacecategory`** | 從內容資料變數`a.loc.category`中收集。說明特定位置的類別。 | varchar(255) |
| **`mobileplaceid`** | 從內容資料變數`a.loc.id`中收集。指定興趣點的識別碼。 | varchar(255) |
| **`mobilepushoptin`** | 行動服務推送選擇加入 | varchar(255) |
| **`mobilepushpayloadid`** | Mobile Services 推送承載 ID | varchar(255) |
| **`mobilerelaunchcampaigncontent`** | 行動服務上市內容 | varchar(255) |
| **`mobilerelaunchcampaignmedium`** | 行動服務上市媒體 | varchar(255) |
| **`mobilerelaunchcampaignsource`** | 行動服務上市來源 | varchar(255) |
| **`mobilerelaunchcampaignterm`** | 行動服務上市條件 | varchar(255) |
| **`mobilerelaunchcampaigntrackingcode`** | 從內容資料變數`a.launch.campaign.trackingcode`中收集。用於贏取中，作為上市促銷活動的追蹤代碼。 | varchar(255) |
| **`mobileresolution`** | 行動裝置的解析度。`[Width] x [Height]` 像素。 | varchar(255) |
| **`monthly_visitor`** | 一個標幟，用來判斷該點擊是否為當月的不重複訪客。 | tinyint unsigned |
| **`mvvar1`** - `mvvar3` | [清單變數](/help/implement/vars/page-vars/list.md)值。根據實施包含使用分隔符號的自訂值清單。`post_mvvar1` - `post_mvvar3` 欄會以 `--**--` 取代原始的分隔符號。 | text |
| **`mvvar1_instances`** - `mvvar3_instances` | 在目前點擊上設定的清單變數值。以 `--**--` 取代原始的分隔符號。`post` 欄位通常不包含資料。 | text |
| **`new_visit`** | 一個標幟，用來判斷目前的點擊是否為新造訪。在造訪閒置長達 30 分鐘後，由 Adobe 設定此值。 | tinyint unsigned |
| **`os`** | 代表訪客作業系統的數值 ID。依據 `user_agent` 欄而定。`operating_system.tsv`標準查詢和`operating_system_type.tsv`[動態查詢](dynamic-lookups.md)的索引鍵值。 | int unsigned |
| **`page_event`** | 影像要求中傳送的點擊類型 (標準點擊、下載連結、自訂連結、退出連結)。請參閱[頁面事件查閱](datafeeds-page-event.md)。 | tinyint unsigned |
| **`page_event_var1`** | 僅用於連結追蹤影像要求。所點按的下載連結、退出連結或自訂連結的 URL。 | text |
| **`page_event_var2`** | 僅用於連結追蹤影像要求。連結的自訂名稱 (若有指定)。依據 `page_event` 中的值，設定[自訂連結](/help/components/dimensions/custom-link.md)、[下載連結](/help/components/dimensions/download-link.md)或[退出連結](/help/components/dimensions/exit-link.md)。 | varchar(100) |
| **`page_type`** | [找不到的頁面](/help/components/dimensions/pages-not-found.md)維度，通常用於 404 頁面。 | char(20) |
| **`page_url`** | 點擊的 URL。請注意，`post_page_url` 在連結追蹤影像要求 ([`tl()`](/help/implement/vars/functions/tl-method.md)) 中被剔除，並使用 varchar(255) 的資料類型。 | text |
| **`pagename`** | [頁面](/help/components/dimensions/page.md)維度。如果[`pagename`](/help/implement/vars/page-vars/pagename.md)變數為空白，Analytics 會改用`page_url`。 | varchar(100) |
| **`pagename_no_url`** | 與 `pagename` 類似，但不會回復到 `page_url`。只有 `post` 列適用。 | varchar(100) |
| **`paid_search`** | 一個標幟，用來判斷該點擊是否符合付費搜尋偵測。 | tinyint unsigned |
| **`persistent_cookie`** | 用於[持續性 Cookie 支援](/help/components/dimensions/persistent-cookie-support.md)維度。指示訪客是否支援不會在每次點擊後被捨棄的 cookie。 | char(1) |
| **`pointofinterest`** | 行動服務興趣點名稱 | varchar(255) |
| **`pointofinterestdistance`** | 行動服務與興趣點中心的距離 | varchar(255) |
| **`post_`**&#x200B;欄 | 包含最終在報告中使用的值。每個後置欄會在伺服器端邏輯、處理規則和 VISTA 規則之後填入。Adobe 建議在大多數情況下使用後置欄。 | 請參閱各個非後置欄 |
| **`product_list`** | [`products`](/help/implement/vars/page-vars/products.md) 頁面變數。幫助填入多個維度和量度，包括[類別](/help/components/dimensions/category.md)、[產品](/help/components/dimensions/product.md)、[單位](/help/components/metrics/units.md)和[收入](/help/components/metrics/revenue.md)。 | text |
| **`prop1`** - `prop75` | 自訂流量變數 1 - 75。用於 [Prop](/help/components/dimensions/prop.md) 維度。 | varchar(100) |
| **`purchaseid`** | 使用[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)變數設定之購買的唯一識別碼。由`duplicate_purchase`欄使用。 | char(20) |
| **`quarterly_visitor`** | 一個標幟，用來判斷該點擊是否為每季的新訪客。 | tinyint unsigned |
| **`ref_domain`** | [反向連結網域](/help/components/dimensions/referring-domain.md)維度。依據 `referrer` 欄而定。 | varchar(100) |
| **`ref_type`** | 代表點擊的反向連結類型的數值 ID。用於[反向連結類型](/help/components/dimensions/referrer-type.md)維度。 <p>1：在您的網站內</p><p>2：其他網站</p> <p>3：搜尋引擎</p> <p>4：硬碟</p> <p>5：USENET</p> <p>6：已輸入/已建立書籤 (無反向連結)</p> <p>7：電子郵件</p> <p>8：無 JavaScript</p> <p>9：社交網路</p><p>10：對話式 AI 工具</p> | tinyint unsigned |
| **`referrer`** | [反向連結](/help/components/dimensions/referrer.md)維度。請注意，雖然 `referrer` 使用 varchar(255) 資料類型，但 `post_referrer` 是使用 varchar(244) 資料類型。 | varchar(255) |
| **`resolution`** | 代表螢幕解析度的數值 ID。用於[螢幕解析度](/help/components/dimensions/monitor-resolution.md)維度。使用`resolution.tsv`查詢表。 | smallint unsigned |
| **`s_kwcid`** | 用於 Adobe Advertising 整合的關鍵字 ID。 | varchar(255) |
| **`s_resolution`** | 原始螢幕解析度值。使用 JavaScript 函數`screen.width x screen.height`收集。 | char(20) |
| **`search_engine`** | 代表將訪客反向連結至您的網站的搜尋引擎的數值 ID。用於[搜尋引擎](/help/components/dimensions/search-engine.md)維度。請參考`search_engines.tsv`查詢表。 | smallint unsigned |
| **`search_page_num`** | 由[所有搜尋頁面排名](/help/components/dimensions/all-search-page-rank.md)維度使用。在使用者點進您的網站之前，指示您的網站要顯示哪個搜尋結果頁面。 | smallint unsigned |
| **`secondary_hit`** | 一個標幟，用來判斷該點擊是否為次要點擊。這個標幟通常來自多套裝標記和複製點擊的 VISTA 規則。 | tinyint unsigned |
| **`sourceid`** | 來源 ID | int unsigned |
| **`state`** | 狀態變數。 | varchar(50) |
| **`stats_server`** | 未使用。處理點擊的 Adobe 內部伺服器。 | char(30) |
| **`t_time_info`** | 訪客的當地時間。格式為：`M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | 用於 Adobe Target 整合。 代表目前符合條件的所有測試。 格式為：`TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`。 | text |
| **`tnt_action`** | 用於 Adobe Target 整合。 代表點擊合格的所有測試。 | text |
| **`tnt_instances`** | 用於 Adobe Target 整合。 Target 執行個體變數。 | text |
| **`transactionid`** | 唯一識別碼，日後可透過資料來源上傳各種資料點。使用[`transactionID`](/help/implement/vars/page-vars/transactionid.md)變數收集。 | text |
| **`truncated_hit`** | 一個標幟，表示影像要求已被截斷。表示已收到部分點擊。<br>Y：點擊遭截斷；收到部分點擊 <br>N：點擊未截斷；收到完整點擊 | char(1) |
| **`user_agent`** | 在影像要求的 HTTP 標頭中發送的使用者代理字串。 | text |
| **`user_hash`** | 未使用。報告套裝 ID 上的雜湊.請改用 `username`。 | int unsigned |
| **`user_server`** | 用於[伺服器](/help/components/dimensions/server.md)維度。 | varchar(100) |
| **`userid`** | 未使用。報告套裝 ID 的數值 ID。請改用 `username`。 | int unsigned |
| **`username`** | 點擊的報告套裝 ID。 | char(40) |
| **`va_closer_detail`** | [最後接觸詳情](/help/components/dimensions/last-touch-detail.md)維度。 | varchar(255) |
| **`va_closer_id`** | 識別[最後接觸管道](/help/components/dimensions/last-touch-channel.md)維度的數值 ID。此 ID 的查詢可以在行銷管道管理員中找到。 | tinyint unsigned |
| **`va_finder_detail`** | [首次接觸詳情](/help/components/dimensions/first-touch-detail.md)維度。 | varchar(255) |
| **`va_finder_id`** | 識別[首次接觸管道](/help/components/dimensions/first-touch-channel.md)維度的數值 ID。此 ID 的查詢可以在行銷管道管理員中找到。 | tinyint unsigned |
| **`va_instance_event`** | 用來識別行銷管道[實例](/help/components/metrics/instances.md)的標幟。 | tinyint unsigned |
| **`va_new_engagement`** | 用來識別行銷管道[新參與度](/help/components/metrics/new-engagements.md)的標幟。 | tinyint unsigned |
| **`video`** | 串流媒體服務維度[內容](/help/components/dimensions/sm-core.md)。 | varchar(255) |
| **`videoad`** | 串流媒體服務維度[廣告](/help/components/dimensions/sm-ads.md)。 | varchar(255) |
| **`videoadinpod`** | 串流媒體服務維度[廣告在 Pod 位置](/help/components/dimensions/sm-ads.md)。 | varchar(255) |
| **`videoadlength`** | 串流媒體服務維度[廣告長度 (變數)](/help/components/dimensions/sm-ads.md)。 | integer |
| **`videoadload`** | 串流媒體服務維度[廣告載入](/help/components/dimensions/sm-ads.md)。 | varchar(255) |
| **`videoadname`** | 串流媒體服務維度[廣告名稱 (變數)](/help/components/dimensions/sm-ads.md)。 | varchar(255) |
| **`videoadplayername`** | 串流媒體服務維度[廣告播放器名稱](/help/components/dimensions/sm-ads.md)。 | varchar(255) |
| **`videoadpod`** | 串流媒體服務維度[廣告 Pod](/help/components/dimensions/sm-ads.md)。 | varchar(255) |
| **`videoadvertiser`** | 串流媒體服務維度[廣告商](/help/components/dimensions/sm-ads.md)。 | varchar(255) |
| **`videoaudioalbum`** | 串流媒體服務維度[相簿](/help/components/dimensions/sm-audio-metadata.md)。 | varchar(255) |
| **`videoaudioartist`** | 串流媒體服務維度[藝人](/help/components/dimensions/sm-audio-metadata.md)。 | varchar(255) |
| **`videoaudioauthor`** | 串流媒體服務維度[作者](/help/components/dimensions/sm-audio-metadata.md)。 | varchar(255) |
| **`videoaudiolabel`** | 串流媒體服務維度[標籤](/help/components/dimensions/sm-audio-metadata.md)。 | varchar(255) |
| **`videoaudiopublisher`** | 串流媒體服務維度[發行者](/help/components/dimensions/sm-audio-metadata.md)。 | varchar(255) |
| **`videoaudiostation`** | 串流媒體服務維度[電台](/help/components/dimensions/sm-audio-metadata.md)。 | varchar(255) |
| **`videocampaign`** | 串流媒體服務維度[行銷活動 ID](/help/components/dimensions/sm-ads.md)。 | varchar(255) |
| **`videochannel`** | 串流媒體服務維度[內容頻道](/help/components/dimensions/sm-core.md)。 | varchar(255) |
| **`videochapter`** | 串流媒體服務維度[章節](/help/components/dimensions/sm-chapters.md)。 | varchar(255) |
| **`videocontenttype`** | 串流媒體服務維度[內容類型](/help/components/dimensions/sm-core.md)。 | varchar(255) |
| **`videodaypart`** | 串流媒體服務維度[時段](/help/components/dimensions/sm-video-metadata.md)。 | varchar(255) |
| **`videoepisode`** | 串流媒體服務維度[集數](/help/components/dimensions/sm-video-metadata.md)。 | varchar(255) |
| **`videofeedtype`** | 串流媒體服務維度[媒體摘要類型](/help/components/dimensions/sm-video-metadata.md)。 | varchar(255) |
| **`videogenre`** | 串流媒體服務維度[類型](/help/components/dimensions/sm-video-metadata.md)。此維度允許在同一個點擊中包含多個值，並以逗號分隔。 | text |
| **`videolength`** | 串流媒體服務維度[內容長度 (變數)](/help/components/dimensions/sm-core.md)。 | integer |
| **`videomvpd`** | 串流媒體服務維度 [MVPD](/help/components/dimensions/sm-video-metadata.md)。 | varchar(255) |
| **`videoname`** | 串流媒體服務維度[內容名稱 (變數)](/help/components/dimensions/sm-core.md)。 | varchar(255) |
| **`videonetwork`** | 串流媒體服務維度[網路](/help/components/dimensions/sm-video-metadata.md)。 | varchar(255) |
| **`videopath`** | 串流媒體服務維度[媒體路徑](/help/components/dimensions/sm-core.md)。 | varchar(100) |
| **`videoplayername`** | 串流媒體服務維度[內容播放器名稱](/help/components/dimensions/sm-core.md)。 | varchar(255) |
| **`videotime`** | 串流媒體服務量度[內容花費時間](/help/components/metrics/sm-core.md)。 | integer |
| **`videoqoebitrateaverageevar`** | 串流媒體服務維度[平均位元速率](/help/components/dimensions/sm-quality.md)。 | varchar(255) |
| **`videoqoebitratechangecountevar`** | 串流媒體服務維度[位元速率變更](/help/components/dimensions/sm-quality.md)。 | varchar(255) |
| **`videoqoebuffercountevar`** | 串流媒體服務維度[緩衝事件](/help/components/dimensions/sm-quality.md)。 | varchar(255) |
| **`videoqoebuffertimeevar`** | 串流媒體服務量度[總緩衝時間](/help/components/dimensions/sm-quality.md)。 | varchar(255) |
| **`videoqoedroppedframecountevar`** | 串流媒體服務維度[丟失的影格](/help/components/dimensions/sm-quality.md)。 | varchar(255) |
| **`videoqoeerrorcountevar`** | 串流媒體服務維度[錯誤](/help/components/dimensions/sm-quality.md)。 | varchar(255) |
| **`videoqoeextneralerrors`** | 串流媒體服務維度[外部錯誤 ID](/help/components/dimensions/sm-quality.md)。此維度允許在同一個點擊中包含多個值。 | text |
| **`videoqoeplayersdkerrors`** | 串流媒體服務維度[播放器 SDK 錯誤 ID](/help/components/dimensions/sm-quality.md)。此維度允許在同一個點擊中包含多個值。 | text |
| **`videoqoetimetostartevar`** | 串流媒體服務維度[開始時間](/help/components/dimensions/sm-quality.md)。 | varchar(255) |
| **`videoseason`** | 串流媒體服務維度[季節](/help/components/dimensions/sm-video-metadata.md)。 | varchar(255) |
| **`videosegment`** | 串流媒體服務維度[內容區段](/help/components/dimensions/sm-core.md)。 | varchar(255) |
| **`videoshow`** | 串流媒體服務維度[節目](/help/components/dimensions/sm-video-metadata.md)。 | varchar(255) |
| **`videoshowtype`** | 串流媒體服務維度[節目類型](/help/components/dimensions/sm-video-metadata.md)。 | varchar(255) |
| **`videostreamtype`** | 串流媒體服務維度[串流類型](/help/components/dimensions/sm-core.md)。 | varchar(255) |
| **`visid_high`** | 搭配 `visid_low` 使用，以唯一碼來識別一位訪客。 | bigint unsigned |
| **`visid_low`** | 搭配 `visid_high` 使用，以唯一碼來識別一位訪客。 | bigint unsigned |
| **`visid_new`** | 一個標幟，用來判斷該點擊是否包含新生成的訪客 ID。 | char(1) |
| **`visid_timestamp`** | 如果是新產生的訪客 ID，則提供該訪客 ID 生成的 UNIX® 時間戳記。 | int |
| **`visid_type`** | 不供外部使用；供 Adobe 在內部用來處理最佳化。代表用來識別訪客的方法的數值 ID。<br>`0`：自訂訪客 ID 或未知/不適用<br>`1`：IP 和用戶代理備援<br>`2`：HTTP 行動訂閱者標題<br>`3`：舊版 Cookie 值 (`s_vi`) <br>`4`：備援 Cookie 值 (`s_fid`) <br>`5`：身分識別服務 | tinyint unsigned |
| **`visit_keywords`** | [搜尋關鍵字](/help/components/dimensions/search-keyword.md)維度。此欄使用非標準字元限制 varchar(244) 來容納 Adobe 使用的後端邏輯。 | varchar(244) |
| **`visit_num`** | [造訪次數](/help/components/dimensions/visit-number.md)維度。從 1 開始，隨著每次訪客開始新的造訪而遞增。 | int unsigned |
| **`visit_page_num`** | [點擊深度](/help/components/dimensions/hit-depth.md)維度。每當訪客產生一次點擊，該數值增加 1。每次造訪都重設。 | int unsigned |
| **`visit_ref_domain`** | 依據`visit_referrer`欄而定。造訪的第一個反向連結網域。 | varchar(100) |
| **`visit_ref_type`** | 代表造訪的首次反向連結的反向連結類型數值 ID。請參考`referrer_type.tsv`查詢表。 | tinyint unsigned |
| **`visit_referrer`** | 造訪的第一個反向連結。 | varchar(255) |
| **`visit_search_engine`** | 代表造訪的第一個搜尋引擎的數值 ID。請參考`search_engines.tsv`查詢表。 | smallint unsigned |
| **`visit_start_page_url`** | 造訪的第一個 URL。 | varchar(255) |
| **`visit_start_pagename`** | 造訪首次點擊時的頁面名稱值。 | varchar(100) |
| **`visit_start_time_gmt`** | 造訪的第一次點擊時間戳記 (根據 UNIX® 時間)。 | int |
| **`weekly_visitor`** | 一個標幟，用來判斷該點擊是否為每週的新訪客。 | tinyint unsigned |
| **`yearly_visitor`** | 一個標幟，用來判斷該點擊是否為每年的新訪客。 | tinyint unsigned |
| **`zip`** | 協助填入[郵遞區號](/help/components/dimensions/zip-code.md)維度。另請參閱 `geo_zip`。 | varchar(50) |

{style="table-layout:auto"}

## 未使用或已停用的欄

以下列出的欄為未使用、已停用或因其他原因在報告中不包含任何值。其中一些欄與已停用的功能相關聯，而另一些則因為新的且更強大的功能而不再需要。這些欄大多數不包含資料；目前的資料彙集庫不支援可能仍包含資料的欄，且在 Analysis Workspace 中不是可用的維度。

* `adclassificationcreative`
* `click_action`
* `click_action_type`
* `click_context`
* `click_context_type`
* `click_sourceid`
* `click_tag`
* `hier1` - `hier5`
* `homepage`
* `ip2`
* `mobileacquisitionclicks`
* `mobileactioninapptime`
* `mobileactiontotaltime`
* `mobileappperformanceaffectedusers`
* `mobileappperformanceappid.app-perf-app-name`
* `mobileappperformanceappid.app-perf-platform`
* `mobileappperformancecrashes`
* `mobileappperformancecrashid.app-perf-crash-name`
* `mobileappperformanceloads`
* `mobileappstoreavgrating`
* `mobileappstoredownloads`
* `mobileappstoreinapprevenue`
* `mobileappstoreinapproyalties`
* `mobileappstoreobjectid.app-store-user`
* `mobileappstoreobjectid.application-name`
* `mobileappstoreobjectid.application-version`
* `mobileappstoreobjectid.appstore-name`
* `mobileappstoreobjectid.category-name`
* `mobileappstoreobjectid.country-name`
* `mobileappstoreobjectid.device-manufacturer`
* `mobileappstoreobjectid.device-name`
* `mobileappstoreobjectid.in-app-name`
* `mobileappstoreobjectid.platform-name-version`
* `mobileappstoreobjectid.rank-category-type`
* `mobileappstoreobjectid.region-name`
* `mobileappstoreobjectid.review-comment`
* `mobileappstoreobjectid.review-title`
* `mobileappstoreoneoffrevenue`
* `mobileappstoreoneoffroyalties`
* `mobileappstorepurchases`
* `mobileappstorerank`
* `mobileappstorerankdivisor`
* `mobileappstorerating`
* `mobileappstoreratingdivisor`
* `mobileavgprevsessionlength`
* `mobilecrashes`
* `mobilecrashrate`
* `mobiledailyengagedusers`
* `mobiledayssincelastupgrade`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobilelaunchessincelastupgrade`
* `mobileltv`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileosenvironment`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `namespace`
* `p_plugins`
* `page_event_var3`
* `partner_plugins`
* `plugins`
* `prev_page`
* `product_merchandising`
* `sampled_hit`
* `service`
* `socialaccountandappids`
* `socialassettrackingcode`
* `socialauthor`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialcontentprovider`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `socialinteractiontype`
* `sociallanguage`
* `sociallatlong`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialowneddefinitioninsighttype`
* `socialowneddefinitioninsightvalue`
* `socialowneddefinitionmetric`
* `socialowneddefinitionpropertyvspost`
* `socialownedpostids`
* `socialownedpropertyid`
* `socialownedpropertyname`
* `socialownedpropertypropertyvsapp`
* `socialpageviews`
* `socialpostviews`
* `socialproperty`
* `socialproperty (deprecated)`
* `socialpubcomments`
* `socialpubposts`
* `socialpubrecommends`
* `socialpubsubscribers`
* `socialterm`
* `socialtermslist`
* `socialtermslist (deprecated)`
* `socialtotalsentiment`
* `survey`
* `survey_instances`
* `tnt_post_vista`
* `ua_color`
* `ua_os`
* `ua_pixels`
* `videoauthorized`
* `videoaverageminuteaudience`
* `videochaptercomplete`
* `videochapterstart`
* `videochaptertime`
* `videopause`
* `videopausecount`
* `videopausetime`
* `videoplay`
* `videoprogress10`
* `videoprogress25`
* `videoprogress50`
* `videoprogress75`
* `videoprogress96`
* `videoqoebitrateaverage`
* `videoqoebitratechange`
* `videoqoebuffer`
* `videoqoedropbeforestart`
* `videoqoedroppedframes`
* `videoqoeerror`
* `videoresume`
* `videototaltime`
* `videouniquetimeplayed`

>[!MORELIKETHIS]
>
>[XDM 物件變數對應](/help/implement/aep-edge/xdm-var-mapping.md)
>[資料物件變數對應](/help/implement/aep-edge/data-var-mapping.md)
