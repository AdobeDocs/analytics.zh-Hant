---
title: 完全處理資料來源終止服務
description: 大量資料插入API和完全處理資料來源之間終止連結和比較的原因。
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: f120c189228892e57e38e4d0e106eb3190326ff1
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 27%

---

# 完全處理資料來源終止服務

數年來，「完全處理資料來源」可讓您提交點擊層級的資料至Adobe Analytics。 此資料的處理方式與透過JavaScript程式庫和行動應用程式SDK收集的資料相同。 2020年，Adobe發佈了[大量資料插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，該API執行的功能與完全處理資料源相同，但具有其他功能。 本主題提供大量資料插入API所提供其他功能的詳細資訊，並概述檔案格式的差異。

自2021年3月25日起，Adobe將無法建立新的「完全處理資料來源」連線。 在2021年7月31日完全廢止服務之前，我們仍會支援現有連線。 除了標準檔案，我們還提供透過大量資料插入API](http://adobe.ly/aabdia)提交資料所需的[步驟逐步說明。

## 我們為什麼要終止此功能？

大量資料插入API(BDIA)提供額外功能，同時涵蓋完整處理支援的所有使用案例。 我們相信，使用大量資料插入API將能為您提供更理想的服務。

## 完整處理資料來源和大量資料插入API之間的主要差異

* 「大量資料插入」允許提交多個可同時處理的檔案。 您可以使用「訪客群組」來確保訪客的連續性和eVar歸因。
* 「大量資料插入」具備資料驗證和錯誤處理功能，因此移除了提交點擊資料的部分管理工作。
* 「大量資料插入」支援數個訪客ID選項。 您可以提交Analytics ID和Marketing CloudID（請參閱[Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)以了解更多資訊）。 此外，您也可以使用自己的ID作為[種子，以產生ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds)。
* 「大量資料插入」支援清單和上下文資料變數。
* 「大量資料插入」不支援Activity Map資料。

## 檔案格式和內容的主要差異

* 「大量資料插入」包含一些其他必要欄位。 如需詳細資訊，請參閱[檔案](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)。
* 為確保訪客的連續性和歸因性，「大量資料插入」需要依時間順序排序檔案中的列。 請參閱[訪客群組](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups)以了解各檔案間訪客活動的順序。
* 「大量資料插入」需要.csv壓縮為.gzip格式的檔案。
* BDIA使用「時間戳記」而非「日期」。

如需詳細資訊，請參閱「大量資料插入(BDIA)」和「完全處理資料來源(FPDS)」中可用欄位值的下列比較。

## BDIA和FPDS中可用欄位值的比較

| BDIA變數 | 完全處理欄變數 | 說明 |
| --- | --- | --- |
| aamlh | 不支援 | Adobe Audience Manager位置提示。 |
| browserHeight | browserHeight | 瀏覽器高度（像素，例如768） |
| browserWidth | browserWidth | 瀏覽器寬度（像素）（例如1024） |
| campaign | 行銷活動 | 轉換促銷活動追蹤代碼 |
| channel | 頻道 | 頻道字串（例如「運動區」） |
| colorDepth | colorDepth | 監視器色彩深度（以位元為單位，如24） |
| connectionType | connectionType | 訪客的連線類型（LAN或資料機） |
| contextData.key | 不支援 | 鍵值配對的指定方式為命名標題「contextData.product」或「contextData.color」 |
| cookiesEnabled | cookiesEnabled | `Y` 或 `N` 適用於訪客是否支援第一方工作階段cookie |
| currencyCode | currencyCode | 收入貨幣代碼（例如`USD`） |
| customerID.[customerIDType].authState | 不支援 | 訪客的驗證狀態。 支援的值為： 0、1、2、未知、已驗證、LOGGED_OUT或「（不區分大小寫）。 連續兩個單引號(&quot;)會導致查詢字串中遺漏值，這在進行點擊時會轉譯為0。 請注意，支援的authState數值表示下列項目： 0 = UNKNOWN, 1 = AUTHENTICATED, 2 = LOGGED_OUT。 customerIDType可以是任何英數字串，但應視為區分大小寫。 |
| customerID.[customerIDType].id | 不支援 | 要使用的客戶ID。 customerIDType可以是任何英數字串，但應視為區分大小寫。 |
| customerID.[customerIDType].isMCSeed | 不支援 | 無論這是否為Marketing Cloud訪客ID的種子。 支援的值為： 0、1、TRUE、FALSE、「（不區分大小寫）。 使用0、FALSE或兩個連續的單引號(&quot;)會導致查詢字串中遺漏值。 customerIDType可以是任何英數字串，但應視為區分大小寫。 |
| eVarN | eVarN，即`<eVar2>`..`<eVar>` | 轉換 eVar 名稱。您最多可以有 75 個 eVar ( eVar1 - eVar75)您可以指定eVar名稱(eVar12)或好記名稱（廣告促銷活動3）。 |
| events | 事件 | [事件字串](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars)，格式語法與s.events變數相同。例如：scAdd,event1,event7 |
| hierN。 | hierN，即`<hier2>`..`</hier2>` | 階層名稱。您最多可以有 5 個階層 ( hier1 - hier5)。 您可以指定預設階層名稱`hier2`或好記名稱（洋基）。 |
| homePage | homePage | Y 或 N -- 目前頁面是否為訪客的首頁。 |
| ipaddress | 不支援 | 訪客的IP位址。 |
| javaEnabled | javaEnabled | Y 或 N -- 訪客是否已啟用 Java。 |
| javaScriptVersion | javaScriptVersion | JavaScript 版本 (如 1.3)。 |
| language | 不支援 | 瀏覽器的支援語言。 例如：`en-us`。 |
| linkName | linkName | 連結名稱。 |
| linkType | linkType | 連結的類型。支援的值包括：  `d: Download link`、  `e: Exit link`、  `o: Custom link`。 |
| linkURL | linkURL | 連結的 HREF。 |
| listn例如list2。 | 不支援 | 一份分隔值清單，會傳入變數中，然後報告為個別行項目以供報告 |
| marketingCloudVisitorID | 不支援 | Marketing Cloud ID. 請參閱[訪客身分識別](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api)和Marketing Cloud訪客ID服務 |
| 不支援 | charSet | 支援的網站字元集。 如 UTF-8、ISO-8859-1 等等。 |
| 不支援 | clickAction | 訪客點擊地圖的物件識別碼 (OID) |
| 不支援 | clickActionType | 訪客點擊地圖的物件識別碼類型 (OIDT) |
| 不支援 | clickContext | 訪客點擊地圖的頁面識別碼 (PID) |
| 不支援 | clickContextType | 訪客點擊地圖的頁面識別碼類型 (PIDT) |
| 不支援 | clickSourceID | 訪客點擊地圖的來源索引 (OI) |
| 不支援 | clickTag | 訪客點擊地圖的物件標記名稱 (OT) |
| 不支援 | scXmlVer | 行銷報表 XML 請求版本編號 (如 1.0)。 |
| 不支援 | timezone | 訪客所在時區與格林威治時間的小時差 (如 -8)。 |
| pageName | pageName | 頁面名稱 |
| pageType | pageType | 頁面類型（例如「錯誤頁面」）。 |
| pageURL | pageURL | 頁面URL(例如https://www.example.com/index.html)。 |
| plugins | 外掛程式 | 瀏覽器外掛程式名稱清單（以分號分隔）。 |
| products | 產品 | 頁面上所有產品的清單。 請使用逗號分隔產品。 例如：運動；球；1;5.95，玩具；Top;1:1.99。 |
| prop1 - prop75 | propN，即`<prop2>`..`</prop2>` | 屬性#字串（例如「運動區」）。 |
| propN | propN | 您的屬性的屬性值。 |
| purchaseID | purchaseID | 購買 ID 號碼。 |
| referrer | 反向連結 | 頁面反向連結的 URL。 |
| reportSuiteID | s_account  | 指定您要提交資料的報表套裝。您應以逗號分隔多個報表套裝ID。 |
| resolution | 解析度 | 螢幕解析度 (如 1024x768)。 |
| server | 伺服器 | 伺服器字串。 |
| state | state | 轉換州字串。 |
| timestamp | 日期 | 使用ISO 8601日期格式YYYY-MM-DDThh:mm:ss±UTC_offset(例如2021-09-01T12:00:00-07:00)或Unix時間格式（自1970年1月1日起的總秒數）。 |
| trackingServer | 不支援 | 只能通過列標題提供。 |
| transactionID | 不支援 | 用於將多個管道使用者活動繫結在一起以便進行報告的通用值。如需詳細資訊，請參閱[資料來源使用手冊](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources)。 |
| userAgent | 不支援 | 用戶代理字串 |
| visitorID | visitorID | 訪客的Analytics ID。 請參閱[訪客身分識別](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en)。 |
| zip | zip | 轉換郵遞區號。 |
