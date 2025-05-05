---
description: 說明資料摘要中欄的表格資料。
keywords: 資料摘要；欄
subtopic: data feeds
title: 資料欄參考
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '3625'
ht-degree: 67%

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

您可在本頁之 [GitHub 上的認可歷史記錄](https://github.com/AdobeDocs/analytics.en/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)上找到之前對此表格的更新。

| 欄名稱 | 欄說明 | 資料類型 |
| --- | --- | --- |
| **`accept_language`** | 列出所有接受的語言，如影像要求中的 Accept-Language HTTP 標頭所示。 | char(20) |
| **`adload`** | 媒體廣告載入 | varchar(255) |
| **`aemassetid`** | 對應至一組Adobe Experience Manager Assets資產ID (GUID)的多值變數。 增加曝光數事件 | 文字 |
| **`aemassetsource`** | 識別資產事件的來源。用於 Adobe Experience Manager。 | varchar(255) |
| **`aemclickedassetid`** | Adobe Experience Manager 資產的資產 ID。增加點擊事件 | varchar(255) |
| **`browser`** | 表示瀏覽器的數值ID。 請參考`browser.tsv`查詢表。 | 不帶正負號的 int |
| **`browser_height`** | [瀏覽器高度](/help/components/dimensions/browser-height.md)維度。 | 不帶正負號的 smallint |
| **`browser_width`** | [瀏覽器寬度](/help/components/dimensions/browser-width.md) | 不帶正負號的 smallint |
| **`c_color`** | 調色盤的位元深度。用於計算[色階](/help/components/dimensions/color-depth.md)維度的一部分。AppMeasurement 使用 JavaScript 函數`screen.colorDepth()`。 | char(20) |
| **`campaign`** | [追踪Code](/help/components/dimensions/tracking-code.md)維度。 | varchar(255) |
| **`carrier`** | Adobe Advertising 整合變數。指定行動電信業者。`carrier.tsv` [動態查詢](dynamic-lookups.md)的索引鍵值。 | varchar(100) |
| **`ch_hdr`** | 透過 HTTP 請求標頭收集的用戶端提示。 | 文字 |
| **`ch_js`** | 透過使用者代理用戶端提示 JavaScript API 收集的用戶端提示。 | 文字 |
| **`channel`** | [網站區段](/help/components/dimensions/site-section.md)維度。 | varchar(100) |
| **`clickmaplink`** | Activity Map 連結 | varchar(255) |
| **`clickmaplinkbyregion`** | Activity Map 連結 (依地區) | varchar(255) |
| **`clickmappage`** | Activity Map 頁面 | varchar(255) |
| **`clickmapregion`** | Activity Map 地區 | varchar(255) |
| **`code_ver`** | 用於編譯及傳送影像要求的 API 或客戶端 SDK 版本。 | char(16) |
| **`color`** | 以`c_color`欄的值為基礎的色階 ID。請參考`color_depth.tsv`查詢表。 | 不帶正負號的 smallint |
| **`connection_type`** | 表示連線型別的數值ID。 [連線型別](/help/components/dimensions/connection-type.md)維度。 請參考`connection_type.tsv`查詢表。 | 不帶正負號的 tinyint |
| **`cookies`** | [Cookie支援](/help/components/dimensions/cookie-support.md)維度。<br>Y：啟用<br>N：停用<br>U：未知 | char(1) |
| **`country`** | 表示訪客所在國家/地區的數值ID。 請參考`country.tsv`查詢表。 | 不帶正負號的 smallint |
| **`ct_connect_type`** | 和`connection_type`欄相關。最常見的值為LAN/Wifi、行動電信業者和資料機。 | char(20) |
| **`curr_factor`** | 決定貨幣小數位數，並用於貨幣轉換。例如，USD使用兩位小數，所以此欄值為`2`。 | tinyint |
| **`curr_rate`** | 交易發生當時的匯率。Adobe 與 XE 合作，以決定當日匯率。 | decimal(24,12) |
| **`currency`** | 交易期間使用的貨幣代碼。 使用[`currencyCode`](/help/implement/vars/config-vars/currencycode.md)設定。 | char(8) |
| **`cust_hit_time_gmt`** | 僅限啟用時間戳記的報告套裝。時間戳記根據 UNIX® 時間隨點擊傳送。 | int |
| **`cust_visid`** | 自訂訪客ID （如果使用[`visitorID`](/help/implement/vars/config-vars/visitorid.md)設定）。 | varchar(255) |
| **`daily_visitor`** | 此旗標可確定點選是否為新的每日訪客。 | 不帶正負號的 tinyint |
| **`dataprivacyconsentoptin`** | [同意管理選擇加入](/help/components/dimensions/cm-opt-in.md)維度。 每個點擊可以有多個值，以垂直號 (`\|`) 分隔。有效值包括 `DMP` 和 `SELL`。 | varchar(100) |
| **`dataprivacyconsentoptout`** | [同意管理選擇退出](/help/components/dimensions/cm-opt-out.md)維度。 每個點擊可以有多個值，以垂直號 (`\|`) 分隔。有效值包括 `SSF`、`DMP` 和 `SELL`。 | varchar(100) |
| **`dataprivacydmaconsent`** | 此值可識別透過Adobe Advertising將資料從Adobe Analytics傳送至第三方廣告提供者(例如Google)時是否獲得同意。 如需詳細資訊，請參閱[廣告同意](/help/components/dimensions/ad-consent.md)。 | varchar(100) |
| **`date_time`** | 可讀格式的點擊時間，根據報告套裝的時區而定。 | 日期時間 |
| **`domain`** | 域[&#128279;](/help/components/dimensions/domain.md)維度。根據訪客的互聯網接入点。 | varchar(100) |
| **`duplicate_events`** | 列出每個計為重複項目的事件。 | varchar(255) |
| **`duplicate_purchase`** | 此旗標可判斷此點選的購買事件是否因為重複而被忽略。 | 不帶正負號的 tinyint |
| **`duplicated_from`** | 僅用於包含點擊複製 VISTA 規則的報告套裝。指出從中複製點擊的報告套裝。 | varchar(40) |
| **`ef_id`** | `ef_id`用於 Adobe Advertising 整合。 | varchar(255) |
| **`evar1 - evar250`** | 自訂變數 1-250。用於[eVar](/help/components/dimensions/evar.md)維度。每個組織使用不同的 eVar。若要瞭解貴組織如何填入個別eVar的詳細資訊，最佳方式是貴組織專屬的[解決方案設計檔案](/help/implement/prepare/solution-design.md)。 | varchar(255) |
| **`event_list`** | 以逗号分隔的 數值 ID 清單，代表點擊觸發的事件。 包括預設事件和 [自定義事件 1-1000](/help/components/metrics/custom-events.md)。 使用`event.tsv`查詢。 | 文字 |
| **`exclude_hit`** | 確定是否從報告排除點擊的標幟。 此`visit_num`欄不會因排除的點擊而遞增。<br>1：未使用。屬於已報廢功能。<br>2：未使用。屬於已報廢功能。<br>3：已不再使用。用戶代理排除<br>4：依據 IP 位址的排除<br>5：遺失重要點擊資訊，例如`page_url`、`pagename`、`page_event`、或者`event_list`<br>6：JavaScript 沒有正確處理點擊<br>7：特定帳戶的排除，例如在 Vista 規則中<br>8：未使用。替代帳戶特定排除。<br>9：未使用。屬於已報廢功能。<br>10：無效的貨幣代碼<br>11：僅時間戳記報告套裝上遺失時間戳記的點擊，或非時間戳記報告套裝上包含時間戳記的點擊<br>12：未使用。屬於已報廢功能。<br>13：未使用。屬於已報廢功能。<br>14：不符合 Analytics 點擊的 Target 點擊<br>15：目前未使用。<br>16：不符合 Analytics 點擊的 Advertising Cloud 點擊 | 不帶正負號的 tinyint |
| **`first_hit_page_url`** | 訪客的第一個 URL。 | varchar(255) |
| **`first_hit_pagename`** | [登入頁面原始](/help/components/dimensions/entry-dimensions.md)維度。 訪客的原始登入頁面名稱。 | varchar(100) |
| **`first_hit_ref_domain`** | [原始反向連結網域](/help/components/dimensions/original-referring-domain.md)維度。 根據`first_hit_referrer`而定。訪客的第一個反向連結網域。 | varchar(100) |
| **`first_hit_ref_type`** | 表示訪客第一個反向連結的反向連結型別數值ID。 請參考`referrer_type.tsv`查詢表。 | 不帶正負號的 tinyint |
| **`first_hit_referrer`** | 訪客的第一個反向連結 URL。 | varchar(255) |
| **`first_hit_time_gmt`** | 訪客初次點擊的時間戳記 (根據 UNIX® 時間)。 | int |
| **`geo_city`** | 根據IP的點選來源城市名稱。 用於[城市](/help/components/dimensions/cities.md)維度。 | char(32) |
| **`geo_country`** | 根據IP的點選來源國家/地區縮寫。 用於[國家/地區](/help/components/dimensions/countries.md)維度。 | char(4) |
| **`geo_dma`** | 根據IP的點選來源人口統計區域數值ID。 用於 [美國 DMA](/help/components/dimensions/us-dma.md) 維度。 | 不帶正負號的 int |
| **`geo_region`** | 根據IP的點選來源州或地區名稱。 用於[地區](/help/components/dimensions/regions.md)維度。 | char(32) |
| **`geo_zip`** | 點擊來源的郵遞區號 (根據 IP 位址)。協助填入[郵遞區號](/help/components/dimensions/zip-code.md)維度。另請參閱`zip`。 | varchar(16) |
| **`hit_source`** | 點選的來源。 點擊來源 1、2 和 6 需計費。<br>1：沒有時間戳記的標準影像要求<br>2：具有時間戳記的標準影像要求<br>3：具有時間戳記的即時資料來源上傳<br>4：未使用<br>5：通用資料來源上傳<br>6：完整處理資料來源上傳<br>7：TransactionID 資料來源上傳<br>8：不再使用；舊版 Adobe Advertising Cloud 資料來源 <br>9：已不再使用；Adobe Social 摘要量度<br>10：使用 Audience Manager 伺服器端轉送 | 不帶正負號的 tinyint |
| **`hit_time_gmt`** | Adobe 資料收集伺服器收到點擊的時間戳記 (根據 UNIX® 時間)。 | int |
| **`hitid_high`** | 搭配 `hitid_low` 使用來識別點擊。 | 不帶正負號的 bigint |
| **`hitid_low`** | 搭配 `hitid_high` 使用來識別點擊。 | 不帶正負號的 bigint |
| **`hourly_visitor`** | 此旗標可確定點選是否為每小時的新訪客。 | 不帶正負號的 tinyint |
| **`ip`** | IPv4 位址，根據影像請求 HTTP 標頭。與 `ipv6` 互斥；如果此欄包含非模糊 IP 位址，`ipv6` 為空白。 | char(20) |
| **`ipv6`** | 壓縮的 IPv6 位址 (若有)。與 `ip` 互斥；如果此欄包含非模糊 IP 位址，`ip` 為空白。 | varchar(40) |
| **`j_jscript`** | 瀏覽器支援的 JavaScript 版本。 | char(5) |
| **`java_enabled`** | [[!UICONTROL Java已啟用]](/help/components/dimensions/java-enabled.md)。 <br>Y：啟用 <br>N：停用 <br>U：未知 | char(1) |
| **`javascript`** | JavaScript版本的查閱 ID （基於 `j_jscript`）。 請參考`javascript_version`查詢表。 | 不帶正負號的 tinyint |
| **`language`** | 代表訪客語言的 數值 ID。 請參考`languages.tsv`查詢表。 | 不帶正負號的 smallint |
| **`last_hit_time_gmt`** | 先前點擊的時間戳記 (根據 UNIX® 時間)。用於計算[[!UICONTROL 和上次造訪間隔天數]](/help/components/dimensions/days-since-last-visit.md)維度。 | int |
| **`last_purchase_num`** | [客戶忠誠度](/help/components/dimensions/customer-loyalty.md)維度。 訪客之前已購買的次數。<br>0：沒有先前購買 (非客戶) <br>1：先前購買 1 次 (新客戶) <br>2：先前購買 2 次 (回頭客戶) <br>3：先前購買 3 次以上 (忠實客戶) | 不帶正負號的 int |
| **`last_purchase_time_gmt`** | 用於[[!UICONTROL 和上次購買間隔天數]](/help/components/dimensions/days-since-last-purchase.md)維度。上次進行購買的時間戳記 (根據 UNIX® 時間)。對於首次購買和之前未購買的訪客，此值為 `0`。 | int |
| **`latlon1`** | 位置 (10 公里以內) | varchar(255) |
| **`latlon23`** | 位置 (100 公尺以內) | varchar(255) |
| **`latlon45`** | 位置 (1 公尺以內) | varchar(255) |
| **`mc_audiences`** | 訪客所屬的 Audience Manager 區段 ID 清單。`post_mc_audiences` 欄會將分隔符號變更為 `--**--`。 | 文字 |
| **`mcvisid`** | Experience Cloud 訪客 ID。128 位元的數字，由兩個串連的 64 位元數字組成，兩個數字皆補至 19 位數。 | varchar(255) |
| **`mobile_id`** | 如果使用者使用行動裝置，則為裝置的數值 ID。`mobile_attributes.tsv` [動態查詢](dynamic-lookups.md)的索引鍵值。 | int |
| **`mobileaction`** | 行動動作。在行動實作中呼叫`trackAction`時自動收集。 允許應用程式中的自動動作路徑。 | varchar(100) |
| **`mobileappid`** | 行動應用程式 ID。以下列格式儲存應用程式名稱和版本：`[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | 用於 Apteligent 資料連接器。Apteligent 中使用的應用程式 ID。 | varchar(255) |
| **`mobileappperformancecrashid`** | 用於 Apteligent 資料連接器。Apteligent 中使用的當機 ID。 | varchar(255) |
| **`mobileappstoreobjectid`** | 用於[!DNL Appfigures]資料聯結器。 應用程式商店物件 ID。 | varchar(255) |
| **`mobilebeaconmajor`** | 行動服務主要信標 | varchar(100) |
| **`mobilebeaconminor`** | 行動服務次要信標 | varchar(100) |
| **`mobilebeaconproximity`** | 行動服務鄰近地區信標 | varchar(255) |
| **`mobilebeaconuuid`** | 行動服務信標 UUID | varchar(100) |
| **`mobilecampaigncontent`** | 顯示連結之內容的名稱或 ID。由「行動應用程式贏取」填入。 | varchar(255) |
| **`mobilecampaignmedium`** | 行銷媒體，例如橫幅或電子郵件。由「行動應用程式贏取」填入。 | varchar(255) |
| **`mobilecampaignname`** | 促銷活動名稱，亦儲存在促銷活動變數中。 由「行動應用程式贏取」填入。 | varchar(255) |
| **`mobilecampaignsource`** | 原始反向連結，例如電子報或社交媒體網路。由「行動應用程式贏取」填入。 | varchar(255) |
| **`mobilecampaignterm`** | 您要對此贏取追蹤的付費關鍵字或其他詞語。由「行動應用程式贏取」填入。 | varchar(255) |
| **`mobiledayofweek`** | 應用程式啟動的工作日數。 | varchar(255) |
| **`mobiledayssincefirstuse`** | 自應用程式初次執行以來的天數。 | varchar(255) |
| **`mobiledayssincelastuse`** | 自應用程式上次執行以來的天數。 | varchar(255) |
| **`mobiledeeplinkid`** | 從內容資料變數`a.deeplink.id`中收集。用於贏取報表中，作為行動贏取連結的識別碼。 | varchar(255) |
| **`mobiledevice`** | 行動裝置名稱。在 iOS 上，此名稱以逗號分隔的 2 位數字串形式儲存。第一個數字代表裝置代別，第二個數字代表裝置系列。 | varchar(255) |
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
| **`monthly_visitor`** | 此旗標可判斷訪客是否屬於當月的不重複訪客。 | 不帶正負號的 tinyint |
| **`mvvar1`** - `mvvar3` | [清單變數](/help/implement/vars/page-vars/list.md)值。 根據實施包含使用分隔符號的自訂值清單。`post_mvvar1` - `post_mvvar3` 欄會以 `--**--` 取代原始的分隔符號。 | 文字 |
| **`mvvar1_instances`** - `mvvar3_instances` | 在目前點擊上設定的清單變數值。以 `--**--` 取代原始的分隔符號。這些 `post` 列通常不包含數據。 | 文字 |
| **`new_visit`** | 此旗標可確定目前的點選是否為新造訪。 造訪閒置30分鐘後，由Adobe設定。 | 不帶正負號的 tinyint |
| **`os`** | 表示訪客的作業系統的數值ID。 依據`user_agent`欄而定。`operating_system.tsv`標準查詢和`operating_system_type.tsv`[動態查詢](dynamic-lookups.md)的索引鍵值。 | 不帶正負號的 int |
| **`page_event`** | 影像要求中傳送的點擊類型 (標準點擊、下載連結、自訂連結、退出連結)。請參閱[頁面事件查閱](datafeeds-page-event.md)。 | 不帶正負號的 tinyint |
| **`page_event_var1`** | 僅用於連結追蹤影像要求。點按之下載連結、退出連結或自訂連結的 URL。 | 文字 |
| **`page_event_var2`** | 僅用於連結追蹤影像要求。連結的自訂名稱（如果已指定）。 根據`page_event`中的值設定[自訂連結](/help/components/dimensions/custom-link.md)、[下載連結](/help/components/dimensions/download-link.md)或[退出連結](/help/components/dimensions/exit-link.md)。 | varchar(100) |
| **`page_type`** | 找不到 [頁面](/help/components/dimensions/pages-not-found.md) 維度，通常用於 404 頁面。 | char(20) |
| **`page_url`** | 點擊的 URL。請注意， `post_page_url` 連結追蹤圖像請求 （[`tl()`](/help/implement/vars/functions/tl-method.md)） 被剝離，並使用數據類型 varchar（255）。 | 文字 |
| **`pagename`** | [頁面](/help/components/dimensions/page.md)維度。 如果[`pagename`](/help/implement/vars/page-vars/pagename.md)變數為空白，Analytics 會改用`page_url`。 | varchar(100) |
| **`pagename_no_url`** | 與 `pagename` 類似，但不會回復到 `page_url`。只有 `post` 列適用。 | varchar(100) |
| **`paid_search`** | 決定點選是否符合付費搜尋偵測的旗標。 | 不帶正負號的 tinyint |
| **`persistent_cookie`** | 用於[持續性 Cookie 支援](/help/components/dimensions/persistent-cookie-support.md)維度。指出訪客是否支援每次點擊後未捨棄的 Cookie。 | char(1) |
| **`pointofinterest`** | 行動服務興趣點名稱 | varchar(255) |
| **`pointofinterestdistance`** | 行動服務與興趣點中心的距離 | varchar(255) |
| **`post_`**&#x200B;欄 | 包含報表中最終使用的值。每個後置欄會填入伺服器端邏輯、處理規則和 VISTA 規則之後。Adobe 建議在大多數情況下使用後置欄。 | 請參閱各個非後置欄 |
| **`product_list`** | [`products`](/help/implement/vars/page-vars/products.md)頁面變數。 協助填入多個維度和量度，包括[類別](/help/components/dimensions/category.md)、[產品](/help/components/dimensions/product.md)、[單位](/help/components/metrics/units.md)和[收入](/help/components/metrics/revenue.md)。 | 文字 |
| **`prop1`** - `prop75` | 自訂流量變數 1 - 75。用於 [Prop](/help/components/dimensions/prop.md) 維度。 | varchar(100) |
| **`purchaseid`** | 使用[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)變數設定之購買的唯一識別碼。由`duplicate_purchase`欄使用。 | char(20) |
| **`quarterly_visitor`** | 此旗標可確定點選是否為新的每季訪客。 | 不帶正負號的 tinyint |
| **`ref_domain`** | [反向連結網域](/help/components/dimensions/referring-domain.md)維度。 根據`referrer`資料行。 | varchar(100) |
| **`ref_type`** | 表示點選的反向連結型別的數值ID。 用於[反向連結類型](/help/components/dimensions/referrer-type.md)維度。<br>1：網站內<br>2：其他網站 <br>3：搜尋引擎 <br>4：硬碟 <br>5：USENET <br>6：分類/建立書籤 (無反向連結) <br>7：電子郵件 <br>8：無 JavaScript <br>9：社交網路 | 不帶正負號的 tinyint |
| **`referrer`** | [反向連結](/help/components/dimensions/referrer.md)維度。 請注意，雖然 `referrer` 使用 varchar(255) 資料類型，但 `post_referrer` 是使用 varchar(244) 資料類型。 | varchar(255) |
| **`resolution`** | 表示熒幕解析度的數值ID。 用於[螢幕解析度](/help/components/dimensions/monitor-resolution.md)維度。使用`resolution.tsv`查詢表。 | 不帶正負號的 smallint |
| **`s_kwcid`** | 用於 Adobe Advertising 整合的關鍵字 ID。 | varchar(255) |
| **`s_resolution`** | 原始螢幕解析度值。使用 JavaScript 函數`screen.width x screen.height`收集。 | char(20) |
| **`search_engine`** | 表示將訪客反向連結至您網站的搜尋引擎數值ID。 用於[搜尋引擎](/help/components/dimensions/search-engine.md)維度。 請參考`search_engines.tsv`查詢表。 | 不帶正負號的 smallint |
| **`search_page_num`** | 由[所有搜尋頁面排名](/help/components/dimensions/all-search-page-rank.md)維度使用。在使用者點進您的網站之前，指示您的網站要顯示哪個搜尋結果頁面。 | 不帶正負號的 smallint |
| **`secondary_hit`** | 此旗標可判斷點選是否為次要點選。 此標幟通常源自複製點選的多套裝標籤和VISTA規則。 | 不帶正負號的 tinyint |
| **`sourceid`** | 來源 ID | 不帶正負號的 int |
| **`state`** | State 變數。 | varchar(50) |
| **`stats_server`** | 未使用。處理點擊的 Adobe 內部伺服器。 | char(30) |
| **`t_time_info`** | 訪客的當地時間。格式為：`M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | 用於 Adobe Target 整合。 代表目前符合條件的所有測試。 格式為：`TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`。 | 文字 |
| **`tnt_action`** | 用於 Adobe Target 整合。 代表點擊合格的所有測試。 | 文字 |
| **`tnt_instances`** | 用於 Adobe Target 整合。 Target 執行個體變數。 | 文字 |
| **`transactionid`** | 唯一識別碼，日後可透過資料來源上傳各種資料點。使用[`transactionID`](/help/implement/vars/page-vars/transactionid.md)變數收集。 | 文字 |
| **`truncated_hit`** | 指出影像要求已截斷的旗標。 表示已收到部分點擊。<br>Y：點擊遭截斷；收到部分點擊 <br>N：點擊未截斷；收到完整點擊 | char(1) |
| **`user_agent`** | 在影像要求的HTTP標頭中傳送的使用者代理字串。 | 文字 |
| **`user_hash`** | 未使用。報告套裝 ID 上的雜湊.請改用 `username`。 | 不帶正負號的 int |
| **`user_server`** | 用於[伺服器](/help/components/dimensions/server.md)維度。 | varchar(100) |
| **`userid`** | 未使用。報告套裝 ID 的數值 ID。請改用 `username`。 | 不帶正負號的 int |
| **`username`** | 點擊的報告套裝 ID。 | char(40) |
| **`va_closer_detail`** | [上次接觸詳細資料](/help/components/dimensions/last-touch-detail.md)維度。 | varchar(255) |
| **`va_closer_id`** | 可識別[上次接觸管道](/help/components/dimensions/last-touch-channel.md)維度的數值ID。 您可於行銷管道管理員中查詢此ID。 | 不帶正負號的 tinyint |
| **`va_finder_detail`** | [首次接觸詳細資料](/help/components/dimensions/first-touch-detail.md)維度。 | varchar(255) |
| **`va_finder_id`** | 可識別[首次接觸管道](/help/components/dimensions/first-touch-channel.md)維度的數值ID。 您可於行銷管道管理員中查詢此ID。 | 不帶正負號的 tinyint |
| **`va_instance_event`** | 識別行銷管道[執行個體](/help/components/metrics/instances.md)的旗標。 | 不帶正負號的 tinyint |
| **`va_new_engagement`** | 識別行銷管道[新參與](/help/components/metrics/new-engagements.md)的旗標。 | 不帶正負號的 tinyint |
| **`video`** | [內容](/help/components/dimensions/sm-core.md)串流媒體維度。 | varchar(255) |
| **`videoad`** | [廣告](/help/components/dimensions/sm-ads.md)串流媒體維度。 | varchar(255) |
| **`videoadinpod`** | Pod位置[&#128279;](/help/components/dimensions/sm-ads.md)串流媒體維度中的廣告。 | varchar(255) |
| **`videoadlength`** | [廣告長度（變數）](/help/components/dimensions/sm-ads.md)串流媒體維度。 | 整數 |
| **`videoadload`** | [廣告載入](/help/components/dimensions/sm-ads.md)串流媒體維度。 | varchar(255) |
| **`videoadname`** | [廣告名稱（變數）](/help/components/dimensions/sm-ads.md)串流媒體維度。 | varchar(255) |
| **`videoadplayername`** | [廣告播放器名稱](/help/components/dimensions/sm-ads.md)串流媒體維度。 | varchar(255) |
| **`videoadpod`** | [廣告Pod](/help/components/dimensions/sm-ads.md)串流媒體維度。 | varchar(255) |
| **`videoadvertiser`** | 廣告 [商](/help/components/dimensions/sm-ads.md) 流媒體維度。 | varchar(255) |
| **`videoaudioalbum`** | 專輯[&#128279;](/help/components/dimensions/sm-audio-metadata.md)流媒體維度。 | varchar(255) |
| **`videoaudioartist`** | [藝人](/help/components/dimensions/sm-audio-metadata.md)串流媒體維度。 | varchar(255) |
| **`videoaudioauthor`** | [作者](/help/components/dimensions/sm-audio-metadata.md)串流媒體維度。 | varchar(255) |
| **`videoaudiolabel`** | [標籤](/help/components/dimensions/sm-audio-metadata.md)串流媒體維度。 | varchar(255) |
| **`videoaudiopublisher`** | [發佈者](/help/components/dimensions/sm-audio-metadata.md)串流媒體維度。 | varchar(255) |
| **`videoaudiostation`** | [電台](/help/components/dimensions/sm-audio-metadata.md)串流媒體維度。 | varchar(255) |
| **`videocampaign`** | [行銷活動ID](/help/components/dimensions/sm-ads.md)串流媒體維度。 | varchar(255) |
| **`videochannel`** | [內容頻道](/help/components/dimensions/sm-core.md)串流媒體維度。 | varchar(255) |
| **`videochapter`** | [Chapter](/help/components/dimensions/sm-chapters.md)串流媒體維度。 | varchar(255) |
| **`videocontenttype`** | 內容類型[&#128279;](/help/components/dimensions/sm-core.md)流媒體維度。 | varchar(255) |
| **`videodaypart`** | [日部分](/help/components/dimensions/sm-video-metadata.md)流媒體維度。 | varchar(255) |
| **`videoepisode`** | [Episode](/help/components/dimensions/sm-video-metadata.md)串流媒體維度。 | varchar(255) |
| **`videofeedtype`** | [媒體摘要型別](/help/components/dimensions/sm-video-metadata.md)串流媒體維度。 | varchar(255) |
| **`videogenre`** | [流派](/help/components/dimensions/sm-video-metadata.md)流媒體維度。此維度允許同一點擊中有多個值，以逗號分隔。 | 文字 |
| **`videolength`** | [內容長度（變數）](/help/components/dimensions/sm-core.md)串流媒體維度。 | 整數 |
| **`videomvpd`** | [MVPD](/help/components/dimensions/sm-video-metadata.md)串流媒體維度。 | varchar(255) |
| **`videoname`** | [內容名稱（變數）](/help/components/dimensions/sm-core.md)串流媒體維度。 | varchar(255) |
| **`videonetwork`** | [網路](/help/components/dimensions/sm-video-metadata.md)串流媒體維度。 | varchar(255) |
| **`videopath`** | [媒體路徑](/help/components/dimensions/sm-core.md)串流媒體維度。 | varchar(100) |
| **`videoplayername`** | [內容播放器名稱](/help/components/dimensions/sm-core.md)串流媒體維度。 | varchar(255) |
| **`videotime`** | [內容逗留時間](/help/components/metrics/sm-core.md)串流媒體量度。 | 整數 |
| **`videoqoebitrateaverageevar`** | [平均位元速率](/help/components/dimensions/sm-quality.md)串流媒體維度。 | varchar(255) |
| **`videoqoebitratechangecountevar`** | [位元速率變更](/help/components/dimensions/sm-quality.md)串流媒體維度。 | varchar(255) |
| **`videoqoebuffercountevar`** | [緩衝事件](/help/components/dimensions/sm-quality.md)串流媒體維度。 | varchar(255) |
| **`videoqoebuffertimeevar`** | [總緩衝期間](/help/components/dimensions/sm-quality.md)串流媒體維度。 | varchar(255) |
| **`videoqoedroppedframecountevar`** | [掉格](/help/components/dimensions/sm-quality.md)串流媒體維度。 | varchar(255) |
| **`videoqoeerrorcountevar`** | [錯誤](/help/components/dimensions/sm-quality.md)串流媒體維度。 | varchar(255) |
| **`videoqoeextneralerrors`** | [外部錯誤識別碼](/help/components/dimensions/sm-quality.md)串流媒體維度。 此維度允許同一次點選中有多個值。 | 文字 |
| **`videoqoeplayersdkerrors`** | [播放器 SDK 錯誤 ID](/help/components/dimensions/sm-quality.md) 流媒體維度。此維度允許同一點擊中有多個值。 | 文字 |
| **`videoqoetimetostartevar`** | [是時候開始](/help/components/dimensions/sm-quality.md)流媒體維度了。 | varchar(255) |
| **`videoseason`** | [本季](/help/components/dimensions/sm-video-metadata.md)流媒體維度。 | varchar(255) |
| **`videosegment`** | [內容區段](/help/components/dimensions/sm-core.md)串流媒體維度。 | varchar(255) |
| **`videoshow`** | [節目](/help/components/dimensions/sm-video-metadata.md)串流媒體維度。 | varchar(255) |
| **`videoshowtype`** | [節目型別](/help/components/dimensions/sm-video-metadata.md)串流媒體維度。 | varchar(255) |
| **`videostreamtype`** | [串流型別](/help/components/dimensions/sm-core.md)串流媒體維度。 | varchar(255) |
| **`visid_high`** | 搭配 `visid_low` 使用，以唯一碼來識別一位訪客。 | 不帶正負號的 bigint |
| **`visid_low`** | 搭配 `visid_high` 使用，以唯一碼來識別一位訪客。 | 不帶正負號的 bigint |
| **`visid_new`** | 此旗標可確定點選是否包含新產生的訪客ID。 | char(1) |
| **`visid_timestamp`** | 如果是新產生訪客ID，則會提供產生訪客ID時的時間戳記(UNIX®)。 | int |
| **`visid_type`** | 不供外部使用；供 Adobe 在內部用來處理最佳化。此數值ID代表用來識別訪客的方法。<br>`0`：自訂訪客 ID 或未知/不適用<br>`1`：IP 和用戶代理備援<br>`2`：HTTP 行動訂閱者標題<br>`3`：舊版 Cookie 值 (`s_vi`) <br>`4`：備援 Cookie 值 (`s_fid`) <br>`5`：身分識別服務 | 不帶正負號的 tinyint |
| **`visit_keywords`** | [搜尋關鍵字](/help/components/dimensions/search-keyword.md)維度。 此欄使用非標準字元限制 varchar(244) 來容納 Adobe 使用的後端邏輯。 | varchar(244) |
| **`visit_num`** | 「造訪」編號[&#128279;](/help/components/dimensions/visit-number.md)為 維度。從 1 開始，隨著每次訪客開始新的造訪而遞增。 | 不帶正負號的 int |
| **`visit_page_num`** | 點擊深度[&#128279;](/help/components/dimensions/hit-depth.md)維度。對於訪客產生的每個點擊增加 1。 重設每次造訪。 | 不帶正負號的 int |
| **`visit_ref_domain`** | 依據`visit_referrer`欄而定。造訪的第一個反向連結網域。 | varchar(100) |
| **`visit_ref_type`** | 表示造訪第一推薦者的推薦者類型的數值 ID。 請參考`referrer_type.tsv`查詢表。 | 不帶正負號的 tinyint |
| **`visit_referrer`** | 造訪的第一個反向連結。 | varchar(255) |
| **`visit_search_engine`** | 表示造訪的第一個搜尋引擎數值ID。 請參考`search_engines.tsv`查詢表。 | 不帶正負號的 smallint |
| **`visit_start_page_url`** | 造訪的第一個 URL。 | varchar(255) |
| **`visit_start_pagename`** | 造訪首次點擊時的頁面名稱值。 | varchar(100) |
| **`visit_start_time_gmt`** | 造訪的第一次點擊時間戳記 (根據 UNIX® 時間)。 | int |
| **`weekly_visitor`** | 此旗標可確定點選是否為每週新訪客。 | 不帶正負號的 tinyint |
| **`yearly_visitor`** | 此旗標可確定點選是否為每年新訪客。 | 不帶正負號的 tinyint |
| **`zip`** | 協助填入[郵遞區號](/help/components/dimensions/zip-code.md)維度。另請參閱 `geo_zip`。 | varchar(50) |

{style="table-layout:auto"}

## 未使用或已淘汰的欄

下列清單為未使用、已淘汰的欄，或報表中不包含值。 這些欄中有些是繫結至已淘汰的功能，有些則是因為新增且更強大的功能而不再需要。 這些欄大多不包含資料；目前資料收集程式庫不支援可能仍包含資料的欄，而且在Analysis Workspace中不是可用的維度。

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
>[XDM物件變數對應](/help/implement/aep-edge/xdm-var-mapping.md)
>[資料物件變數對應](/help/implement/aep-edge/data-var-mapping.md)
