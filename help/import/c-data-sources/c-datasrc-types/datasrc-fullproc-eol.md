---
title: 完全處理資料源的生命週期結束
description: 批量資料插入API與完全處理資料源之間連結結束和比較的原因。
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 27%

---

# 完全處理資料源的生命週期結束

幾年來，「完全處理資料源」使您能夠向Adobe Analytics提交命中級資料。 此資料的處理方式與通過我們的JavaScript庫和移動應用SDK收集的資料相同。 2020年，Adobe [批量資料插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)執行與「完全處理資料源」相同的功能，但具有附加功能。 本主題提供有關批量資料插入API提供的其他功能的詳細資訊，並概述檔案格式的差異。

從2021年3月25日起，Adobe阻止新的完全處理資料源連接的建立。 支援現有連接，直到2022年1月31日完全棄用該服務。 除了標準文檔外，我們還提供了 [通過批量資料插入API提交資料所需的步驟](https://adobe.ly/aabdia)。

## 為什麼我們要終止這個功能？

批量資料插入API(BDIA)提供了附加功能，同時涵蓋了完全處理支援的所有使用情形。 使用批量資料插入API可以更好地為您服務。

## 完全處理資料源與批量資料插入API的關鍵區別

* 批量資料插入允許提交多個檔案，這些檔案可以並行處理。 您可以使用訪問者組來確保訪問者的連續性和eVar屬性。
* 批量資料插入具有資料驗證和錯誤處理功能，因此刪除了提交命中資料的一些管理工作。
* 批量資料插入支援訪問者ID的多個選項。 您可以同時提交分析ID和Marketing CloudID(請參閱 [身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant) 瞭解更多資訊)。 另外，您可以使用自己的ID [用於生成ECID的種子](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds)。
* 批量資料插入支援清單和上下文資料變數。
* 批量資料插入不支援Activity Map資料。

## 檔案格式和內容的關鍵差異

* 批量資料插入包含一些其他必需欄位。 查看 [文檔](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) 的雙曲餘切值。
* 為確保訪問者的連續性和屬性，批量資料插入要求按時間順序對檔案中的行進行排序。 請參閱 [訪問者組](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) 瞭解跨檔案訪問者活動的順序。
* 批量資料插入要求檔案以.gzip格式壓縮。
* BDIA使用「timestamp」而不是「date」。

有關詳細資訊，請參閱以下對批量資料插入(BDIA)和完全處理資料源(FPDS)中可用欄位值的比較。

## BDIA和FPDS中可用欄位值的比較

| BDIA變數 | 完全處理欄變數 | 說明 |
| --- | --- | --- |
| aamlh | 不支援 | Adobe Audience Manager位置提示。 |
| browserHeight | 瀏覽器高度 | 瀏覽器高度（以像素為單位）（例如，768） |
| browserWidth | 瀏覽器寬度 | 瀏覽器寬度（以像素為單位）（例如1024） |
| campaign | 活動 | 轉換市場活動跟蹤代碼 |
| channel | 通道 | 通道字串（例如，Sports Section） |
| colorDepth | 顏色深度 | 監視位中的顏色深度（例如，24） |
| connectionType | 連接類型 | 訪問者的連接類型（LAN或調制解調器） |
| contextData.key | 不支援 | 鍵值對是通過命名標題&quot;contextData.product&quot;或&quot;contextData.color&quot;來指定的 |
| cookiesEnabled | Cookie已啟用 | `Y` 或 `N` 如果訪問者支援第一方會話cookie |
| currencyCode | currencyCode | 收入幣種代碼(例如， `USD`) |
| 客戶ID。[customerIDType].authState | 不支援 | 訪問者的已驗證狀態。 支援的值為： 0、1、2、UNKNOWN、AUTHENTICATED、LOGGED_OUT或「（不區分大小寫）。 兩個連續的單引號(&quot;)導致查詢字串中省略該值，當命中時，該值將轉換為0。 請注意，支援的authState數值表示以下值： 0 = UNKNOWN, 1 = AUTHENTICATED, 2 = LOGGED_OUT。 customerIDType可以是任何字母數字字串，但應視為區分大小寫。 |
| 客戶ID。[customerIDType].id | 不支援 | 要使用的客戶ID。 customerIDType可以是任何字母數字字串，但應視為區分大小寫。 |
| 客戶ID。[customerIDType].isMCSeed | 不支援 | 這是否是Marketing Cloud訪問者ID的種子。 支援的值為： 0、1、TRUE、FALSE、「（不區分大小寫）。 使用0、FALSE或兩個連續的單引號(&quot;)會導致從查詢字串中省略該值。 customerIDType可以是任何字母數字字串，但應視為區分大小寫。 |
| eVarN | eVarN，即 `<eVar2>`...`<eVar>` | 轉換 eVar 名稱。您最多可以有 75 個 eVar ( eVar1 -eVar75)可以指定eVar名稱(eVar12)或友好名稱（廣告市場活動3）。 |
| events | 事件 | [事件字串](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars)，使用與s.events變數相同的語法格式化。 例如：scAdd,event1,event7 |
| hierN。 | hierN，即 `<hier2>`...`</hier2>` | 階層名稱。您最多可以有 5 個階層 ( hier1 - hier5)。 可以指定預設層次結構名稱 `hier2` 或者友好的名字（洋基隊）。 |
| homePage | 首頁 | Y 或 N -- 目前頁面是否為訪客的首頁。 |
| ipaddress | 不支援 | 訪問者的IP地址。 |
| javaEnabled | javaEnabled | Y 或 N -- 訪客是否已啟用 Java。 |
| javaScriptVersion | javaScriptVersion | JavaScript 版本 (如 1.3)。 |
| language | 不支援 | 瀏覽器支援的語言。 例如：`en-us`。 |
| linkName | 連結名稱 | 連結名稱。 |
| linkType | 連結類型 | 連結的類型。支援的值包括： `d: Download link`。 `e: Exit link`。 `o: Custom link`。 |
| linkURL | 連結URL | 連結的 HREF。 |
| listn例如，list2。 | 不支援 | 傳遞到變數中，然後作為單獨行項報告以供報告的值的分隔清單 |
| 營銷CloudVisitorID | 不支援 | Marketing Cloud ID. 請參閱 [訪問者身份](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api) 和Marketing Cloud訪客身份服務 |
| 不支援 | charSet | 網站支援的字元集。 如 UTF-8、ISO-8859-1 等等。 |
| 不支援 | clickAction | 訪客點擊地圖的物件識別碼 (OID) |
| 不支援 | clickActionType | 訪客點擊地圖的物件識別碼類型 (OIDT) |
| 不支援 | clickContext | 訪客點擊地圖的頁面識別碼 (PID) |
| 不支援 | clickContextType | 訪客點擊地圖的頁面識別碼類型 (PIDT) |
| 不支援 | clickSourceID | 訪客點擊地圖的來源索引 (OI) |
| 不支援 | clickTag | 訪客點擊地圖的物件標記名稱 (OT) |
| 不支援 | scXmlVer | 行銷報表 XML 請求版本編號 (如 1.0)。 |
| 不支援 | timezone | 訪客所在時區與格林威治時間的小時差 (如 -8)。 |
| pageName | 頁名 | 頁面名稱 |
| pageType | pageType | 頁面類型（例如「錯誤頁面」）。 |
| pageURL | 頁面URL | 頁面URL(例如https://www.example.com/index.html)。 |
| plugins | 插件 | 以分號分隔的瀏覽器插件名稱清單。 |
| products | 產品 | 頁面上所有產品的清單。 用逗號分隔產品。 例如：運動；球；1;5.95，玩具；頂部；1:1.99。 |
| prop1 - prop75 | propN，即 `<prop2>`...`</prop2>` | 屬性#字串（例如，Sports Section）。 |
| propN | propN | 您的屬性的屬性值。 |
| purchaseID | 採購ID | 購買 ID 號碼。 |
| referrer | 引用者 | 頁面反向連結的 URL。 |
| reportSuiteID | s_account  | 指定您要提交資料的報表套裝。您應使用逗號分隔多個報表套件ID。 |
| resolution | 決議 | 螢幕解析度 (如 1024x768)。 |
| server | 伺服器 | 伺服器字串。 |
| state | 狀態 | 轉換州字串。 |
| timestamp | 日期 | 使用YYYY-MM-DDThh的ISO 8601日期格式:mm:ss±UTC_offset(例如，2021-09-01T12:00:00-07:00)或Unix時間格式（自1970年1月1日以來已用的秒數）。 |
| trackingServer | 不支援 | 只能通過列標題提供。 |
| transactionID | 不支援 | 用於將多個管道使用者活動繫結在一起以便進行報告的通用值。有關詳細資訊，請參見 [《資料源使用手冊》](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources)。 |
| userAgent | 不支援 | 用戶代理字串 |
| visitorID | 訪問者ID | 訪問者分析ID。 請參閱 [訪問者身份](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en)。 |
| zip | 郵遞區號 | 轉換郵遞區號。 |
