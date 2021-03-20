---
title: 完全處理資料來源的生命週期結束
description: 批量資料插入API和完全處理資料源之間連結終止和比較的原因。
translation-type: tm+mt
source-git-commit: 2e077db74b7719f49aec513fc99dad33a4d5b831
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 9%

---


# 完全處理資料來源的生命週期結束

數年來，「完全處理資料來源」可讓您提交點擊層級資料至Adobe Analytics。 此資料的處理方式與透過我們的JavaScript程式庫和行動應用程式SDK收集的資料相同。 2020年，Adobe發佈了[批量資料插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，該API執行的功能與完全處理資料源相同，但具有附加功能。 本主題提供大量資料插入API提供之其他功能的詳細資訊，並概述檔案格式的差異。

自2021年3月25日起，Adobe將阻止建立新的「完全處理資料來源」連線。 在服務完全不再提倡之前，將繼續支援現有的連線。 取消日期將於2021年進行，但具體日期尚未確定。

## 我們為什麼要終止此功能？

大量資料插入API(BDIA)提供其他功能，同時涵蓋「完全處理」支援的所有使用案例。 我們相信，使用大量資料插入API將能為您提供更好的服務。

## 完全處理資料來源與大量資料插入API之間的主要差異

* 「大量資料插入」允許提交多個可並行處理的檔案。 您可以使用「訪客群組」來確保訪客的連續性和eVar歸因。
* 「大量資料插入」具備資料驗證和錯誤處理功能，因此移除了提交點擊資料的部分管理工作。
* 「大量資料插入」支援數個訪客ID選項。 您可以同時提交Analytics ID和Marketing CloudID（請參閱[Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)以瞭解詳細資訊）。 此外，您也可以使用自己的ID做為[種子，以產生ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds)。
* 大量資料插入支援清單和上下文資料變數。
* 大量資料插入不支援Activity Map資料。

## 檔案格式和內容的主要差異

* 「大量資料插入」有一些其他必要欄位。 如需詳細資訊，請參閱[檔案](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)。
* 為確保訪客的連續性和歸因，「大量資料插入」要求檔案中的列依時間順序排序。 請參閱[訪客群組](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups)以瞭解跨檔案的訪客活動順序。
* 「大量資料插入」需要檔案以。gzip格式壓縮為。csv。
* BDIA使用「時間戳記」而非「日期」。

如需詳細資訊，請參閱「大量資料插入(BDIA)」和「完全處理資料來源(FPDS)」中可用欄位值的下列比較。

## BDIA和FPDS中可用欄位值的比較

| BDIA、FPDS、兩者 | BDIA變數 | 完全處理欄變數 | 說明 |
| --- | --- | --- | --- |
| BDIA | aamlh | 不支援 | Adobe Audience Manager位置提示。 請參閱下方地區清單AAM表格中的有效ID值。 |
|   | browserHeight | browserHeight | 瀏覽器高度（以像素為單位，例如768） |
|   | browserWidth | browserWidth | 瀏覽器寬度（以像素為單位，例如1024） |
|   | campaign | 促銷活動 | 轉換促銷活動追蹤代碼 |
|   | channel | 頻道 | 頻道字串（例如「運動區域」） |
|   | colorDepth | colorDepth | 以位元表示的螢幕色深（例如24） |
|   | connectionType | connectionType | 訪客的連線類型（LAN或資料機） |
| BDIA | contextData.key | 不支援 | 索引鍵值配對是透過命名標題&quot;contextData.product&quot;或&quot;contextData.color&quot;來指定 |
|   | cookiesEnabled | cookiesEnabled | `Y` 或 `N` 若訪客支援第一方作業Cookie |
|   | currencyCode | currencyCode | 收入貨幣代碼（例如`USD`） |
| BDIA | customerID。[customerIDType].authState | 不支援 | 訪客的已驗證狀態。 支援的值有： 0、1、2、未知、已驗證、LOGGED_OUT或「（不區分大小寫）。 兩個連續的單引號(&quot;)會使查詢字串中的值被省略，在進行點擊時，此值會轉換為0。 請注意，支援的authState數值表示： 0 =未知， 1 =已驗證， 2 = LOGGED_OUT。 customerIDType可以是任何英數字串，但應視為區分大小寫。 |
| BDIA | customerID。[customerIDType].id | 不支援 | 要使用的客戶ID。 customerIDType可以是任何英數字串，但應視為區分大小寫。 |
| BDIA | customerID。[customerIDType].isMCSeed | 不支援 | 這是否為Marketing Cloud訪客ID的種子。 支援的值有： 0、1、TRUE、FALSE、「（不區分大小寫）。 使用0、FALSE或兩個連續的單引號(&quot;)會使查詢字串中遺漏該值。 customerIDType可以是任何英數字串，但應視為區分大小寫。 |
