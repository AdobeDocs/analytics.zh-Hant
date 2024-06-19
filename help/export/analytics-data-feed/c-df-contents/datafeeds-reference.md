---
description: 說明資料摘要中欄的表格資料。
keywords: 資料摘要；欄
subtopic: data feeds
title: 資料欄參考
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '3928'
ht-degree: 99%

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
| **`aemassetid`** | 對應一組「Adobe Experience Manager 資產」之資產 ID (GUID) 的多值變數。增加曝光數事件 | 文字 |
| **`aemassetsource`** | 識別資產事件的來源。用於 Adobe Experience Manager。 | varchar(255) |
| **`aemclickedassetid`** | Adobe Experience Manager 資產的資產 ID。增加點擊事件 | varchar(255) |
| **`browser`** | 瀏覽器的數值 ID。請參考`browser.tsv`查詢表。 | 不帶正負號的 int |
| **`browser_height`** | 瀏覽器視窗的高度 (像素)。 | 不帶正負號的 smallint |
| **`browser_width`** | 瀏覽器視窗的寬度 (像素)。 | 不帶正負號的 smallint |
| **`c_color`** | 調色盤的位元深度。用於計算[色階](/help/components/dimensions/color-depth.md)維度的一部分。AppMeasurement 使用 JavaScript 函數`screen.colorDepth()`。 | char(20) |
| **`campaign`** | 用於[追蹤代碼](/help/components/dimensions/tracking-code.md)維度的變數。 | varchar(255) |
| **`carrier`** | Adobe Advertising 整合變數。指定行動電信業者。`carrier.tsv` [動態查詢](dynamic-lookups.md)的索引鍵值。 | varchar(100) |
| **`ch_hdr`** | 透過 HTTP 請求標頭收集的用戶端提示。 | 文字 |
| **`ch_js`** | 透過使用者代理用戶端提示 JavaScript API 收集的用戶端提示。 | 文字 |
| **`channel`** | 用於[網站區段](/help/components/dimensions/site-section.md)維度的變數。 | varchar(100) |
| **`click_action`** | 已不再使用。在舊版 ClickMap 工具中已點選的連結位址。 | varchar(100) |
| **`click_action_type`** | 已不再使用。舊版 ClickMap 工具的連結類型。<br>0：HREF URL<br>1：自訂 ID<br>2：JavaScript onClick 事件<br>3：表單元素 | 不帶正負號的 tinyint |
| **`click_context`** | 已不再使用。發生連結點按的頁面名稱。舊版 ClickMap 工具的一部分。 | varchar(255) |
| **`click_context_type`** | 已不再使用。表示 `click_context` 是否具備頁面名稱或預設為頁面 URL。<br>0：頁面 URL<br>1：頁面名稱 | 不帶正負號的 tinyint |
| **`click_sourceid`** | 已不再使用。點按連結頁面上位置的數值 ID。舊版 ClickMap 工具的一部分。 | 不帶正負號的 int |
| **`click_tag`** | 已不再使用。已點擊的 HTML 元素類型。 | char(10) |
| **`clickmaplink`** | Activity Map 連結 | varchar(255) |
| **`clickmaplinkbyregion`** | Activity Map 連結 (依地區) | varchar(255) |
| **`clickmappage`** | Activity Map 頁面 | varchar(255) |
| **`clickmapregion`** | Activity Map 地區 | varchar(255) |
| **`code_ver`** | 用於編譯及傳送影像要求的 API 或客戶端 SDK 版本。 | char(16) |
| **`color`** | 以`c_color`欄的值為基礎的色階 ID。請參考`color_depth.tsv`查詢表。 | 不帶正負號的 smallint |
| **`connection_type`** | 表示連線類型的數值 ID。用於[連線類型](/help/components/dimensions/connection-type.md)維度的變數。請參考`connection_type.tsv`查詢表。 | 不帶正負號的 tinyint |
| **`cookies`** | 用於 [Cookie 支援](/help/components/dimensions/cookie-support.md)維度的變數。<br>Y：啟用<br>N：停用<br>U：未知 | char(1) |
| **`country`** | 數值 ID 代表 `country.tsv` 查詢中找到的值。 | 不帶正負號的 smallint |
| **`ct_connect_type`** | 和`connection_type`欄相關。最常見的值是 LAN/Wifi、行動電信業者和數據機。 | char(20) |
| **`curr_factor`** | 決定貨幣小數位數，並用於貨幣轉換。例如，USD 使用兩個小數位數，因此該欄值為 2。 | tinyint |
| **`curr_rate`** | 交易發生當時的匯率。Adobe 與 XE 合作，以決定當日匯率。 | decimal(24,12) |
| **`currency`** | 交易期間使用的貨幣代碼。 | char(8) |
| **`cust_hit_time_gmt`** | 僅限啟用時間戳記的報告套裝。時間戳記根據 UNIX® 時間隨點擊傳送。 | int |
| **`cust_visid`** | 如果已設定自訂訪客 ID，則會填入此欄。 | varchar(255) |
| **`daily_visitor`** | 確定點擊是否為新每日訪客的旗標。 | 不帶正負號的 tinyint |
| **`dataprivacyconsentoptin`** | 在[同意管理選擇加入](/help/components/dimensions/cm-opt-in.md)維度中使用的變數。每個點擊可以有多個值，以垂直號 (`\|`) 分隔。有效值包括 `DMP` 和 `SELL`。 | varchar(100) |
| **`dataprivacyconsentoptout`** | 在[同意管理選擇退出](/help/components/dimensions/cm-opt-out.md)維度中使用的變數。每個點擊可以有多個值，以垂直號 (`\|`) 分隔。有效值包括 `SSF`、`DMP` 和 `SELL`。 | varchar(100) |
| **`dataprivacydmaconsent`** | 此值識別是否需要同意才能從 Adobe Analytics 透過 Adobe Advertising 將資料傳送到第三方廣告提供者 (例如 Google)。如需詳細資訊，請參閱[廣告同意](/help/components/dimensions/ad-consent.md)。 | varchar(100) |
| **`date_time`** | 可讀格式的點擊時間，根據報告套裝的時區而定。 | 日期時間 |
| **`domain`** | 用於[網域](/help/components/dimensions/domain.md)維度的變數。根據訪客的網際網路存取點而定。 | varchar(100) |
| **`duplicate_events`** | 列出每個計為重複項目的事件。 | varchar(255) |
| **`duplicate_purchase`** | 此旗標可指出此點擊的購買事件因為重複而被忽略。 | 不帶正負號的 tinyint |
| **`duplicated_from`** | 僅用於包含點擊複製 VISTA 規則的報告套裝。指出從中複製點擊的報告套裝。 | varchar(40) |
| **`ef_id`** | `ef_id`用於 Adobe Advertising 整合。 | varchar(255) |
| **`evar1 - evar250`** | 自訂變數 1-250。用於[eVar](/help/components/dimensions/evar.md)維度。每個組織使用不同的 eVar。如需關於貴組織如何填入各 eVar 的更多資訊，請參閱貴組織專用的解決方案設計文件。 | varchar(255) |
| **`event_list`** | 以逗號分隔的數值 ID 清單，代表點擊觸發的事件。包括預設事件和自訂事件 1-1000。使用`event.tsv`查詢。 | 文字 |
| **`exclude_hit`** | 表示該點擊已從報表中排除的旗標。此`visit_num`欄不會因排除的點擊而遞增。<br>1：未使用。屬於已報廢功能。<br>2：未使用。屬於已報廢功能。<br>3：已不再使用。用戶代理排除<br>4：依據 IP 位址的排除<br>5：遺失重要點擊資訊，例如`page_url`、`pagename`、`page_event`、或者`event_list`<br>6：JavaScript 沒有正確處理點擊<br>7：特定帳戶的排除，例如在 Vista 規則中<br>8：未使用。替代帳戶特定排除。<br>9：未使用。屬於已報廢功能。<br>10：無效的貨幣代碼<br>11：僅時間戳記報告套裝上遺失時間戳記的點擊，或非時間戳記報告套裝上包含時間戳記的點擊<br>12：未使用。屬於已報廢功能。<br>13：未使用。屬於已報廢功能。<br>14：不符合 Analytics 點擊的 Target 點擊<br>15：目前未使用。<br>16：不符合 Analytics 點擊的 Advertising Cloud 點擊 | 不帶正負號的 tinyint |
| **`first_hit_page_url`** | 訪客的第一個 URL。 | varchar(255) |
| **`first_hit_pagename`** | 用於[登入頁面原始](/help/components/dimensions/entry-dimensions.md)維度的變數。訪客的原始登入頁面名稱。 | varchar(100) |
| **`first_hit_ref_domain`** | 用於[原始反向連結網域](/help/components/dimensions/original-referring-domain.md)維度的變數。根據`first_hit_referrer`而定。訪客的第一個反向連結網域。 | varchar(100) |
| **`first_hit_ref_type`** | 表示訪客第一個反向連結的反向連結類型數值 ID。使用`referrer_type.tsv`查詢。 | 不帶正負號的 tinyint |
| **`first_hit_referrer`** | 訪客的第一個反向連結 URL。 | varchar(255) |
| **`first_hit_time_gmt`** | 訪客初次點擊的時間戳記 (根據 UNIX® 時間)。 | int |
| **`geo_city`** | 根據 IP 的點擊來源城市名稱。用於[城市](/help/components/dimensions/cities.md)維度。 | char(32) |
| **`geo_country`** | 根據 IP 的點擊來源國家/地區縮寫。用於[國家/地區](/help/components/dimensions/countries.md)維度。 | char(4) |
| **`geo_dma`** | 根據 IP 的點擊來源人口統計區域數值 ID。用於 [美國 DMA](/help/components/dimensions/us-dma.md) 維度。 | 不帶正負號的 int |
| **`geo_region`** | 根據 IP 的點擊來源州或地區名稱。用於[地區](/help/components/dimensions/regions.md)維度。 | char(32) |
| **`geo_zip`** | 點擊來源的郵遞區號 (根據 IP 位址)。協助填入[郵遞區號](/help/components/dimensions/zip-code.md)維度。另請參閱`zip`。 | varchar(16) |
| **`hier1 - hier5`** | 由階層變數使用。包含使用分隔符號的值清單。在報告套裝設定下選擇分隔符號。 | varchar(255) |
| **`hit_source`** | 表示點擊的來源。點擊來源 1、2 和 6 需計費。<br>1：沒有時間戳記的標準影像要求<br>2：具有時間戳記的標準影像要求<br>3：具有時間戳記的即時資料來源上傳<br>4：未使用<br>5：通用資料來源上傳<br>6：完整處理資料來源上傳<br>7：TransactionID 資料來源上傳<br>8：不再使用；舊版 Adobe Advertising Cloud 資料來源 <br>9：已不再使用；Adobe Social 摘要量度<br>10：使用 Audience Manager 伺服器端轉送 | 不帶正負號的 tinyint |
| **`hit_time_gmt`** | Adobe 資料收集伺服器收到點擊的時間戳記 (根據 UNIX® 時間)。 | int |
| **`hitid_high`** | 搭配 `hitid_low` 使用來識別點擊。 | 不帶正負號的 bigint |
| **`hitid_low`** | 搭配 `hitid_high` 使用來識別點擊。 | 不帶正負號的 bigint |
| **`homepage`** | 已不再使用。指出目前 URL 是否為瀏覽器的首頁。 | char(1) |
| **`hourly_visitor`** | 此旗標可確定點擊是否為每小時的新訪客。 | 不帶正負號的 tinyint |
| **`ip`** | IPv4 位址，根據影像請求 HTTP 標頭。與 `ipv6` 互斥；如果此欄包含非模糊 IP 位址，`ipv6` 為空白。 | char(20) |
| **`ip2`** | 未使用。報告套裝的後端參考變數，包含以 IP 位址為基礎的 VISTA 規則。 | char(20) |
| **`ipv6`** | 壓縮的 IPv6 位址 (若有)。與 `ip` 互斥；如果此欄包含非模糊 IP 位址，`ip` 為空白。 | varchar(40) |
| **`j_jscript`** | 瀏覽器支援的 JavaScript 版本。 | char(5) |
| **`java_enabled`** | 此旗標可指出是否已啟用 Java。<br>Y：啟用 <br>N：停用 <br>U：未知 | char(1) |
| **`javascript`** | 依據`j_jscript` JavaScript 版的查詢 ID。請參考`javascript_version`查詢表。 | 不帶正負號的 tinyint |
| **`language`** | 語言的數值 ID。使用`languages.tsv`查詢表。 | 不帶正負號的 smallint |
| **`last_hit_time_gmt`** | 先前點擊的時間戳記 (根據 UNIX® 時間)。用於計算[和上次造訪間隔天數](/help/components/dimensions/days-since-last-visit.md)維度。 | int |
| **`last_purchase_num`** | 用於[客戶忠誠度](/help/components/dimensions/customer-loyalty.md)維度的變數。訪客之前已購買的次數。<br>0：沒有先前購買 (非客戶) <br>1：先前購買 1 次 (新客戶) <br>2：先前購買 2 次 (回頭客戶) <br>3：先前購買 3 次以上 (忠實客戶) | 不帶正負號的 int |
| **`last_purchase_time_gmt`** | 用於[和上次購買間隔天數](/help/components/dimensions/days-since-last-purchase.md)維度。上次進行購買的時間戳記 (根據 UNIX® 時間)。對於首次購買和之前未購買的訪客，此值為 `0`。 | int |
| **`latlon1`** | 位置 (10 公里以內) | varchar(255) |
| **`latlon23`** | 位置 (100 公尺以內) | varchar(255) |
| **`latlon45`** | 位置 (1 公尺以內) | varchar(255) |
| **`mc_audiences`** | 訪客所屬的 Audience Manager 區段 ID 清單。`post_mc_audiences` 欄會將分隔符號變更為 `--**--`。 | 文字 |
| **`mcvisid`** | Experience Cloud 訪客 ID。128 位元的數字，由兩個串連的 64 位元數字組成，兩個數字皆補至 19 位數。 | varchar(255) |
| **`mobile_id`** | 如果使用者使用行動裝置，則為裝置的數值 ID。`mobile_attributes.tsv` [動態查詢](dynamic-lookups.md)的索引鍵值。 | int |
| **`mobileaction`** | 行動動作。在行動服務中呼叫`trackAction`時自動收集。允許應用程式中的自動動作路徑。 | varchar(100) |
| **`mobileappid`** | 行動應用程式 ID。以下列格式儲存應用程式名稱和版本：`[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | 用於 Apteligent 資料連接器。Apteligent 中使用的應用程式 ID。 | varchar(255) |
| **`mobileappperformancecrashid`** | 用於 Apteligent 資料連接器。Apteligent 中使用的當機 ID。 | varchar(255) |
| **`mobileappstoreobjectid`** | 用於 Appfigures 資料連接器。應用程式商店物件 ID。 | varchar(255) |
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
| **`mobiledayssincelastupgrade`** | 已淘汰 - 從內容資料變數 a.DaysSinceLastUpgrade 收集。 自上次作業階段以來已經過的天數。 | varchar(255) |
| **`mobiledayssincelastuse`** | 自應用程式上次執行以來的天數。 | varchar(255) |
| **`mobiledeeplinkid`** | 從內容資料變數`a.deeplink.id`中收集。用於贏取報表中，作為行動贏取連結的識別碼。 | varchar(255) |
| **`mobiledevice`** | 行動裝置名稱。在 iOS 上，此名稱以逗號分隔的 2 位數字串形式儲存。第一個數字代表裝置代別，第二個數字代表裝置系列。 | varchar(255) |
| **`mobilehourofday`** | 定義一天當中啟動應用程式的時段。請依照 24 小時數字格式。 | varchar(255) |
| **`mobileinstalldate`** | Mobile 安裝日期。提供使用者初次開啟行動應用程式的日期。 | varchar(255) |
| **`mobilelaunchessincelastupgrade`** | 已淘汰 - 從內容資料變數 a.LaunchesSinceUpgrade 收集。 報表自上次升級以來的啟動次數。 | varchar(255) |
| **`mobilelaunchnumber`** | 每次啟動行動應用程式時增加 1。 | varchar(255) |
| **`mobileltv`** | 已不再使用。由 trackLifetimeValue 方法填入。 | varchar(255) |
| **`mobilemessagebuttonname`** | 從內容資料變數`a.message.button.id`中收集。用於應用程式內傳訊，以識別關閉訊息的按鈕。 | varchar(100) |
| **`mobilemessageid`** | 應用程式內訊息 ID | varchar(255) |
| **`mobilemessageonline`** | 線上應用程式內訊息 | varchar(255) |
| **`mobilemessagepushoptin`** | 從內容資料變數`a.push.optin`中收集。當使用者選擇加入推播訊息時，設為「true」；否則，值為「false」。 | varchar(255) |
| **`mobilemessagepushpayloadid`** | 從內容資料變數`a.push.payloadid`中收集。用於推播訊息中，作為裝載識別碼。 | varchar(255) |
| **`mobileosenvironment`** | 已淘汰 - 從內容資料變數`a.OSEnvironment`中收集。 表明 OS 環境，例如 Android 或 iOS。 | varchar(255) |
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
| **`monthly_visitor`** | 此旗標可標示當月的不重複訪客。 | 不帶正負號的 tinyint |
| **`mvvar1`** - `mvvar3` | 清單變數值。根據實施包含使用分隔符號的自訂值清單。`post_mvvar1` - `post_mvvar3` 欄會以 `--**--` 取代原始的分隔符號。 | 文字 |
| **`mvvar1_instances`** - `mvvar3_instances` | 在目前點擊上設定的清單變數值。以 `--**--` 取代原始的分隔符號。沒有 `post` 欄。 | 文字 |
| **`namespace`** | 未使用。屬於已報廢功能。 | varchar(50) |
| **`new_visit`** | 此旗標可確定目前的點擊是否為新造訪。造訪閒置 30 分鐘後，由 Adobe 伺服器設定。 | 不帶正負號的 tinyint |
| **`os`** | 表示訪客的作業系統的數值 ID。依據`user_agent`欄而定。`operating_system.tsv`標準查詢和`operating_system_type.tsv`[動態查詢](dynamic-lookups.md)的索引鍵值。 | 不帶正負號的 int |
| **`p_plugins`** | 已不再使用。瀏覽器可用的外掛程式清單。 使用的 JavaScript 函數 `navigator.plugins()`。 | 文字 |
| **`page_event`** | 影像要求中傳送的點擊類型 (標準點擊、下載連結、自訂連結、退出連結)。請參閱[頁面事件查閱](datafeeds-page-event.md)。 | 不帶正負號的 tinyint |
| **`page_event_var1`** | 僅用於連結追蹤影像要求。點按之下載連結、退出連結或自訂連結的 URL。 | 文字 |
| **`page_event_var2`** | 僅用於連結追蹤影像要求。連結的自訂名稱 (若有)。 | varchar(100) |
| **`page_event_var3`** | 已不再使用。包含調查和媒體模組資料。使用舊版 Adobe Analytics 填入的舊版影片報告。 | 文字 |
| **`page_type`** | 用於填入[找不到頁面](/help/components/dimensions/pages-not-found.md)維度。專用於 404 頁。此變數應該為空白或包含值`ErrorPage`。 | char(20) |
| **`page_url`** | 點擊的 URL。請注意，`post_page_url` 被卸除連結追踪影像請求並使用 varchar(255) 的資料類型。 | 文字 |
| **`pagename`** | 用於填入[頁面](/help/components/dimensions/page.md)維度。如果[`pagename`](/help/implement/vars/page-vars/pagename.md)變數為空白，Analytics 會改用`page_url`。 | varchar(100) |
| **`pagename_no_url`** | 與 `pagename` 類似，但不會回復到 `page_url`。只有 `post` 列適用。 | varchar(100) |
| **`paid_search`** | 如果點擊符合付費搜尋偵測，則會設定此旗標。 | 不帶正負號的 tinyint |
| **`partner_plugins`** | 未使用。屬於已報廢功能。 | varchar(255) |
| **`persistent_cookie`** | 用於[持續性 Cookie 支援](/help/components/dimensions/persistent-cookie-support.md)維度。指出訪客是否支援每次點擊後未捨棄的 Cookie。 | char(1) |
| **`plugins`** | 已不再使用。與瀏覽器中可用外掛程式對應的數值ID清單。 使用`plugins.tsv`查詢。 | varchar(180) |
| **`pointofinterest`** | 行動服務興趣點名稱 | varchar(255) |
| **`pointofinterestdistance`** | 行動服務與興趣點中心的距離 | varchar(255) |
| **`post_`**&#x200B;欄 | 包含報表中最終使用的值。每個後置欄會填入伺服器端邏輯、處理規則和 VISTA 規則之後。Adobe 建議在大多數情況下使用後置欄。 | 請參閱各個非後置欄 |
| **`prev_page`** | 未使用。前一頁的 Adobe 專有識別碼。 | 不帶正負號的 int |
| **`product_list`** | 透過[`products`](/help/implement/vars/page-vars/products.md)變數傳入的產品清單。產品是以逗號分隔，而個別產品屬性是由分號分隔。 | 文字 |
| **`product_merchandising`** | 未使用。請改用 `product_list`。 | 文字 |
| **`prop1`** - `prop75` | 自訂流量變數 1 - 75。用於 [Prop](/help/components/dimensions/prop.md) 維度。 | varchar(100) |
| **`purchaseid`** | 使用[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)變數設定之購買的唯一識別碼。由`duplicate_purchase`欄使用。 | char(20) |
| **`quarterly_visitor`** | 此旗標可確定點擊是否為每季新訪客。 | 不帶正負號的 tinyint |
| **`ref_domain`** | 根據反向連結欄而定。點擊的反向連結網域。用於[反向連結網域](/help/components/dimensions/referring-domain.md)維度。 | varchar(100) |
| **`ref_type`** | 表示點擊的反向連結類型的數值 ID。用於[反向連結類型](/help/components/dimensions/referrer-type.md)維度。<br>1：網站內<br>2：其他網站 <br>3：搜尋引擎 <br>4：硬碟 <br>5：USENET <br>6：分類/建立書籤 (無反向連結) <br>7：電子郵件 <br>8：無 JavaScript <br>9：社交網路 | 不帶正負號的 tinyint |
| **`referrer`** | 上一頁的頁面 URL。用於[反向連結](/help/components/dimensions/referrer.md)維度。請注意，雖然 `referrer` 使用 varchar(255) 資料類型，但 `post_referrer` 是使用 varchar(244) 資料類型。 | varchar(255) |
| **`resolution`** | 表示螢幕解析度的數值 ID。用於[螢幕解析度](/help/components/dimensions/monitor-resolution.md)維度。使用`resolution.tsv`查詢表。 | 不帶正負號的 smallint |
| **`s_kwcid`** | 用於 Adobe Advertising 整合的關鍵字 ID。 | varchar(255) |
| **`s_resolution`** | 原始螢幕解析度值。使用 JavaScript 函數`screen.width x screen.height`收集。 | char(20) |
| **`search_engine`** | 表示將訪客反向連結至您的網站的搜尋引擎數值 ID。使用`search_engines.tsv`查詢。 | 不帶正負號的 smallint |
| **`search_page_num`** | 由[所有搜尋頁面排名](/help/components/dimensions/all-search-page-rank.md)維度使用。在使用者點進您的網站之前，指示您的網站要顯示哪個搜尋結果頁面。 | 不帶正負號的 smallint |
| **`secondary_hit`** | 用於追蹤次要點擊的旗標。通常源自複製點擊的多套裝加註標籤和 VISTA 規則。 | 不帶正負號的 tinyint |
| **`service`** | 未使用。請改用 `page_event`。 | char(2) |
| **`socialaccountandappids`** | 已不再使用。社交帳戶和應用程式 ID | varchar(255) |
| **`socialassettrackingcode`** | 已不再使用。社交促銷活動變數 | varchar(255) |
| **`socialauthor`** | 已不再使用。社交作者變數 | varchar(255) |
| **`socialcontentprovider`** | 已不再使用。社交平台/屬性 | varchar(255) |
| **`socialinteractiontype`** | 已不再使用。社交互動類型 | varchar(255) |
| **`sociallanguage`** | 已不再使用。社交語言 | varchar(255) |
| **`sociallatlong`** | 已不再使用。社交緯度/經度 | varchar(255) |
| **`socialowneddefinitioninsighttype`** | 已不再使用。社交擁有的定義分析類型 | varchar(255) |
| **`socialowneddefinitioninsightvalue`** | 已不再使用。社交擁有的定義分析值 | varchar(255) |
| **`socialowneddefinitionmetric`** | 已不再使用。社交擁有的定義量度 | varchar(255) |
| **`socialowneddefinitionpropertyvspost`** | 已不再使用。社交擁有的定義屬性與貼文 | varchar(255) |
| **`socialownedpostids`** | 已不再使用。社交擁有的貼文 ID | varchar(255) |
| **`socialownedpropertyid`** | 已不再使用。社交擁有的屬性 ID | varchar(255) |
| **`socialownedpropertyname`** | 已不再使用。社交擁有的屬性名稱 | varchar(255) |
| **`socialownedpropertypropertyvsapp`** | 已不再使用。社交擁有的屬性與應用程式 | varchar(255) |
| **`sourceid`** | 來源 ID | 不帶正負號的 int |
| **`state`** | State 變數。 | varchar(50) |
| **`stats_server`** | 未使用。處理點擊的 Adobe 內部伺服器。 | char(30) |
| **`survey`** | 已不再使用。Adobe Survey 變數。只有 `post` 列適用。 | 文字 |
| **`survey_instances`** | 已不再使用。Adobe Survey 執行個體變數。 | 文字 |
| **`t_time_info`** | 訪客的當地時間。格式為：`M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | 用於 Adobe Target 整合。 代表目前符合條件的所有測試。 格式為：`TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`。 | 文字 |
| **`tnt_action`** | 用於 Adobe Target 整合。 代表點擊合格的所有測試。 | 文字 |
| **`tnt_instances`** | 用於 Adobe Target 整合。 Target 執行個體變數。 | 文字 |
| **`tnt_post_vista`** | 已不再使用。請改用 `post_tnt`。 | 文字 |
| **`transactionid`** | 唯一識別碼，日後可透過資料來源上傳各種資料點。使用[`transactionID`](/help/implement/vars/page-vars/transactionid.md)變數收集。 | 文字 |
| **`truncated_hit`** | 此旗標代表影像要求已截斷。表示已收到部分點擊。<br>Y：點擊遭截斷；收到部分點擊 <br>N：點擊未截斷；收到完整點擊 | char(1) |
| **`ua_color`** | 已不再使用。先前作為色彩深度的後援。 | char(20) |
| **`ua_os`** | 已不再使用。先前作為作業系統的後援。 | char(80) |
| **`ua_pixels`** | 已不再使用。先前作為瀏覽器高度和寬度的後援。 | char(20) |
| **`user_agent`** | 傳入影像要求之 HTTP 標頭的使用者代理字串。 | 文字 |
| **`user_hash`** | 未使用。報告套裝 ID 上的雜湊.請改用 `username`。 | 不帶正負號的 int |
| **`user_server`** | 用於[伺服器](/help/components/dimensions/server.md)維度。 | varchar(100) |
| **`userid`** | 未使用。報告套裝 ID 的數值 ID。請改用 `username`。 | 不帶正負號的 int |
| **`username`** | 點擊的報告套裝 ID。 | char(40) |
| **`va_closer_detail`** | 用於[上次接觸詳情](/help/components/dimensions/last-touch-detail.md)維度的變數。 | varchar(255) |
| **`va_closer_id`** | 可識別[上次接觸通路](/help/components/dimensions/last-touch-channel.md)維度的數值 ID。可以在「行銷通路管理員」中找到此 ID 的查閱。 | 不帶正負號的 tinyint |
| **`va_finder_detail`** | 用於[首次接觸詳情](/help/components/dimensions/first-touch-detail.md)維度的變數。 | varchar(255) |
| **`va_finder_id`** | 可識別[首次接觸通路](/help/components/dimensions/first-touch-channel.md)維度的數值 ID。可以在「行銷通路管理員」中找到此 ID 的查閱。 | 不帶正負號的 tinyint |
| **`va_instance_event`** | 可識別行銷通路[執行個體數](/help/components/metrics/instances.md)的旗標。 | 不帶正負號的 tinyint |
| **`va_new_engagement`** | 可識別行銷通路[新增參與](/help/components/metrics/new-engagements.md)的旗標。 | 不帶正負號的 tinyint |
| **`video`** | 影片內容 | varchar(255) |
| **`videoad`** | 影片廣告名稱 | varchar(255) |
| **`videoadinpod`** | Pod 位置中的影片廣告 | varchar(255) |
| **`videoadlength`** | 影片廣告長度 | 整數 |
| **`videoadload`** | 影片廣告載入 | varchar(255) |
| **`videoadname`** | 影片廣告名稱 | varchar(255) |
| **`videoadplayername`** | 影片廣告播放器名稱 | varchar(255) |
| **`videoadpod`** | 影片廣告 Pod | varchar(255) |
| **`videoadvertiser`** | 影片廣告商 | varchar(255) |
| **`videoaudioalbum`** | 影音相簿 | varchar(255) |
| **`videoaudioartist`** | 影音藝人 | varchar(255) |
| **`videoaudioauthor`** | 影音作者 | varchar(255) |
| **`videoaudiolabel`** | 影音標籤 | varchar(255) |
| **`videoaudiopublisher`** | 影音發佈者 | varchar(255) |
| **`videoaudiostation`** | 影音電台 | varchar(255) |
| **`videocampaign`** | 影音促銷活動 | varchar(255) |
| **`videochannel`** | 影片頻道 | varchar(255) |
| **`videochapter`** | 影片章節名稱 | varchar(255) |
| **`videocontenttype`** | 影片內容類型。所有影片檢視會自動設為 &#39;Video&#39;。 | varchar(255) |
| **`videodaypart`** | 影片時段 | varchar(255) |
| **`videoepisode`** | 影片集數 | varchar(255) |
| **`videofeedtype`** | 影片輸出類型 | varchar(255) |
| **`videogenre`** | 影片類型 | 文字 |
| **`videolength`** | 影片長度 | 整數 |
| **`videomvpd`** | 影片 MVPD | varchar(255) |
| **`videoname`** | 影片名稱 | varchar(255) |
| **`videonetwork`** | 影片網路 | varchar(255) |
| **`videopath`** | 影片路徑 | varchar(100) |
| **`videoplayername`** | 影片播放器名稱 | varchar(255) |
| **`videotime`** | 視訊時間 | 整數 |
| **`videoqoebitrateaverageevar`** | 影片品質平均位元速率 | varchar(255) |
| **`videoqoebitratechangecountevar`** | 影片品質變更計數 | varchar(255) |
| **`videoqoebuffercountevar`** | 影片品質緩衝計數 | varchar(255) |
| **`videoqoebuffertimeevar`** | 影片品質緩衝時間 | varchar(255) |
| **`videoqoedroppedframecountevar`** | 影片品質掉格計數 | varchar(255) |
| **`videoqoeerrorcountevar`** | 影片品質錯誤計數 | varchar(255) |
| **`videoqoeextneralerrors`** | 影片品質外部錯誤 | 文字 |
| **`videoqoeplayersdkerrors`** | 影片品質 SDK 錯誤 | 文字 |
| **`videoqoetimetostartevar`** | 影片品質開始時間 | varchar(255) |
| **`videoseason`** | 影片季數 | varchar(255) |
| **`videosegment`** | 影片區段 | varchar(255) |
| **`videoshow`** | 影片節目 | varchar(255) |
| **`videoshowtype`** | 影片節目類型 | varchar(255) |
| **`videostreamtype`** | 影片串流類型 | varchar(255) |
| **`visid_high`** | 搭配 `visid_low` 使用，以唯一碼來識別一位訪客。 | 不帶正負號的 bigint |
| **`visid_low`** | 搭配 `visid_high` 使用，以唯一碼來識別一位訪客。 | 不帶正負號的 bigint |
| **`visid_new`** | 用於識別點擊是否包含新產生訪客 ID 的旗標。 | char(1) |
| **`visid_timestamp`** | 如果訪客 ID 為新產生，則會提供產生訪客 ID 時的時間戳記 (根據 UNIX® 時間)。 | int |
| **`visid_type`** | 不供外部使用；供 Adobe 在內部用來處理最佳化。此數值 ID 代表用來識別訪客的方法。<br>`0`：自訂訪客 ID 或未知/不適用<br>`1`：IP 和用戶代理備援<br>`2`：HTTP 行動訂閱者標題<br>`3`：舊版 Cookie 值 (`s_vi`) <br>`4`：備援 Cookie 值 (`s_fid`) <br>`5`：身分識別服務 | 不帶正負號的 tinyint |
| **`visit_keywords`** | 用於[搜尋關鍵字](/help/components/dimensions/search-keyword.md)維度的變數。此欄使用非標準字元限制 varchar(244) 來容納 Adobe 使用的後端邏輯。 | varchar(244) |
| **`visit_num`** | 用於[造訪數](/help/components/dimensions/visit-number.md)維度的變數。從 1 開始，隨著每次訪客開始新的造訪而遞增。 | 不帶正負號的 int |
| **`visit_page_num`** | 用於[點擊深度](/help/components/dimensions/hit-depth.md)維度的變數。對於使用者產生的每次點擊會增加 1。重設每次造訪。 | 不帶正負號的 int |
| **`visit_ref_domain`** | 依據`visit_referrer`欄而定。造訪的第一個反向連結網域。 | varchar(100) |
| **`visit_ref_type`** | 表示造訪的首次反向連結的反向連結類型數值 ID。使用`referrer_type.tsv`查詢表。 | 不帶正負號的 tinyint |
| **`visit_referrer`** | 造訪的第一個反向連結。 | varchar(255) |
| **`visit_search_engine`** | 造訪的第一個搜尋引擎數值 ID。使用`search_engines.tsv`查詢。 | 不帶正負號的 smallint |
| **`visit_start_page_url`** | 造訪的第一個 URL。 | varchar(255) |
| **`visit_start_pagename`** | 造訪首次點擊時的頁面名稱值。 | varchar(100) |
| **`visit_start_time_gmt`** | 造訪的第一次點擊時間戳記 (根據 UNIX® 時間)。 | int |
| **`weekly_visitor`** | 此旗標可確定點擊是否為每週新訪客。 | 不帶正負號的 tinyint |
| **`yearly_visitor`** | 此旗標可確定點擊是否為每年新訪客。 | 不帶正負號的 tinyint |
| **`zip`** | 協助填入[郵遞區號](/help/components/dimensions/zip-code.md)維度。另請參閱 `geo_zip`。 | varchar(50) |

## 空白欄

下列清單為未使用的欄，因此不包含資料：

* `adclassificationcreative`
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
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
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
