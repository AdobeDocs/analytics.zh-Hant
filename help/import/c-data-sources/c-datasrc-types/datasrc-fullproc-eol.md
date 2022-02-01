---
title: 完全處理資料來源的生命週期結束
description: 生命週期結束的原因，以及大量資料插入 API 與完全處理資料來源之間的比較。
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: ht
source-wordcount: '1225'
ht-degree: 100%

---

# 完全處理資料來源的生命週期結束

多年來，「完全處理資料來源」讓您將點擊層級資料提交至 Adobe Analytics。此資料的處理方式與透過我們的 JavaScript 程式庫和行動應用程式 SDK 收集的資料相同。2020 年，Adobe 發行了[大量資料插入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，它執行與「完全處理資料來源」相同的功能，但具有附加功能。本主題提供有關大量資料插入 API 所提供其他功能的詳細資訊，並概述檔案格式的差異。

2021 年 3 月 25 日起，Adobe 禁止建立新的完全處理資料來源連線。支援現有連線，直到 2022 年 1 月 31 日該服務被完全取代為止。除了標準文件之外，我們還提供了[透過大量資料插入 API 提交資料所需步驟](https://adobe.ly/aabdia)的逐步解說。

## 為什麼我們終止了這項功能？

大量資料插入 API (BDIA) 提供了附加功能，同時涵蓋了完全處理支援的所有使用案例。大量資料插入 API 為您提供更好的服務。

## 完全處理資料來源和大量資料插入 API 之間的關鍵差異

* 大量資料插入允許提交多個檔案，這些檔案可以並行處理。您可以使用訪客群組來確保訪客連續性和 eVar 歸因。
* 大量資料插入具有資料驗證和錯誤處理功能，因此無需提交點擊資料的一些管理工作。
* 大量資料插入支援訪客 ID 的多個選項。您可以同時提交 Analytics ID 和 Marketing Cloud ID (請參閱[身分識別服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)以了解更多)。此外，您可以使用自己的 ID 做為[產生 ECID 的種子](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds)。
* 大量資料插入支援清單和內容資料變數。
* 大量資料插入不支援 Activity Map 資料。

## 檔案格式和內容的關鍵差異

* 大量資料插入包含一些其他必要欄位。如需詳細資訊，請參閱[文件](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)。
* 為確保訪客連續性和歸因，大量資料插入要求檔案中的列依時間順序進行排序。請參閱[訪客群組](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups)以了解跨檔案訪客活動的排序。
* 大量資料插入要求檔案以 .gzip 格式壓縮。
* BDIA 使用「timestamp」而非「date」。

如需詳細資訊，請參閱以下對大量資料插入 (BDIA) 和完全處理資料來源 (FPDS) 中可用欄位值的比較。

## BDIA 和 FPDS 中可用欄位值的比較

| BDIA 變數 | 完全處理欄變數 | 說明 |
| --- | --- | --- |
| aamlh | 不支援 | Adobe Audience Manager 位置提示。 |
| browserHeight | browserHeight | 瀏覽器高度 (以像素為單位，例如 768) |
| browserWidth | browserWidth | 瀏覽器寬度 (以像素為單位，例如 1024) |
| campaign | campaign | 轉換促銷活動追蹤代碼 |
| channel | channel | 管道字串 (例如體育版)。 |
| colorDepth | colorDepth | 監視器色彩深度 (以位元為單位，例如 24) |
| connectionType | connectionType | 訪客的連線類型 (LAN 或數據機) |
| contextData.key | 不支援 | 機碼值組是透過命名標題「contextData.product」或「contextData.color」指定的 |
| cookiesEnabled | cookiesEnabled | `Y` 或 `N`，表示訪客是否支援第一方工作階段 Cookie |
| currencyCode | currencyCode | 收入貨幣代碼 (例如 `USD`) |
| customerID.[customerIDType].authState | 不支援 | 訪客的已驗證狀態。支援的值為：0、1、2、UNKNOWN、AUTHENTICATED、LOGGED_OUT 或 &#39;&#39; (不區分大小寫)。兩個連續的單引號 (&quot;) 會導致查詢字串中省略該值，當點擊時該值將轉換為 0。請注意，支援的 authState 數值表示以下值：0 = UNKNOWN、1 = AUTHENTICATED、2 = LOGGED_OUT。customerIDType 可以是任何英數字元字串，但應視為區分大小寫。 |
| customerID.[customerIDType].id | 不支援 | 要使用的客戶 ID。customerIDType 可以是任何英數字元字串，但應視為區分大小寫。 |
| customerID.[customerIDType].isMCSeed | 不支援 | 這是不是 Marketing Cloud 訪客 ID 的種子。支援的值為：0、1、TRUE、FALSE、&#39;&#39; (不區分大小寫)。使用 0、FALSE 或兩個連續的單引號 (&quot;) 會導致查詢字串中省略該值。customerIDType 可以是任何英數字元字串，但應視為區分大小寫。 |
| eVarN | eVarN，即 `<eVar2>`...`<eVar>` | 轉換 eVar 名稱。您最多可以有 75 個 eVar ( eVar1 - eVar75 )。可以指定 eVar 名稱 (eVar12) 或易記名稱 (廣告行銷活動 3)。 |
| events | events | [事件字串](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=zh-Hant#vars)，格式語法與 s.events 變數相同。例如：scAdd,event1,event7 |
| hierN | hierN，即 `<hier2>`...`</hier2>` | 階層名稱。您最多可以有 5 個階層 ( hier1 - hier5 )。可以指定預設階層名稱 `hier2` 或易記名稱 (洋基隊)。 |
| homePage | homePage | Y 或 N -- 目前頁面是否為訪客的首頁。 |
| ipaddress | 不支援 | 訪客的 IP 位址。 |
| javaEnabled | javaEnabled | Y 或 N -- 訪客是否已啟用 Java。 |
| javaScriptVersion | javaScriptVersion | JavaScript 版本 (如 1.3)。 |
| language | 不支援 | 瀏覽器支援的語言。例如：`en-us`。 |
| linkName | linkName | 連結名稱。 |
| linkType | linkType | 連結的類型。支援的值包括： `d: Download link`, `e: Exit link`, `o: Custom link`. |
| linkURL | linkURL | 連結的 HREF。 |
| listn 例如 list2。 | 不支援 | 使用分隔字元的值清單，在傳給變數之後，會報告為個別的行項目以供製作報告。 |
| marketingCloudVisitorID | 不支援 | Marketing Cloud ID。請參閱[訪客身分識別](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant#id-service-api)和 Marketing Cloud 訪客 ID 服務 |
| 不支援 | charSet | 您的網站支援的字元集。例如 UTF-8、ISO-8859-1 等等。 |
| 不支援 | clickAction | 訪客點擊地圖的物件識別碼 (OID) |
| 不支援 | clickActionType | 訪客點擊地圖的物件識別碼類型 (OIDT) |
| 不支援 | clickContext | 訪客點擊地圖的頁面識別碼 (PID) |
| 不支援 | clickContextType | 訪客點擊地圖的頁面識別碼類型 (PIDT) |
| 不支援 | clickSourceID | 訪客點擊地圖的來源索引 (OI) |
| 不支援 | clickTag | 訪客點擊地圖的物件標記名稱 (OT) |
| 不支援 | scXmlVer | 行銷報表 XML 請求版本編號 (如 1.0)。 |
| 不支援 | timezone | 訪客所在時區與格林威治時間的小時差 (如 -8)。 |
| pageName | pageName | 頁面名稱 |
| pageType | pageType | 頁面類型 (例如「錯誤頁面」)。 |
| pageURL | pageURL | 頁面 URL (例如 https://www.example.com/index.html)。 |
| plugins | plugins | 以分號分隔的瀏覽器外掛程式名稱清單。 |
| products | products | 頁面上所有產品的清單。使用逗號分隔產品。例如：Sports;Ball;1;5.95,Toys; Top;1:1.99。 |
| prop1 - prop75 | propN，即 `<prop2>`...`</prop2>` | 屬性編號字串 (例如體育版)。 |
| propN | propN | 您的屬性的屬性值。 |
| purchaseID | purchaseID | 購買 ID 號碼。 |
| referrer | referrer | 頁面反向連結的 URL。 |
| reportSuiteID | s_account  | 指定您要提交資料的報表套裝。您應使用逗號分隔多個報表套件 ID。 |
| resolution | resolution | 螢幕解析度 (如 1024x768)。 |
| server | server | 伺服器字串。 |
| state | state | 轉換州字串。 |
| timestamp | 日期 | 使用 ISO 8601 日期格式 YYYY-MM-DDThh:mm:ss±UTC_offset (例如 2021-09-01T12:00:00-07:00) 或 Unix 時間格式 (自 1970 年 1 月 1 日起的總秒數)。 |
| trackingServer | 不支援 | 只能透過欄標題提供。 |
| transactionID | 不支援 | 用於將多個管道使用者活動繫結在一起以便進行報告的通用值。如需詳細資訊，請參閱[資料來源使用手冊](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=zh-Hant#data-sources)。 |
| userAgent | 不支援 | 使用者代理字串 |
| visitorID | visitorID | 訪客的 Analytics ID。請參閱[訪客身分識別](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)。 |
| zip | zip | 轉換郵遞區號。 |
