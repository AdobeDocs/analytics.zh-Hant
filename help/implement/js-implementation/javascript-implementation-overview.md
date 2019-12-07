---
description: 資料必須傳送至報表套裝以顯示於報表中，才能開始使用 Analytics。
keywords: Analytics Implementation;javascript;javascript implementation;appmeasurement;download appmeasurement;Identity Service;visitorapi.js;caching;appmeasurement compression
title: JavaScript 實作概觀
topic: Developer and implementation
uuid: bb661d8c-faf9-4454-ac3c-0c1a4c0a9336
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript 實作概觀

資料必須傳送至報表套裝以顯示於報表中，才能開始使用 Analytics。

若要將資料傳送至 [!DNL Analytics]，建議您使用 [Launch](/help/implement/implement-with-launch/create-analytics-property.md)，這是最簡單的方法。但是，某些情況下，您可能會想使用舊式的 JavaScript 方法實施 Analytics。

> [!NOTE]本節將說明 Analytics 的傳統實施方法。所有 Analytics 客戶皆能夠存取 [Launch](/help/implement/implement-with-launch/create-analytics-property.md)，這是部署 Experience Cloud 標籤的標準方法。

## 實施步驟 {#section_73961BAD5BB4430A95E073DE5C026277}

若想順利實施具有程式碼的頁面來收集資料，您必須能夠存取您的主控伺服器以便將新內容上傳至網站。此外，讓現有網站實施程式碼，也會有幫助。

下列步驟將帶領您進行基本的 Analytics 實施。

| 任務 | 說明 |
|--- |--- |
| 1. 下載 JavaScript 適用的 AppMeasurement 和 ID 服務。 | 透過 Experience Cloud 登入 Analytics。您可從 Analytics &gt; 管理員 &gt; 代碼管理器取得下載檔案。此下載 zip 包中包含多個檔案。AppMeasurement.js 和 VisitorAPI.js 為實施 Analytics 時的相關檔案。 |
| 2. 設定 Identity 服務(先前稱為訪客 ID 服務)。 | See [Set up the Identity Service for Analytics](https://docs.adobe.com/content/help/en/id-service/using/home.html) |
| 3. 更新 `AppMeasurement.js`。 | Copy the [example AppMeasurement.js code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) and paste it at the beginning of your `AppMeasurement.js` file. 至少更新下列變數:<ul><li>s.account="INSERT-RSID-HERE"</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>如果 [您不確定這些值，請參閱正確填入trackingServer和trackingServerSecure變數](https://helpx.adobe.com/analytics/kb/determining-data-center.html) ，或連絡Client Care。 如果變數未正確設定，您的實施將無法正確收集資料。</br> |
| 4. 託管 `AppMeasurement.js` 和 `VisitorAPI.js`。 | 這些核心 JavaScript 檔案必須放置您網站所有頁面都能存取的網站伺服器上。下一個步驟需要用到這些檔案的路徑。 |
| 5. 在所有網站頁面上參考 `AppMeasurement.js` 和 `VisitorAPI.js`。 | <ul><li>在每一頁的 `head` 或 `body` 標籤中新增下列程式碼行，加入訪客 ID 服務(`VisitorAPI.js` 必須放在 `AppMeasurement.js` 之前)。<br>`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</br></li><li>在每一頁的 `head` 或 `body` 標籤中新增下列程式碼行，加入 JavaScript 適用的 AppMeasurement:<br>`script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</br></li></ul> |
| 6. 更新並部署頁面程式碼。 | Copy the [Example Page Code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) and paste it just after the opening `body` tag on each page you want to track. 至少更新下列變數:<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s.pageName="INSERT-NAME-HERE" (for example, s.pageName=document.title)</li></ul> |
| 7. 使用 Experience Cloud Debugger 驗證是否已傳送資料。 | 安裝 [ Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2)。安裝後，載入您已部署頁面程式碼的頁面並開啟除錯程式。除錯程式會顯示已傳送之收集資料的詳細資料. |

## 快取 {#section_4E2D1D962DF046418134C43CFC49AD4A}

JavaScript 檔案初始載入後會置於訪客瀏覽器的快取中，通常一個工作階段不會下載超過一次。此檔案即使用於網站上的每個頁面，也不會下載至每個頁面上。大部分網站上的使用者每個工作階段會進行多次頁面檢視，所以將多次使用的 JavaScript 傳輸至此檔案可以減少整體下載資料量。

## 壓縮 JavaScript 適用的 AppMeasurement {#section_C10BBC84C81C414088F97363D29E021B}

若您對 H 程式碼的頁面寬度 (大小) 有所顧慮 (JavaScript 1.0 適用的 AppMeasurement 會預先壓縮)，Adobe 建議您考慮使用 GZIP 來壓縮此檔案。所有主要瀏覽器都可支援 GZIP，且在壓縮及解壓縮核心 [!DNL s_code.js] JavaScript 檔案的效能上，GZIP 都優於 JavaScript 壓縮。

下列連結有助於說明如何使用 GZIP 功能在您的網站上處理 [!DNL s_code.js] JavaScript 程式碼的壓縮: 

[Apache 模組 mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[使用 Tomcat 和 Flex 啟用 gzip 壓縮](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
