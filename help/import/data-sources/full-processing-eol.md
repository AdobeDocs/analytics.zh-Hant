---
title: 完整處理資料來源的生命週期結束
description: 深入瞭解完整處理資料來源的生命週期結束公告。
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 4%

---

# 完整處理資料來源的生命週期結束

完整處理資料來源歷來可讓組織將點選層級資料提交至Adobe Analytics。 此資料的處理方式與透過傳統資料收集方法(例如AppMeasurement)收集的資料相同。 在2020年，Adobe發行了[大量資料插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)，它執行與完整處理資料來源相同的功能，但具有附加功能。 本頁提供大量資料插入API所提供其他功能的詳細資訊，並概述檔案格式的差異。

2021年3月25日，Adobe禁止建立新的完整處理資料來源連線。 在2022年1月31日，所有完整處理資料服務都已停用。

## 完整處理資料來源和大量資料插入API之間的主要差異

* 大量資料插入可讓您提交多個檔案以進行平行處理。 訪客群組可確保訪客連續性和eVar歸因。
* 大量資料插入具有資料驗證和錯誤處理功能，可移除提交點選資料的一些管理工作。
* 大量資料插入支援多種訪客ID識別方法。
* 大量資料插入有一些額外的必要欄位：訪客身分識別欄、`pageName` （或同等連結）、`reportSuiteID`、`timestamp`和`userAgent`。
* 為確保訪客連續性和歸因，大量資料插入要求檔案中的列依時間順序排序。 請參閱[訪客群組](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/)以了解跨檔案訪客活動的排序。
* 大量資料插入需要以.gzip格式壓縮的.csv檔案。
* BDIA使用`timestamp`而非`date`。

## BDIA和完整處理資料來源之間的變數比較

大量資料插入引進了以下變數，這些變數先前在完整處理資料來源中無法使用：

* **`aamlh`**： Adobe Audience Manager位置提示。
* **`contextData.key`**： [內容資料變數](/help/implement/vars/page-vars/contextdata.md)。
* **`customerID`**：Experience Cloud識別碼服務變數。 包含 `id`、`authState` 和 `isMCSeed`。
* **`hints`**： [使用者端提示](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=zh-Hant)變數。 包含`bitness`、`brands`、`mobile`、`model`、`platform`、`platformversion`和`wow64`。
* **`ipaddress`**：訪客的IP位址。
* **`language`**： [語言](/help/components/dimensions/language.md)維度。
* **`list1`** - **`list3`**： [清單變數](/help/implement/vars/page-vars/list.md)。
* **`marketingCloudVisitorID`**：訪客的Experience CloudID。
* **`tnta`**： [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=zh-Hant)整合中所使用的Target資料裝載。
* **`trackingServer`**： [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md)變數。
* **`transactionID`**： [`transactionID`](/help/implement/vars/page-vars/transactionid.md)變數。
* **`userAgent`**：裝置的使用者代理字串。

下列變數不支援透過大量資料插入：

* **`charSet`**： [`charSet`](/help/implement/vars/config-vars/charset.md)變數。 大量資料插入僅支援UTF-8。
* **`timezone`**：訪客從GMT時區位移（以小時為單位）。
* **`clickAction`**、**`clickActionType`**、**`clickContext`**、**`clickContextType`**、**`clickSourceID`**、**`clickTag`**：Activity Map資料收集中使用的變數。
