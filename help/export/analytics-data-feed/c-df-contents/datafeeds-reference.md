---
description: 說明資料摘要中欄的表格資料。
keywords: Data Feed;columns
subtopic: data feeds
title: 資料欄參考
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 資料欄參考

參閱本頁內容，了解各欄包含哪些資料。大部分實施不會用到每一欄，因此在決定要將哪些欄包含在資料摘要匯出中時，可參考此頁面。

>[!IMPORTANT] 對於所有欄位 (例如定義為 255 個字元的欄位)，資料摘要可能會因為字串中多了字元逸出值而傳送額外的字元。如果您的實施經常會傳送超過字元限制的值，請注意可能是這些可能的額外字元所致。

## 欄、說明和資料類型

>[!NOTE] 大多數欄包含類似的欄，其前置詞為 `post_`。後置欄包含伺服器端邏輯、處理規則和 VISTA 規則之後的值。Adobe 建議在大多數情況下使用後置欄。如需詳細資訊，請參閱[資料摘要常見問題集](../df-faq.md)。

| 欄名稱 | 欄說明 | 資料類型 |
| --- | --- | --- |
| `accept_language` | 列出所有接受的語言，如影像要求中的「接受語言HTTP」標題所示。 | char(20) |
| `aemassetid` | 與一組Adobe Experience Manager資產的資產ID(GUID)對應的多值變數。 遞增曝光事件。 | text |
| `aemassetsource` | 識別資產事件的來源。 用於Adobe Experience Manager。 | varchar(255) |
| `aemclickedassetid` | Adobe Experience Manager資產的資產ID。 遞增點按事件。 | varchar(255) |
| `browser` | 瀏覽器的數值ID。 參考browser.tsv查閱表格。 | 不帶正負號的 int |
| `browser_height` | 瀏覽器視窗的高度 (像素)。 | 不帶正負號的 smallint |
| `browser_width` | 瀏覽器視窗的寬度 (像素)。 | 不帶正負號的 smallint |
| `c_color` | 色盤的位元深度。 用於計算「顏色深度」尺寸。 使用JavaScript函式screen.colorDepth()。 | char(20) |
| `campaign` | 用於追蹤代碼維度的變數。 | varchar(255) |
| `carrier` | Adobe Advertising Cloud整合變數。 指定行動電信業者。 參考電信業者查閱表格。 | varchar(100) |
| `channel` | 用於「網站區域」維度的變數。 | varchar(100) |
| `click_action` | 已不再使用。在舊版Clickmap工具中點按的連結位址。 | varchar(100) |
| `click_action_type` | 已不再使用。舊版Clickmap工具的連結類型。<br>0：HREF URL<br>1：自訂 ID<br>2：JavaScript onClick 事件<br>3：表單元素 | 不帶正負號的 tinyint |
| `click_context` | 已不再使用。發生連結點按的頁面名稱。 舊版Clickmap工具的一部分。 | varchar(255) |
| `click_context_type` | 已不再使用。指出click_context是否具有頁面名稱或預設為頁面URL。<br>0：頁面 URL<br>1：頁面名稱 | 不帶正負號的 tinyint |
| `click_sourceid` | 已不再使用。已點按連結頁面上位置的數值ID。 舊版Clickmap工具的一部分。 | 不帶正負號的 int |
| `click_tag` | 已不再使用。已點按的HTML元素類型。 | char(10) |
| `clickmaplink` | Activity Map 連結 | varchar(255) |
| `clickmaplinkbyregion` | Activity Map 連結 (依地區) | varchar(255) |
| `clickmappage` | Activity Map 頁面 | varchar(255) |
| `clickmapregion` | Activity Map 地區 | varchar(255) |
| `code_ver` | 用於編譯和傳送影像要求的AppMeasurement程式庫版本。 | char(16) |
| `color` | 根據c_color欄的值，色深ID。 參考color_depth.tsv查閱表格。 | 不帶正負號的 smallint |
| `connection_type` | 代表連線類型的數值ID。 用於「連接類型」維的變數。 參考connection_type.tsv查閱表格。 | 不帶正負號的 tinyint |
| `cookies` | 用於Cookie支援維度的變數。<br>Y：啟用<br>N：停用<br>U：未知 | char(1) |
| `country` | 代表點擊所來國家的數值ID。 Adobe與Digital Envoy合作，將IP位址與國家／地區相符。 使用country.tsv查閱。 | 不帶正負號的 smallint |
| `ct_connect_type` | 與connection_type列相關。 最常見的值是LAN/Wifi、Mobile Carrier和Modem。 | char(20) |
| `curr_factor` | 確定貨幣小數位數，並用於貨幣兌換。 例如，USD使用兩個小數位，因此此列值應為2。 | tinyint |
| `curr_rate` | 交易發生時的匯率。 Adobe與XE合作決定當天的匯率。 | decimal(24,12) |
| `currency` | 交易期間使用的貨幣代碼。 | char(8) |
| `cust_hit_time_gmt` | 僅啟用時間戳記的報表套裝。 隨點擊傳送的時間戳記，以Unix時間為基礎。 | int |
| `cust_visid` | 如果設定了自訂訪客ID，則會填入此欄。 | varchar(255) |
| `daily_visitor` | 用以判斷點擊是否為新每日訪客的旗標。 | 不帶正負號的 tinyint |
| `date_time` | 根據報表套裝的時區，以可讀格式顯示點擊的時間。 | 日期時間 |
| `domain` | 用於「網域」維度的變數。 根據使用者的網際網路服務供應商(ISP)。 | varchar(100) |
| `duplicate_events` | 列出每個被計為重複的事件。 | varchar(255) |
| `duplicate_purchase` | 指出此點擊的購買事件應被忽略的旗標，因為該事件是重複的。 | 不帶正負號的 tinyint |
| `duplicated_from` | 僅用於包含點擊復本VISTA規則的報表套裝。 指出點擊是從哪個報表套裝複製的。 | varchar(40) |
| `ef_id` | Adobe Advertising Cloud整合中使用的ef_id。 | varchar(255) |
| `evar1 - evar250` | 自訂變數1-250。 每個組織使用eVar的方式都不同。 有關組織如何填入各eVar的詳細資訊，最適合的地方是您組織專屬的解決方案設計檔案。 | varchar(255) |
| `event_list` | 以逗號分隔的數值ID清單，代表點擊時觸發的事件。 同時包含預設事件和自訂事件1-1000。 使用event.tsv查閱。 | text |
| `exclude_hit` | 指出點擊已排除在報告之外的旗標。 visit_num 欄不會因為排除的點擊而增加。<br>1：未使用。屬於已報廢功能。<br>2：未使用。屬於已報廢功能。<br>3：已不再使用。排除使用者代理<br>4：根據 IP 位址排除<br>5：遺失重要點擊資訊，例如 page_url、pagename、page_event 或 event_list<br>6：JavaScript 無法正確處理點擊<br>7：帳戶特定排除，例如在 VISTA 規則中<br>8：未使用。替代帳戶特定排除。<br>9：未使用。屬於已報廢功能。<br>10：無效的貨幣代碼<br>11：僅時間戳記報表套裝上遺失時間戳記的點擊，或非時間戳記報表套裝上包含時間戳記的點擊<br>12：未使用。屬於已報廢功能。<br>13：未使用。屬於已報廢功能。<br>14：不符合 Analytics 點擊的 Target 點擊<br>15：目前未使用。<br>16：不符合 Analytics 點擊的 Advertising Cloud 點擊 | 不帶正負號的 tinyint |
| `first_hit_page_url` | 訪客的第一個URL。 | varchar(255) |
| `first_hit_pagename` | 用於「登入頁面原始」維度的變數。 訪客的原始登入頁面名稱。 | varchar(100) |
| `first_hit_ref_domain` | 用於「原始反向連結網域」維度的變數。 根據first_hit_referrer。 訪客的第一個反向連結網域。 | varchar(100) |
| `first_hit_ref_type` | 代表訪客第一個反向連結反向連結類型的數值ID。 使用referrer_type.tsv查閱。 | 不帶正負號的 tinyint |
| `first_hit_referrer` | 訪客的第一個反向連結URL。 | varchar(255) |
| `first_hit_time_gmt` | 訪客在Unix時間內首次點擊的時間戳記。 | int |
| `geo_city` | 根據IP，點擊來自的城市名稱。 Adobe與Digital Envoy合作，將IP位址與城市相符。 | char(32) |
| `geo_country` | 根據IP，點擊來源國家的縮寫。 Adobe與Digital Envoy合作，將IP位址與國家／地區相符。 | char(4) |
| `geo_dma` | 點擊來自的人口統計區域數值ID（根據IP）。 Adobe與Digital Envoy合作，將IP位址與人口統計區域相符。 | 不帶正負號的 int |
| `geo_region` | 點擊來自的州或地區名稱（根據IP）。 Adobe與Digital Envoy合作，將IP位址與州／地區相符。 | char(32) |
| `geo_zip` | 點擊的來源郵遞區號 (根據 IP)。Adobe與Digital Envoy合作，將IP位址與郵遞區號相符。 | varchar(16) |
| `hier1 - hier5` | 階層變數使用。 包含分隔字元的值清單。 分隔字元是在報表套裝設定下選擇。 | varchar(255) |
| `hit_source` | 指出點擊來源。<br>1：沒有時間戳記的標準影像請求<br>2：具有時間戳記的標準影像請求<br>3：具有時間戳記的即時資料來源上傳<br>4：未使用<br>5：通用資料來源上傳<br>6：完整處理資料來源上傳<br>7：TransactionID 資料來源上傳<br>8：不再使用；舊版 Adobe Advertising Cloud 資料來源 <br>9：已不再使用；Adobe Social 摘要量度 | 不帶正負號的 tinyint |
| `hit_time_gmt` | Adobe 資料收集伺服器收到點擊的點擊時間戳記 (根據 Unix 時間)。 | int |
| `hitid_high` | 與hitid_low搭配使用，以唯一識別點擊。 | 不帶正負號的 bigint |
| `hitid_low` | 與hitid_high搭配使用，以唯一識別點擊。 | 不帶正負號的 bigint |
| `homepage` | 已不再使用。指出目前的URL是否為瀏覽器的首頁。 | char(1) |
| `hourly_visitor` | 用以判斷點擊是否為新每小時訪客的旗標。 | 不帶正負號的 tinyint |
| `ip` | IP位址，根據影像要求的HTTP標題。 | char(20) |
| `ip2` | 未使用。根據IP位址包含VISTA規則之報表套裝的後端參考變數。 | char(20) |
| `j_jscript` | 瀏覽器支援的JavaScript版本。 | char(5) |
| `java_enabled` | 此旗標用於指出是否已啟用 Java。<br>Y：啟用 <br>N：停用 <br>U：未知 | char(1) |
| `javascript` | 基於j_jscript的JavaScript版本查閱ID。 使用查閱表格。 | 不帶正負號的 tinyint |
| `language` | 語言的數值ID。 使用languages.tsv查閱表格。 | 不帶正負號的 smallint |
| `last_hit_time_gmt` | 先前點擊的時間戳記（在Unix時間）。 用於計算「自上次瀏覽起的天數」維度。 | int |
| `last_purchase_num` | 用於「客戶忠誠度」維度的變數。 表示訪客之前的購買次數。<br>0：沒有先前購買 (非客戶) <br>1：先前購買 1 次 (新客戶) <br>2：先前購買 2 次 (回頭客戶) <br>3：先前購買 3 次以上 (忠實客戶) | 不帶正負號的 int |
| `last_purchase_time_gmt` | 用於「上次購買間隔天數」維。 上次購買的時間戳記（在Unix時間）。 對於首次購買和之前未進行購買的訪客，此值為0。 | int |
| `latlon1` | 位置 (10 公里以內) | varchar(255) |
| `latlon23` | 位置 (100 公尺以內) | varchar(255) |
| `latlon45` | 位置 (1 公尺以內) | varchar(255) |
| `mc_audiences` | 訪客所屬的Audience Manager區段ID清單。 | text |
| `mcvisid` | Experience Cloud 訪客 ID. 128位元數，由兩個串連的64位元數字組成，以19位元補充。 | varchar(255) |
| `mobile_id` | 如果使用者使用行動裝置，則為裝置的數值 ID。 | int |
| `mobileaction` | 行動行動。 在行動服務中呼叫 trackAction 時自動收集。允許應用程式中的自動動作路徑。 | varchar(100) |
| `mobileappid` | 行動應用程式ID。 以下列格式儲存應用程式名稱和版本: [AppName] [BundleVersion] | varchar(255) |
| `mobileappperformanceappid` | 用於 Apteligent 資料連接器。Apteligent 中使用的應用程式 ID。 | varchar(255) |
| `mobileappperformancecrashid` | 用於 Apteligent 資料連接器。Apteligent 中使用的當機 ID。 | varchar(255) |
| `mobileappstoreobjectid` | 用於 Appfigures 資料連接器。App Store 物件 ID | varchar(255) |
| `mobilebeaconmajor` | 行動服務主要信標 | varchar(100) |
| `mobilebeaconminor` | 行動服務次要信標 | varchar(100) |
| `mobilebeaconproximity` | 行動服務鄰近地區信標 | varchar(255) |
| `mobilebeaconuuid` | 行動服務信標 UUID | varchar(100) |
| `mobilecampaigncontent` | 顯示連結之內容的名稱或ID。 由「行動應用程式贏取」填入。 | varchar(255) |
| `mobilecampaignmedium` | 行銷媒體，例如橫幅或電子郵件。 由「行動應用程式贏取」填入。 | varchar(255) |
| `mobilecampaignname` | 行銷活動名稱，亦儲存於行銷活動變數中。由「行動應用程式贏取」填入。 | varchar(255) |
| `mobilecampaignsource` | 原始反向連結，例如電子報或社交媒體網路。 由「行動應用程式贏取」填入。 | varchar(255) |
| `mobilecampaignterm` | 付費關鍵字或您要追蹤此贏取的其他詞語。 由「行動應用程式贏取」填入。 | varchar(255) |
| `mobiledayofweek` | 應用程式啟動的工作日數。 | varchar(255) |
| `mobiledayssincefirstuse` | 應用程式首次執行後的天數。 | varchar(255) |
| `mobiledayssincelastupgrade` | 從內容資料變數 a.DaysSinceLastUpgrade 收集。自上次作業階段以來已經過的天數。 | varchar(255) |
| `mobiledayssincelastuse` | 上次執行應用程式後的天數。 | varchar(255) |
| `mobiledeeplinkid` | 從內容資料變數 a.<span>deeplink</span>.id 收集。用於贏取報表中，作為行動贏取連結的識別碼。 | varchar(255) |
| `mobiledevice` | 行動裝置名稱。 在iOS上，它會儲存為逗號分隔的2位數字串。 第一數字代表裝置產生，第二數字代表裝置系列。 | varchar(255) |
| `mobilehourofday` | 定義應用程式啟動當天的某小時。 遵循24小時數值格式。 | varchar(255) |
| `mobileinstalldate` | 行動裝置安裝日期。 提供使用者第一次開啟行動應用程式的日期。 | varchar(255) |
| `mobilelaunchessincelastupgrade` | 從內容資料變數 a.LaunchesSinceUpgrade 收集。報表自上次升級以來的啟動次數。 | varchar(255) |
| `mobilelaunchnumber` | 每次啟動行動應用程式時，遞增一次。 | varchar(255) |
| `mobileltv` | 已不再使用。由 trackLifetimeValue 方法填入。 | varchar(255) |
| `mobilemessagebuttonname` | 從內容資料變數 a.<span>message</span>.button.id 收集。用於應用程式內傳訊，以識別關閉訊息的按鈕。 | varchar(100) |
| `mobilemessageid` | 應用程式內訊息 ID | varchar(255) |
| `mobilemessageonline` | 線上應用程式內訊息 | varchar(255) |
| `mobilemessagepushoptin` | 從內容資料變數 a.push.optin 收集。當使用者選擇加入推播訊息時，設為「true」；否則，值為「false」。 | varchar(255) |
| `mobilemessagepushpayloadid` | 從內容資料變數 a.push.payloadid 收集。用於推播訊息中，作為裝載識別碼。 | varchar(255) |
| `mobileosenvironment` | 從內容資料變數 a.OSEnvironment 收集。表明 OS 環境，例如 Android 或 iOS。 | varchar(255) |
| `mobileosversion` | 行動服務作業系統版本 | varchar(255) |
| `mobileplaceaccuracy` | 從內容資料變數 a.loc.acc 收集。指出 GPS 在採集時的準確度 (以公尺為單位)。 | varchar(255) |
| `mobileplacecategory` | 從內容資料變數 a.loc.category 收集。說明特定位置的類別。 | varchar(255) |
| `mobileplaceid` | 從內容資料變數 a.<span>loc</span>.id 收集。指定興趣點的識別碼。 | varchar(255) |
| `mobilerelaunchcampaigncontent` | 行動服務上市內容 | varchar(255) |
| `mobilerelaunchcampaignmedium` | 行動服務上市媒體 | varchar(255) |
| `mobilerelaunchcampaignsource` | 行動服務上市來源 | varchar(255) |
| `mobilerelaunchcampaignterm` | 行動服務上市條件 | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | 從內容資料變數 a.launch.campaign.trackingcode 收集。用於贏取中，作為上市促銷活動的追蹤代碼。 | varchar(255) |
| `mobileresolution` | 行動裝置的解析度。 寬度x高度（像素）。 | varchar(255) |
| `monthly_visitor` | 指出訪客是目前月份唯一的旗標。 | 不帶正負號的 tinyint |
| `mvvar1` - `mvvar3` | 列出變數值。 包含自訂值的分隔清單，視實作而定。 | text |
| `namespace` | 未使用。多年前，這項被廢棄的功能的一部分。 | varchar(50) |
| `new_visit` | 用以判斷目前點擊是否為新瀏覽的旗標。 在閒置30分鐘後由Adobe伺服器設定。 | 不帶正負號的 tinyint |
| `os` | 代表訪客作業系統的數值ID。 根據user_agent列。 使用作業系統查閱。 | 不帶正負號的 int |
| `p_plugins` | 已不再使用。瀏覽器可用的增效模組清單。 已使用JavaScript函式navigator.plugins()。 | text |
| `page_event` | 影像要求中傳送的點擊類型 (標準點擊、下載連結、自訂連結、退出連結)。請參閱[頁面事件查閱](datafeeds-page-event.md)。 | 不帶正負號的 tinyint |
| `page_event_var1` | 僅用於連結追蹤影像請求。 點按的下載連結、退出連結或自訂連結的URL。 | text |
| `page_event_var2` | 僅用於連結追蹤影像請求。 連結的自訂名稱（如果已指定）。 | varchar(100) |
| `page_event_var3` | 已不再使用。包含調查和媒體模組資料。 在舊版Adobe Analytics中填入舊版視訊報表。 | text |
| `page_type` | 用於填入「找不到頁面」維度，僅用於404頁面。 此變數應為空白或包含「ErrorPage」。 | char(20) |
| `page_url` | 點擊的URL。 未用於連結追蹤影像要求。 | varchar(255) |
| `pagename` | 用於填入「頁面」維度。 如果頁面名稱變數為空，Analytics會改用page_url。 | varchar(100) |
| `paid_search` | 如果點擊符合付費搜尋偵測，則設定的旗標。 | 不帶正負號的 tinyint |
| `partner_plugins` | 未使用。多年前，這項被廢棄的功能的一部分。 | varchar(255) |
| `persistent_cookie` | 由「永續性Cookie支援」維度使用。 指出訪客是否支援每次點擊後未捨棄的Cookie。 | char(1) |
| `plugins` | 已不再使用。對應至瀏覽器內可用外掛程式的數值ID清單。 使用plugins.tsv查閱。 | varchar(180) |
| `pointofinterest` | 行動服務興趣點名稱 | varchar(255) |
| `pointofinterestdistance` | 行動服務與興趣點中心的距離 | varchar(255) |
| `post_ columns` | 包含報表中最終使用的值。 每個後置欄會填入伺服器端邏輯、處理規則和VISTA規則之後。 Adobe 建議在大多數情況下使用後置欄。 | 請參閱個別的非貼文欄 |
| `prev_page` | 未使用。上一頁的Adobe專屬識別碼。 | 不帶正負號的 int |
| `product_list` | 透過產品變數傳入的產品清單。 產品以逗號分隔，個別產品屬性以分號分隔。 | text |
| `product_merchandising` | 未使用。請改用product_list。 | text |
| `prop1` - `prop75` | 自訂流量變數1-75。 | varchar(100) |
| `purchaseid` | 購買的唯一識別碼，如使用s_purchaseID變數所設定。 由duplicate_purchase欄使用。 | char(20) |
| `quarterly_visitor` | 用以判斷點擊是否為新每季訪客的旗標。 | 不帶正負號的 tinyint |
| `ref_domain` | 根據反向連結欄。 點擊的反向連結網域。 | varchar(100) |
| `ref_type` | 代表點擊之反向連結類型的數值ID。<br>1：網站內<br>2：其他網站 <br>3：搜尋引擎 <br>4：硬碟 <br>5：USENET <br>6：分類/建立書籤 (無反向連結) <br>7：電子郵件 <br>8：無 JavaScript <br>9：社交網路 | 不帶正負號的 tinyint |
| `referrer` | 上一頁的頁面URL。 請注意， `referrer` 雖然使用varchar(255)的資料類型， `post_referrer` 但使用varchar(244)的資料類型。 | varchar(255) |
| `resolution` | 代表螢幕解析度的數值ID。 填充「監視器解析度」維。 使用resolution.tsv查閱表格。 | 不帶正負號的 smallint |
| `s_kwcid` | 用於 Adobe Advertising Cloud 整合的關鍵字 ID。 | varchar(255) |
| `s_resolution` | 原始螢幕解析度值。 使用JavaScript函式screen.width x screen.height收集。 | char(20) |
| `sampled_hit` | 已不再使用。先前用於臨機分析中的取樣。 | char(1) |
| `search_engine` | 代表將訪客引薦至您網站之搜尋引擎的數值ID。 使用search_engines.tsv查閱。 | 不帶正負號的 smallint |
| `search_page_num` | 「所有搜尋頁面排名」維度使用。 指出您的網站在使用者點進您的網站之前所出現的搜尋結果頁面。 | 不帶正負號的 smallint |
| `secondary_hit` | 追蹤次要點擊的旗標。 通常源自複製點擊的多套裝標籤和VISTA規則。 | 不帶正負號的 tinyint |
| `service` | 未使用。請改用page_event。 | char(2) |
| `socialaccountandappids` | 已不再使用。Social帳戶和應用程式ID | varchar(255) |
| `socialassettrackingcode` | 已不再使用。社交促銷活動變數 | varchar(255) |
| `socialauthor` | 已不再使用。社交作者變數 | varchar(255) |
| `socialcontentprovider` | 已不再使用。社交平台 / 屬性 | varchar(255) |
| `socialinteractiontype` | 已不再使用。社交互動類型 | varchar(255) |
| `sociallanguage` | 已不再使用。社交語言 | varchar(255) |
| `sociallatlong` | 已不再使用。社交經緯度 | varchar(255) |
| `socialowneddefinitioninsighttype` | 已不再使用。社交擁有的定義分析類型 | varchar(255) |
| `socialowneddefinitioninsightvalue` | 已不再使用。社交擁有的定義分析值 | varchar(255) |
| `socialowneddefinitionmetric` | 已不再使用。社交擁有的定義量度 | varchar(255) |
| `socialowneddefinitionpropertyvspost` | 已不再使用。社交擁有的定義屬性與貼文 | varchar(255) |
| `socialownedpostids` | 已不再使用。社交擁有的貼文ID | varchar(255) |
| `socialownedpropertyid` | 已不再使用。社交擁有的屬性ID | varchar(255) |
| `socialownedpropertyname` | 已不再使用。社交擁有的屬性名稱 | varchar(255) |
| `socialownedpropertypropertyvsapp` | 已不再使用。社交擁有的屬性與應用程式 | varchar(255) |
| `state` | 狀態變數。 | varchar(50) |
| `stats_server` | 沒用。 處理點擊的 Adobe 內部伺服器。 | char(30) |
| `t_time_info` | 訪客的當地時間。 格式如下: YYYY/M/D HH:MM:SS 月份 (0-11，0 為 1 月) 時區差 (以分鐘為單位) | varchar(100) |
| `tnt` | 用於Adobe Target整合。 | text |
| `tnt_action` | 用於Adobe Target整合。 | text |
| `tnt_post_vista` | 已不再使用。請改用post_tnt。 | text |
| `transactionid` | 唯一識別碼，稍後可透過資料來源上傳各種資料點。 | text |
| `truncated_hit` | 表示影像要求已截斷的旗標。 表示已收到部分點擊。<br>Y：點擊遭截斷；收到部分點擊 <br>N：點擊未截斷；收到完整點擊 | char(1) |
| `ua_color` | 已不再使用。先前用作顏色深度的備援。 | char(20) |
| `ua_os` | 已不再使用。先前用作作業系統的備援。 | char(80) |
| `ua_pixels` | 已不再使用。先前用作瀏覽器高度和寬度的備援。 | char(20) |
| `user_agent` | 在影像要求的HTTP標題中傳送的使用者代理字串。 | text |
| `user_hash` | 沒用。 報表套裝ID的雜湊。 請改用使用者名稱。 | 不帶正負號的 int |
| `user_server` | 用於「伺服器」維度的變數。 | varchar(100) |
| `userid` | 沒用。 報表套裝ID的數值ID。 請改用使用者名稱。 | 不帶正負號的 int |
| `username` | 點擊的報表套裝ID。 | char(40) |
| `va_closer_detail` | 用於「上次接觸詳細資料」維度的變數。 | varchar(255) |
| `va_closer_id` | 識別「上次接觸渠道」維度的數值ID。 如需此ID的查閱，請參閱行銷渠道管理員。 | 不帶正負號的 tinyint |
| `va_finder_detail` | 用於「首次接觸詳細資料」維度的變數。 | varchar(255) |
| `va_finder_id` | 識別「首次接觸渠道」維度的數值ID。 如需此ID的查閱，請參閱行銷渠道管理員。 | 不帶正負號的 tinyint |
| `va_instance_event` | 用以識別行銷渠道例項的旗標。 用於行銷渠道上次接觸例項量度。 | 不帶正負號的 tinyint |
| `va_new_engagement` | 標幟以識別行銷渠道的新參與。 用於「新增參與」度量。 | 不帶正負號的 tinyint |
| `video` | 視訊內容 | varchar(255) |
| `videoad` | 視訊廣告名稱 | varchar(255) |
| `videoadinpod` | Pod 位置中的視訊廣告 | varchar(255) |
| `videoadlength` | 視訊廣告長度 | varchar(255) |
| `videoadload` | 視訊廣告載入 | varchar(255) |
| `videoadname` | 視訊廣告名稱 | varchar(255) |
| `videoadplayername` | 視訊廣告播放器名稱 | varchar(255) |
| `videoadpod` | 視訊廣告 Pod | varchar(255) |
| `videoadvertiser` | 視訊廣告商 | varchar(255) |
| `videoaudioalbum` | 影音相簿 | varchar(255) |
| `videoaudioartist` | 影音藝人 | varchar(255) |
| `videoaudioauthor` | 影音作者 | varchar(255) |
| `videoaudiolabel` | 影音標籤 | varchar(255) |
| `videoaudiopublisher` | 影音發佈者 | varchar(255) |
| `videoaudiostation` | 影音電台 | varchar(255) |
| `videocampaign` | 影音促銷活動 | varchar(255) |
| `videochannel` | 視訊頻道 | varchar(255) |
| `videochapter` | 視訊章節名稱 | varchar(255) |
| `videocontenttype` | 視訊內容類型。所有視訊檢視會自動設為 &#39;Video&#39;。 | varchar(255) |
| `videodaypart` | 視訊時段 | varchar(255) |
| `videoepisode` | 視訊集數 | varchar(255) |
| `videofeedtype` | 視訊輸出類型 | varchar(255) |
| `videogenre` | 視訊類型 | text |
| `videolength` | 視訊長度 | varchar(255) |
| `videomvpd` | 視訊 MVPD | varchar(255) |
| `videoname` | 視訊名稱 | varchar(255) |
| `videonetwork` | 視訊網路 | varchar(255) |
| `videopath` | 視訊路徑 | varchar(100) |
| `videoplayername` | 視訊播放器名稱 | varchar(255) |
| `videoqoebitrateaverageevar` | 視訊品質平均位元速率 | varchar(255) |
| `videoqoebitratechangecountevar` | 視訊品質變更計數 | varchar(255) |
| `videoqoebuffercountevar` | 視訊品質緩衝計數 | varchar(255) |
| `videoqoebuffertimeevar` | 視訊品質緩衝時間 | varchar(255) |
| `videoqoedroppedframecountevar` | 視訊品質下降的影格計數 | varchar(255) |
| `videoqoeerrorcountevar` | 視訊品質錯誤計數 | varchar(255) |
| `videoqoeextneralerrors` | 視訊品質外部錯誤 | text |
| `videoqoeplayersdkerrors` | 視訊品質 SDK 錯誤 | text |
| `videoqoetimetostartevar` | 視訊品質的開始時間 | varchar(255) |
| `videoseason` | 視訊季數 | varchar(255) |
| `videosegment` | 視訊區段 | varchar(255) |
| `videoshow` | 視訊節目 | varchar(255) |
| `videoshowtype` | 視訊節目類型 | varchar(255) |
| `videostreamtype` | 視訊串流類型 | varchar(255) |
| `visid_high` | 與visid_low搭配使用，以唯一識別瀏覽。 | 不帶正負號的 bigint |
| `visid_low` | 與visid_high搭配使用，以唯一識別瀏覽。 | 不帶正負號的 bigint |
| `visid_new` | 用以識別點擊是否包含新產生的訪客ID的旗標。 | char(1) |
| `visid_timestamp` | 如果訪客ID是新產生的，則提供訪客ID產生時的時間戳記（在Unix時間）。 | int |
| `visid_type` | 此數值 ID 表示用於識別訪客的方法。<br>0：自訂訪客 ID <br>1：IP 和使用者代理備援 <br>2：HTTP 行動訂閱者標題 <br>3：舊版 Cookie 值 (s_vi) <br>4：備援 Cookie 值 (s_fid) <br>5：身分識別服務 | 不帶正負號的 tinyint |
| `visit_keywords` | 用於「搜尋關鍵字」維度的變數。此欄使用非標準字元限制來容納 Adobe 使用的後端邏輯。 | varchar(244) |
| `visit_num` | 用於瀏覽次數維度的變數。 從1開始，每次每位訪客開始新瀏覽時遞增。 | 不帶正負號的 int |
| `visit_page_num` | 用於「點擊深度」維度的變數。 使用者產生的每次點擊增加1。 重設每次瀏覽。 | 不帶正負號的 int |
| `visit_ref_domain` | 根據visit_referrer欄。 瀏覽的第一個反向連結網域。 | varchar(100) |
| `visit_ref_type` | 代表瀏覽之第一個反向連結反向連結類型的數值ID。 使用referrer_type.tsv查閱表格。 | 不帶正負號的 tinyint |
| `visit_referrer` | 瀏覽的第一個反向連結。 | varchar(255) |
| `visit_search_engine` | 瀏覽之第一個搜尋引擎的數值ID。 使用search_engines.tsv查閱表格。 | 不帶正負號的 smallint |
| `visit_start_page_url` | 瀏覽的第一個URL。 | varchar(255) |
| `visit_start_pagename` | 瀏覽的第一個頁面名稱。 | varchar(100) |
| `visit_start_time_gmt` | 瀏覽首次點擊的時間戳記（在Unix時間）。 | int |
| `weekly_visitor` | 用以判斷點擊是否為新每週訪客的旗標。 | 不帶正負號的 tinyint |
| `yearly_visitor` | 用以判斷點擊是否為新每年訪客的旗標。 | 不帶正負號的 tinyint |
| `zip` | 用於填入郵遞區號維度。 | varchar(50) |

