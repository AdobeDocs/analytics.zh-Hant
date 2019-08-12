---
description: 說明資料饋送中欄的表格資料。
keywords: 資料饋送；欄
seo-description: 說明資料饋送中欄的表格資料。
seo-title: 資料欄參考
solution: Analytics
subtopic: 資料饋送
title: 資料欄參考
topic: Reports & Analytics
uuid: 9042a274-7124-4323-3cd6-5c84ab3ef6d
translation-type: tm+mt
source-git-commit: 6bae6861586fc2aba33888cadfec3b1399898b90

---


# 資料欄參考

使用此頁面瞭解每個欄中包含的資料。大部分實施不會使用每個欄，因此在決定要包含在資料饋送匯出中的欄時，可以參考此頁面。

> [!IMPORTANT] 對於任何指定欄(例如，定義為255個字元的例項)，資料饋送可傳送額外字元，因為字串中附加了字元逸出值。如果您的實施定期傳送超出字元限制的值，請記住此主題。

## 欄、說明和資料類型

> [!NOTE] 大部分欄包含類似的欄 `post_`，加上前置詞。後置欄包含伺服器端邏輯、處理規則和 VISTA 規則之後的值。Adobe 建議在大多數情況下使用後置欄。

| 欄名稱 | 欄說明 | 資料類型 |
| --- | --- | --- |
| accept_language | 列出所有接受的語言，如影像要求中的 Accept-Language HTTP 標頭所示。 | char(20) |
| aemassetid | 對應一組「Adobe Experience Manager 資產」之資產 ID (GUID) 的多值變數。增加曝光數事件 | text |
| aemassetsource | 識別資產事件的來源。用於 Adobe Experience Manager。 | varchar(255) |
| aemclickedassetid | Adobe Experience Manager 資產的資產 ID。增加點擊事件 | varchar(255) |
| browser | 瀏覽器的數值 ID。請參考 browser.tsv 查閱表格。 | 未簽署int |
| browser_height | 瀏覽器視窗的高度 (像素)。 | 未簽署的smallint |
| browser_width | 瀏覽器視窗的寬度 (像素)。 | 未簽署的smallint |
| c_color | 調色盤的位元深度。作為計算「色彩深度」維度的一部分。使用 JavaScript 函數 screen.colorDepth()。 | char(20) |
| campaign | 用於「追蹤程式碼」維度的變數。 | varchar(255) |
| carrier | Adobe Advertising Cloud 整合變數。指定行動電信業者。請參考電信業者查閱表格。 | varchar(100) |
| channel | 用於「網站區域」維度的變數。 | varchar(100) |
| click_action | 已不再使用。使用舊版 ClickMap 工具點按的連結位址。 | varchar(100) |
| click_action_type | 已不再使用。舊版 ClickMap 工具的連結類型。<br>0：HREF URL<br>1：自訂ID<br>2：JavaScript onClick event<br>3：表單元素 | 不帶正負號的 tinyint |
| click_context | 已不再使用。發生連結點按的頁面名稱。舊版 ClickMap 工具的一部分。 | varchar(255) |
| click_context_type | 已不再使用。表示 click_context 是否具備頁面名稱或預設為頁面 URL。<br>0：頁面URL<br>1：頁面名稱 | 不帶正負號的 tinyint |
| click_sourceid | 已不再使用。點按連結頁面上位置的數值 ID。舊版 ClickMap 工具的一部分。 | 未簽署int |
| click_tag | 已不再使用。已點擊的 HTML 元素類型。 | char(10) |
| clickmaplink | Activity Map連結 | varchar(255) |
| clickmaplinkbyregion | 依地區區分的Activity Map連結 | varchar(255) |
| clickmappage | Activity Map頁面 | varchar(255) |
| clickmapregion | Activity Map地區 | varchar(255) |
| code_ver | 用於編譯及傳送影像要求的 AppMeasurement 程式庫版本。 | char(16) |
| color | 以 c_color 欄為基礎的色彩深度 ID。請參考 color_depth.tsv 查閱表格。 | 未簽署的smallint |
| connection_type | 此數值 ID 表示連線類型。用於「連線類型」維度的變數。請參考 connection_type.tsv 查閱表格。 | 不帶正負號的 tinyint |
| Cookie | 用於「Cookie 支援」維度的變數。<br>Y：disableDN<br>：LibleDu<br>：未知 | char(1) |
| country | 此數值 ID 表示點擊來源國家/地區。Adobe 與 Digital Envoy 合作，比對 IP 位址與國家/地區。使用 country.tsv 查閱。 | 未簽署的smallint |
| ct_connect_type | 與 connection_type 欄相關。最常見的值是 LAN/Wifi、行動電信業者和數據機。 | char(20) |
| curr_factor | 決定貨幣小數位數，並用於貨幣轉換。例如，USD 使用兩個小數位數，因此該欄值為 2。 | tinyint |
| curr_rate | 交易發生當時的匯率。Adobe 與 XE 合作，以決定當日匯率。 | decimal(24,12) |
| currency | 交易期間使用的貨幣代碼。 | char(8) |
| cust_hit_time_gmt | 僅限啟用時間戳記的報表套裝。時間戳記根據 Unix 時間隨點擊傳送。 | int |
| cust_visid | 如果已設定自訂訪客 ID，則會填入此欄。 | varchar(255) |
| daily_visitor | 此旗標用於確定點擊是否為新每日訪客。 | 不帶正負號的 tinyint |
| date_time | 可讀格式的點擊時間，根據報表套裝的時區而定。 | 日期時間 |
| domain | 用於「網域」維度的變數。以使用者的 Internet 服務提供商 (ISP) 為基礎。 | varchar(100) |
| duplicate_events | 列出每個計為重複項目的事件。 | varchar(255) |
| duplicate_purchase | 此旗標用於指出此點擊的購買事件因為重複而應被忽略。 | 不帶正負號的 tinyint |
| duplicated_from | 僅用於包含點擊複製 VISTA 規則的報表套裝。指出從中複製點擊的報表套裝。 | varchar(40) |
| ef_id | ef_id 用於 Adobe Advertising Cloud 整合。 | varchar(255) |
| evar1 - evar250 | 自訂變數 1-250。每個組織使用不同的 eVar。如需關於貴組織如何填入各 eVar 的更多資訊，請參閱貴組織專用的解決方案設計文件。 | varchar(255) |
| event_list | 以逗號分隔的數值 ID 清單，代表點擊觸發的事件。包括預設事件和自訂事件 1-1000。使用 event.tsv 查閱。 | text |
| exclude_hit | 此旗標用於表示點擊已從報告排除。visit_ num欄不會因為排除的點擊而增加。<br>1: 未使用. 精選功能的一部分。<br>2: 未使用. 精選功能的一部分。<br>3：不再使用。使用者代理排除<br>4：根據IP位址<br>排除：遺漏重要點擊資訊，例如page_ url、pagename、page_ event或event_ list<br>6：JavaScript未正確處理點擊<br>7：帳戶專屬排除，例如VISTA規則<br>8：未使用。替代帳戶專屬排除。<br>9: 未使用. 精選功能的一部分。<br>10：無效的貨幣代碼<br>11：點擊遺失時間戳記報表套裝上的時間戳記，或點擊在非時間戳記報表套裝<br>12上包含時間戳記：未使用。精選功能的一部分。<br>13: 未使用. 精選功能的一部分。<br>14：不符合Analytics點擊<br>15的Target點擊：目前未使用。<br>16：無法符合Analytics點擊的Advertising Cloud點擊 | 不帶正負號的 tinyint |
| first_hit_page_url | 訪客的第一個 URL。 | varchar(255) |
| first_hit_pagename | 用於「登入頁面原始」維度的變數。訪客的原始登入頁面名稱。 | varchar(100) |
| first_hit_ref_domain | 此用於「原始反向連結網域」維度的變數。以 first_hit_referrer 為基礎。訪客的第一個反向連結網域。 | varchar(100) |
| first_hit_ref_type | 此數值 ID 表示訪客第一個反向連結的反向連結類型。使用 referrer_type.tsv 查閱。 | 不帶正負號的 tinyint |
| first_hit_referrer | 訪客的第一個反向連結 URL。 | varchar(255) |
| first_hit_time_gmt | 訪客初次點擊的時間戳記，格式為 Unix 時間。 | int |
| geo_city | 根據 IP 的點擊來源城市名稱。Adobe 與 Digital Envoy 合作，比對 IP 位址與城市。 | char(32) |
| geo_country | 根據 IP 的點擊來源國家/地區縮寫。Adobe 與 Digital Envoy 合作，比對 IP 位址與國家/地區。 | char(4) |
| geo_dma | 根據 IP 的點擊來源地理區域數值 ID。Adobe 與 Digital Envoy 合作，比對 IP 位址與地理區域。 | 未簽署int |
| geo_region | 根據 IP 的點擊來源州或地區名稱。Adobe 與 Digital Envoy 合作，比對 IP 位址與州/地區。 | char(32) |
| geo_zip | 點擊的郵遞區號源自於IP。Adobe 與 Digital Envoy 合作，比對 IP 位址與郵遞區號。 | varchar(16) |
| hier1 - hier5 | 由階層變數使用。包含使用分隔符號的值清單。在報表套裝設定下選擇分隔符號。 | varchar(255) |
| hit_source | 指出點擊來源。<br>1：不含時間戳記 <br>的標準影像請求：含時間戳記 <br>的標準影像要求：使用時間戳記 <br>的即時資料來源上傳：未使用 <br>5：通用資料來源上傳 <br>6：完整處理資料來源上傳 <br>7：transactionID資料來源上傳 <br>8：不再使用；舊版Adobe Advertising Cloud資料來源 <br>9：不再使用；Adobe Social摘要度量 | 不帶正負號的 tinyint |
| hit_time_gmt | 點擊Adobe資料收集伺服器的時間戳記會根據Unix時間接收點擊。 | int |
| hitid_high | 用於結合 hitid_low 以專門識別點擊。 | 未簽署的bigint |
| hitid_low | 用於結合 hitid_high 以專門識別點擊。 | 未簽署的bigint |
| homepage | 已不再使用。指出目前 URL 是否為瀏覽器的首頁。 | char(1) |
| hourly_visitor | 此旗標用於確定點擊是否為新每小時訪客。 | 不帶正負號的 tinyint |
| ip | IP 位址，根據影像要求的 HTTP 標頭。 | char(20) |
| ip2 | 未使用。報表套裝的後端參考變數，包含以 IP 位址為基礎的 VISTA 規則。 | char(20) |
| j_jscript | 瀏覽器支援的 JavaScript 版本。 | char(5) |
| java_enabled | 此旗標用於指出是否已啟用 Java。<br>Y：已啓用 <br>N：停用 <br>U：未知 | char(1) |
| javascript | JavaScript 版本的查閱 ID，根據 j_jscript。使用查閱表格。 | 不帶正負號的 tinyint |
| language | 語言的數值 ID。使用 languages.tsv 查閱表格。 | 未簽署的smallint |
| last_hit_time_gmt | 先前點擊的時間戳記 (Unix 時間)。用於計算「上次造訪間隔天數」維度。 | int |
| last_purchase_num | 用於「客戶忠誠度」維度的變數。表示訪客之前的購買次數。<br>0：無先前購買(非客戶) <br>1：1之前購買(新客戶) <br>2：先前購買(舊客戶)2：先前購買(舊客戶) <br>3：或更多先前購買 | 未簽署int |
| last_purchase_time_gmt | 用於「上次購買間隔天數」維度。上次購買的時間戳記 (Unix 時間)。對於首次購買和之前未購買的訪客，此值為 0。 | int |
| latlon1 | 位置 (10 公里以內) | varchar(255) |
| latlon23 | 位置 (100 公尺以內) | varchar(255) |
| latlon45 | 位置 (1 公尺以內) | varchar(255) |
| mc_audiences  | 訪客所屬的 Audience Manager 區段 ID 清單。 | text |
| mcvisid | Experience Cloud 訪客 ID。128 位元的數字，由兩個串連的 64 位元數字組成，兩個數字皆補至 19 位數。 | varchar(255) |
| mobile_id | 如果使用者使用行動裝置，則裝置的數值ID。 | int |
| mobileaction | 行動動作。在Mobile Services中呼叫trackAction時自動收集的。允許應用程式中的自動動作路徑。 | varchar(100) |
| mobileappid | 行動應用程式 ID。以下列格式儲存應用程式名稱和版本:[AppName] [BundleVersion] | varchar(255) |
| mobileappsocialeappid | 用於Apteligent資料連接器。Apteligent中使用的應用程式ID。 | varchar(255) |
| mobileappsocialececradid | 用於Apteligent資料連接器。Apteligent中使用的當機ID。 | varchar(255) |
| mobileappstoretid | 用於AppFigures資料連接器。應用程式商店物件ID | varchar(255) |
| mobilebeaconmajor | Mobile Services信標主要 | varchar(100) |
| mobilebeaconminor | 行動服務信標次要 | varchar(100) |
| mobilebeaconproximity | Mobile Services信標鄰近地區 | varchar(255) |
| mobilebeaconuuid | Mobile Services信標UUID | varchar(100) |
| mobilecampaigncontent | 顯示連結的內容名稱或 ID。由「行動應用程式贏取」填入。 | varchar(255) |
| mobilecampaignmedium | 行銷媒體，例如橫幅或電子郵件。由「行動應用程式贏取」填入。 | varchar(255) |
| mobilecampaignname | 行銷活動名稱，亦儲存於行銷活動變數中。由「行動應用程式贏取」填入。 | varchar(255) |
| mobilecampaignsource | 原始轉介來源，例如電子報或社交媒體網路。由「行動應用程式贏取」填入。 | varchar(255) |
| mobilecampaignterm | 您想要以此贏取追蹤的付費關鍵字或其他詞語。由「行動應用程式贏取」填入。 | varchar(255) |
| mobiledayofweek | 應用程式啟動的工作日數。 | varchar(255) |
| mobiledayssincefirstuse | 自應用程式初次執行以來的天數。 | varchar(255) |
| mobiledayssincelastupgrade | 從上下文資料變數a. DaysSinceLastUpgrade收集。自上一個作業開始後所經過的天數。 | varchar(255) |
| mobiledayssincelastuse | 自應用程式上次執行以來的天數。 | varchar(255) |
| mobiledeplinkid | 從上下文資料變數a.<span>deeplink</span>. id收集。用於贏取報表作為行動贏取連結的識別碼。 | varchar(255) |
| mobiledevice | 行動裝置名稱。在 iOS 上，此名稱以逗號分隔的 2 位數字串形式儲存。第一個數字代表裝置代別，第二個數字代表裝置系列。 | varchar(255) |
| mobilehourofday | 定義啟動應用程式的一天中的時段。請依照 24 小時數字格式。 | varchar(255) |
| mobileinstalldate | 行動安裝日期。提供使用者初次開啟行動應用程式的日期。 | varchar(255) |
| mobilelaunchessincelastupgrade | 從上下文資料變數a. launchEsseUpgrade收集。報告自從上次升級後啓動的次數。 | varchar(255) |
| mobilelaunchnumber | 每次啟動行動應用程式時增加 1。 | varchar(255) |
| mobileltv | 已不再使用。由 trackLifetimeValue 方法填入。 | varchar(255) |
| mobilemessageutonname | 從上下文資料變數.<span>message</span>. button. id收集。用於應用程式內訊息，以識別關閉訊息的按鈕。 | varchar(100) |
| mobilemessageid | 應用程式內訊息ID | varchar(255) |
| mobilemessageonline | 應用程式內訊息線上訊息 | varchar(255) |
| mobilemessagepushtin | 從上下文資料變數. push. optin收集。使用者選擇加入推送訊息時，設為「true」；否則值為「false」。 | varchar(255) |
| mobilemessagepushpayloadid | 從上下文資料變數a. push. payloadid收集。用於推送訊息作為裝載識別碼。 | varchar(255) |
| mobileosenvironment | 從上下文資料變數a.OS環境收集。狀態OS環境，例如Android或iOS。 | varchar(255) |
| mobileosversion | Mobile Services作業系統版本 | varchar(255) |
| mobileplaceaccuracy | 從上下文資料變數a. loc. acc收集。指出GPS在收集時的準確度。 | varchar(255) |
| mobileplacecategory | 從上下文資料變數. loc. category收集。說明特定位置的類別。 | varchar(255) |
| mobileplaceid | 從上下文資料變數a.<span>loc</span>. id收集。指定興趣點的識別碼。 | varchar(255) |
| mobilersocialunchcampaign content | Mobile Services啓動內容 | varchar(255) |
| mobilersocialunchcampaignmedium | Mobile Services啓動媒體 | varchar(255) |
| mobilersocialunchcampaign source | Mobile Services啓動來源 | varchar(255) |
| mobilersocialunchcampaignterm | Mobile Services啓動期限 | varchar(255) |
| mobilersocialunchcampaigntrackingcode | 從上下文資料變數a. launch. campaign. trackingcode收集。用於贏取作為啓動促銷活動的追蹤代碼。 | varchar(255) |
| mobileresolution | 行動裝置的解析度。寬 x 高 (以像素表示)。 | varchar(255) |
| monthly_visitor | 此旗標用於表示當月的獨特訪客。 | 不帶正負號的 tinyint |
| mvvar- mvvar3 | 清單變數值。根據實作包含使用分隔符號的自訂值清單。 | text |
| namespace | 未使用。多年前報廢功能的一部分。 | varchar(50) |
| new_visit | 此旗標用於確定目前的點擊是否為新造訪。造訪閒置 30 分鐘後，由 Adobe 伺服器設定。 | 不帶正負號的 tinyint |
| os | 此數值 ID 表示訪客的作業系統。根據 user_agent 欄。使用 os 查閱。 | 未簽署int |
| p_plugins | 已不再使用。瀏覽器的可用外掛程式清單.使用 JavaScript 函數 navigator.plugins()。 | text |
| page_event | 影像要求中傳送的點擊類型 (標準點擊、下載連結、自訂連結、退出連結)。 | 不帶正負號的 tinyint |
| page_event_var1 | 僅用於連結追蹤影像要求。點按之下載連結、退出連結或自訂連結的 URL。 | text |
| page_event_var2 | 僅用於連結追蹤影像要求。連結的自訂名稱 (若有)。 | varchar(100) |
| page_event_var3 | 已不再使用。包含調查和媒體模組資料。使用舊版 Adobe Analytics 填入的舊版影片報告。 | text |
| page_type | 用於填入「找不到頁面」維度，專用於 404 頁面。此變數應該為空白或包含「ErrorPage」。 | char(20) |
| page_url | 點擊的 URL。未用於連結追蹤影像要求。 | varchar(255) |
| pagename | 用於填入「頁面」維度。如果 pagename 變數為空白，Analytics 會改用 page_url。 | varchar(100) |
| paid_search | 如果點擊符合付費搜尋偵測，則會設定此旗標。 | 不帶正負號的 tinyint |
| partner_plugins | 未使用。多年前報廢功能的一部分。 | varchar(255) |
| persistent_cookie | 由「永久性 Cookie 支援」維度使用。指出訪客是否支援每次點擊後未捨棄的 Cookie。 | char(1) |
| 外掛程式 | 已不再使用。與瀏覽器中可用外掛程式對應的數值 ID 清單。使用 plugins.tsv 查閱。 | varchar(180) |
| pointofinterest | Mobile Services興趣點名稱 | varchar(255) |
| pointofinterestdistance | 行動服務與興趣點中心的距離 | varchar(255) |
| post_ columns | 包含報表中最終使用的值。每個後置欄會填入伺服器端邏輯、處理規則和 VISTA 規則之後。Adobe 建議在大多數情況下使用後置欄。 | 請參閱各個非後置欄 |
| prev_page | 未使用。上一頁的 Adobe 專屬識別碼。 | 未簽署int |
| product_list | 透過產品變數傳入的產品清單。產品是以逗號分隔，而個別產品屬性是由分號分隔。 | text |
| product_merchandising | 未使用。請改用 product_list。 | text |
| prop1 - prop75 | 自訂流量變數 1 - 75。 | varchar(100) |
| purchaseid | 使用 s_purchaseID 變數設定之購買的唯一識別碼。由 duplicate_purchase 欄使用。 | char(20) |
| quarterly_visitor | 此旗標用於確定點擊是否為新每季訪客。 | 不帶正負號的 tinyint |
| ref_domain | 根據反向連結欄。點擊的反向連結網域。 | varchar(100) |
| ref_type | 此數值 ID 表示點擊的反向連結類型。<br>1：網站內<br>2：其他網站 <br>3：搜尋引擎 <br>4：硬碟 <br>5：USENET <br>6：分類/建立書簽(無反向連結) <br>7：電子郵件 <br>8：無JavaScript <br>9：社交網路 | 不帶正負號的 tinyint |
| referrer | 上一頁的頁面 URL。 | varchar(255) |
| resolution | 此數值 ID 表示螢幕解析度。填入「螢幕解析度」維度。使用 resolution.tsv 查閱表格。 | 未簽署的smallint |
| s_kwcid | 用於Adobe Advertising Cloud整合的關鍵字ID。 | varchar(255) |
| s_resolution | 原始螢幕解析度值。使用 JavaScript 函數 screen.width x screen.height 收集。 | char(20) |
| sampled_hit | 已不再使用。先前用於 Ad Hoc Analysis 中的取樣。 | char(1) |
| search_engine | 此數值 ID 表示將訪客反向連結至您網站的搜尋引擎。使用 search_engines.tsv 查閱。 | 未簽署的smallint |
| search_page_num | 由「所有搜尋頁面排名」維度使用。指出在使用者點進您的網站之前，網站顯示的搜尋結果頁面。 | 未簽署的smallint |
| secondary_hit | 此旗標用於追蹤次要點擊。通常源自複製點擊的多套裝標記和 VISTA 規則。 | 不帶正負號的 tinyint |
| service | 未使用。請改用 page_event。 | char(2) |
| socialaccountandappids | 已不再使用。社交帳戶和應用程式 ID | varchar(255) |
| socialassettrackingcode | 已不再使用。社交促銷活動變數 | varchar(255) |
| socialauthor | 已不再使用。社交作者變數 | varchar(255) |
| socialcontentprovider | 已不再使用。社交平台/屬性 | varchar(255) |
| socialinteractiontype | 已不再使用。社交互動類型 | varchar(255) |
| sociallanguage | 已不再使用。社交語言 | varchar(255) |
| sociallatlong | 已不再使用。社交緯度/經度 | varchar(255) |
| socialowneddefinitioninsighttype | 已不再使用。社交擁有的定義分析類型 | varchar(255) |
| socialowneddefinitioninsightvalue | 已不再使用。社交擁有的定義分析值 | varchar(255) |
| socialowneddefinitionmetric | 已不再使用。社交擁有的定義量度 | varchar(255) |
| socialowneddefinitionpropertyvspost | 已不再使用。社交擁有的定義屬性與貼文 | varchar(255) |
| socialownedpostids | 已不再使用。社交擁有的貼文 ID | varchar(255) |
| socialownedpropertyid | 已不再使用。社交擁有的屬性 ID | varchar(255) |
| socialownedpropertyname | 已不再使用。社交擁有的屬性名稱 | varchar(255) |
| socialownedpropertypropertyvsapp | 已不再使用。社交擁有的屬性與應用程式 | varchar(255) |
| state | State 變數。 | varchar(50) |
| stats_server | 未使用。處理點擊的 Adobe 內部伺服器。 | char(30) |
| t_time_info | 訪客的當地時間。格式如下:M/D/YYYY HH：MM：SS Month(0-11，0=月)時區偏移(分鐘) | varchar(100) |
| tnt | 用於 Adobe Target 整合。 | text |
| tnt_action | 用於 Adobe Target 整合。 | text |
| tnt_post_vista | 已不再使用。請改用 post_tnt。 | text |
| transactionid | 唯一識別碼，日後可透過資料來源上傳各種資料點。 | text |
| truncated_hit | 此旗標用於表示影像要求已截斷。表示已收到部分點擊。<br>Y：點擊遭截斷；部分點擊收到 <br>N：點擊未被截斷；收到完整點擊 | char(1) |
| ua_color | 已不再使用。先前作為色彩深度的後援。 | char(20) |
| ua_os | 已不再使用。先前作為作業系統的後援。 | char(80) |
| ua_pixels | 已不再使用。先前作為瀏覽器高度和寬度的後援。 | char(20) |
| user_agent | 傳入影像要求之 HTTP 標頭的使用者代理字串。 | text |
| user_hash | 未使用。報表套裝 ID 上的雜湊.請改用使用者名稱。 | 未簽署int |
| user_server | 用於「伺服器」維度的變數。 | varchar(100) |
| userid | 未使用。報表套裝 ID 的數值 ID。請改用使用者名稱。 | 未簽署int |
| username | 報表套裝 ID適用於點擊。 | char(40) |
| va_closer_detail | 用於「上次接觸詳情」維度的變數。 | varchar(255) |
| va_closer_id | 可識別「上次接觸渠道」維度的數值 ID 。可以在「行銷通路管理員」中找到此 ID 的查閱。 | 不帶正負號的 tinyint |
| va_finder_detail | 用於「首次接觸詳情」維度的變數。 | varchar(255) |
| va_finder_id | 可識別「首次接觸管道」維度的數值 ID 。可以在「行銷通路管理員」中找到此 ID 的查閱。 | 不帶正負號的 tinyint |
| va_instance_event | 用於識別行銷管道例項的旗標。由「行銷管道上次接觸例項」量度使用。 | 不帶正負號的 tinyint |
| va_new_engagement | 用於識別行銷管道新增參與的旗標。由「新增參與」量度使用。 | 不帶正負號的 tinyint |
| video | 視訊內容 | varchar(255) |
| videoad | 視訊廣告名稱 | varchar(255) |
| videoadinpod | Pod位置中的視訊廣告 | varchar(255) |
| videoadlength | 視訊廣告長度 | varchar(255) |
| videoadload | 視訊廣告載入 | varchar(255) |
| videoadname | 視訊廣告名稱 | varchar(255) |
| videoadplayername | 視訊廣告播放器名稱 | varchar(255) |
| videoadpod | 視訊廣告pod | varchar(255) |
| videoAdvertiser | 視訊廣告商 | varchar(255) |
| videoaudiobum | 視訊音訊相簿 | varchar(255) |
| videoaudiouser | 視訊音訊藝術家 | varchar(255) |
| videoudioauthor | 視訊音訊作者 | varchar(255) |
| videoudiolabel | 視訊音訊標籤 | varchar(255) |
| videoudiaPublisher | 視訊音訊publisher | varchar(255) |
| videoudiostation | 視訊音訊工作站 | varchar(255) |
| videocampaignn | 視訊促銷活動 | varchar(255) |
| videochannel | 視訊頻道 | varchar(255) |
| videochapter | 影片章節名稱 | varchar(255) |
| videocontenttype | 視訊內容類型。所有視訊檢視會自動設為 'Video'。 | varchar(255) |
| videodaypart | 視訊日部分 | varchar(255) |
| videoepisode | 視訊集集 | varchar(255) |
| videofeedtype | 視訊饋送類型 | varchar(255) |
| videogenre | 視訊類型 | text |
| videolength | 視訊長度 | varchar(255) |
| videomvpd | 視訊MVPD | varchar(255) |
| videoname | 視訊名稱 | varchar(255) |
| videonetwork | 視訊網路 | varchar(255) |
| videopath | 視訊路徑 | varchar(100) |
| videoplayername | 視訊播放器名稱 | varchar(255) |
| videoqoebitrateaverageevar | 視訊品質平均位元速率 | varchar(255) |
| videoqoebitratechangecountevar | 視訊品質變更計數 | varchar(255) |
| videoqoebuffercountevar | 視訊品質緩衝計數 | varchar(255) |
| videoqoebuffertimeevar | 視訊品質緩衝時間 | varchar(255) |
| videoqoedroppedframecountevar | 視訊品質掉格計數 | varchar(255) |
| videoqoeerrorcountevar | 視訊品質錯誤計數 | varchar(255) |
| videoqoeextneralerrors | 視訊品質外部錯誤 | text |
| videoqoeplayersdkerrors | 視訊品質SDK錯誤 | text |
| videoqoetimetostartevar | 視訊品質開始時間 | varchar(255) |
| videoseason | 視訊季節 | varchar(255) |
| videosegment | 視訊區段 | varchar(255) |
| videoshow | 影片顯示 | varchar(255) |
| videoshowtype | 視訊顯示類型 | varchar(255) |
| videostreamtype | 視訊串流類型 | varchar(255) |
| visid_high | 用於結合 visid_low 以專門識別造訪。 | 未簽署的bigint |
| visid_low | 用於結合 visid_high 以專門識別造訪。 | 未簽署的bigint |
| visid_new | 用於識別點擊是否包含新產生訪客 ID 的旗標。 | char(1) |
| visid_timestamp | 如果新產生訪客 ID，則會提供產生訪客 ID 時的時間戳記 (單位為 Unix 時間)。 | int |
| visid_type | 此數值 ID 表示用於識別訪客的方法。<br>0：自訂訪客ID <br>1：IP和使用者代理後援 <br>2：HTTP行動訂閱者標題 <br>3：舊版Cookie值(s_ vi) <br>4：後援Cookie值(s_ fid) <br>5：身分服務 | 不帶正負號的 tinyint |
| visit_keywords | 用於「搜尋關鍵字」維度的變數。此欄使用非標準字元限制來容納Adobe使用的後端邏輯。 | varchar(244) |
| visit_num | 用於「造訪數」維度的變數。從 1 開始，每次訪客開始新的造訪時都會遞增。 | 未簽署int |
| visit_page_num | 用於「點擊深度」維度的變數。對於使用者產生的每次點擊會增加 1。重設每次造訪。 | 未簽署int |
| visit_ref_domain | 根據 visit_referrer 欄。造訪的第一個反向連結網域。 | varchar(100) |
| visit_ref_type | 此數值 ID 表示造訪之第一個反向連結的反向連結類型。使用 referrer_type.tsv 查閱表格。 | 不帶正負號的 tinyint |
| visit_referrer | 造訪的第一個反向連結。 | varchar(255) |
| visit_search_engine | 此數值 ID 是造訪的第一個搜尋引擎。使用 search_engines.tsv 查閱表格。 | 未簽署的smallint |
| visit_start_page_url | 造訪的第一個 URL。 | varchar(255) |
| visit_start_pagename | 此次瀏覽起始的造訪的第一個頁面名稱。 | varchar(100) |
| visit_start_time_gmt | 造訪之第一次點擊的時間戳記 (單位為 Unix 時間)。 | int |
| weekly_visitor | 此旗標用於確定點擊是否為新每週訪客。 | 不帶正負號的 tinyint |
| yearly_visitor | 此旗標用於確定點擊是否為新每年訪客。 | 不帶正負號的 tinyint |
| zip | 用於填入「郵遞區號」維度。 | varchar(50) |

## 空白欄

下列欄清單未使用，且不包含資料：

* mobileacquisiclictions
* mobileactioninapptime
* mobileactiontotaltime
* mobileappsocialeafecteedusers
* mobileappsocialeappid<span>.</span>app-perf-app-name
* mobileappsocialeappid<span>.</span>app-perf-platform
* mobileappsocialecrash
* mobileappsupportececradid<span>.</span>app-perf-frash-name
* mobilepappsocialelocals
* mobileappstorch光柵
* mobileappstoredownloads
* mobileappStoreinappeue
* mobileappstoreisproperality
* mobileappstoretid<span>.</span>app-store-user
* mobileappstoretid<span>.</span>application-name
* mobileappstoretid<span>.</span>application-version
* mobileappstoretid<span>.</span>appstore-name
* mobileappstoretid<span>.</span>category-name
* mobileappstoretid<span>.</span>country-name
* mobileappstoretid<span>.</span>裝置製造商
* mobileappstoretid<span>.</span>device-name
* mobileappstoretid<span>.</span>in-app-name
* mobileappstoretid<span>.</span>platform-name-version
* mobileappstoretid<span>.</span>rands-category-type
* mobileappstoretid<span>.</span>region-name
* mobileappstoretid<span>.</span>review-comment
* mobileappstoretid<span>.</span>review-title
* mobileappstoreoffalue
* mobileappstoreoffolality
* mobileappstorepurchards
* mobileappstorercank
* mobileappstorerpublisher
* mobileappstreeration
* mobileappstoreratingdivesor
* mobilelaugpsessionlength
* mobilecrashes
* mobilecraprate
* mobiledailymagedusers
* mobileddeplinkid<span>.</span>名稱
* mobileinstalls
* mobilelaunches
* mobileltvtotal
* mobilemessageclicks
* mobilemessageid<span>.</span>dest
* mobilemessageid<span>.</span>名稱
* mobilemessageid<span>.</span>type
* mobilemessageimpressions
* mobilemessagagpushpayloadit<span><span>.</span></span>名稱
* mobilemessageviews
* mobilemonthrollengtedusers
* mobileppleneltime
* mobileplaceentry
* mobileppleexit
* mobileprevsessionlength
* mobilerselectunchcampaigntrackingcode<span><span>.</span></span>名稱
* mobileupgrades
* socialaveragesentiment
* socialaveragesentiment(deprecated)
* socialfbstories
* socialfbstorytellers
* socialinteractioncount
* sociallikeadds
* sociallink
* sociallink(已停用)
* socialmentions
* socialpageviews
* socialpostviews
* socialproperty
* social屬性(已停用)
* socialpubcomments
* socialpubposts
* socialpubrecommends
* socialpubsubscribers
* socialterm
* socialtermslist
* socialtermslist(deprecated)
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
* videuniquetimeplayed