## 空白欄

下列清單為未使用的欄，因此不包含資料：

* mobileacquisitionclicks
* mobileactioninapptime
* mobileactiontotaltime
* mobileappperformanceaffectedusers
* mobileappperformanceappid<span>.</span>app-perf-app-name
* mobileappperformanceappid<span>.</span>app-perf-platform
* mobileappperformancecrashes
* mobileappperformancecrashid<span>.</span>app-perf-crash-name
* mobileappperformanceloads
* mobileappstoreavgrating
* mobileappstoredownloads
* mobileappstoreinapprevenue
* mobileappstoreinapproyalties
* mobileappstoreobjectid<span>.</span>app-store-user
* mobileappstoreobjectid<span>.</span>application-name
* mobileappstoreobjectid<span>.</span>application-version
* mobileappstoreobjectid<span>.</span>appstore-name
* mobileappstoreobjectid<span>.</span>category-name
* mobileappstoreobjectid<span>.</span>country-name
* mobileappstoreobjectid<span>.</span>device-manufacturer
* mobileappstoreobjectid<span>.</span>device-name
* mobileappstoreobjectid<span>.</span>in-app-name
* mobileappstoreobjectid<span>.</span>platform-name-version
* mobileappstoreobjectid<span>.</span>rank-category-type
* mobileappstoreobjectid<span>.</span>region-name
* mobileappstoreobjectid<span>.</span>review-comment
* mobileappstoreobjectid<span>.</span>review-title
* mobileappstoreoneoffrevenue
* mobileappstoreoneoffroyalties
* mobileappstorepurchases
* mobileappstorerank
* mobileappstorerankdivisor
* mobileappstorerating
* mobileappstoreratingdivisor
* mobileavgprevsessionlength
* mobilecrashes
* mobilecrashrate
* mobiledailyengagedusers
* mobiledeeplinkid<span>.</span>name
* mobileinstalls
* mobilelaunches
* mobileltvtotal
* mobilemessageclicks
* mobilemessageid<span>.</span>dest
* mobilemessageid<span>.</span>name
* mobilemessageid<span>.</span>type
* mobilemessageimpressions
* mobilemessagepushpayloadid<span><span>.</span></span>name
* mobilemessageviews
* mobilemonthlyengagedusers
* mobileplacedwelltime
* mobileplaceentry
* mobileplaceexit
* mobileprevsessionlength
* mobilerelaunchcampaigntrackingcode<span><span>.</span></span>name
* mobileupgrades
* socialaveragesentiment
* socialaveragesentiment (已廢止)
* socialfbstories
* socialfbstorytellers
* socialinteractioncount
* sociallikeadds
* sociallink
* sociallink (已廢止)
* socialmentions
* socialpageviews
* socialpostviews
* socialproperty
* socialproperty (已廢止)
* socialpubcomments
* socialpubposts
* socialpubrecommends
* socialpubsubscribers
* socialterm
* socialtermslist
* socialtermslist (已廢止)
* socialtotalsentiment
* sourceid
* videoauthorized
* videoaverageminuteaudience
* videochaptercomplete
* videochapterstart
* videochaptertime
* videopause
* videopausecount
* videopausetime
* videoplay
* videoprogress10
* videoprogress25
* videoprogress50
* videoprogress75
* videoprogress96
* videoqoebitrateaverage
* videoqoebitratechange
* videoqoebuffer
* videoqoedropbeforestart
* videoqoedroppedframes
* videoqoeerror
* videoresume
* videototaltime
* videouniquetimeplayed
