---
title: 完全處理資料來源的服務終止
description: 進一步了解全面處理資料來源的服務終止公告。
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 12%

---

# 完全處理資料來源的服務終止

過去，完全處理資料來源可讓組織將點擊層級資料提交至Adobe Analytics。 此資料的處理方式與透過傳統資料收集方式（例如AppMeasurement）收集的資料相同。 在2020年，Adobe發佈 [大量資料插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)，執行的功能與完整處理資料來源相同，但具有其他功能。 本頁提供大量資料插入API所提供其他功能的詳細資訊，並概述檔案格式的差異。

2021年3月25日，Adobe無法建立新的完全處理資料來源連線。 2022年1月31日，所有完整處理資料服務都已停用。

## 完全處理資料來源和大量資料插入API之間的主要差異

* 大量資料插入可讓您提交多個檔案以進行平行處理。 訪客群組可確保訪客的連續性和eVar歸因。
* 大量資料插入具有資料驗證和錯誤處理功能，移除了提交點擊資料的部分管理工作。
* 大量資料插入支援多種訪客ID識別方法。
* 大量資料插入包含一些其他必填欄位：訪客身分識別欄，即 `pageName` （或等同連結）, `reportSuiteID`, `timestamp`，和 `userAgent`.
* 為確保訪客的連續性和歸因，大量資料插入需要檔案中的列按時間順序排序。 請參閱[訪客群組](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/)以了解跨檔案訪客活動的排序。
* 大量資料插入需要.csv壓縮為.gzip格式的檔案。
* BDIA使用 `timestamp` 而非 `date`.

## BDIA與完全處理資料來源的變數比較

下列變數已導入「大量資料插入」中，先前在完全處理資料來源時無法使用：

* **`aamlh`**:Adobe Audience Manager位置提示。
* **`contextData.key`**: [上下文資料變數](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**:Experience CloudID服務變數。 包含 `id`、`authState` 和 `isMCSeed`。
* **`hints`**: [用戶端提示](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=zh-Hant) 變數。 包含 `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion`，和 `wow64`.
* **`ipaddress`**:訪客的IP位址。
* **`language`**:此 [語言](/help/components/dimensions/language.md) 維度。
* **`list1`** - **`list3`**: [清單變數](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**:訪客的Experience CloudID。
* **`tnta`**:用於的Target資料裝載 [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) 整合。
* **`trackingServer`**: 變數.[`trackingServer`](/help/implement/vars/config-vars/trackingserver.md)
* **`transactionID`**: 變數.[`transactionID`](/help/implement/vars/page-vars/transactionid.md)
* **`userAgent`**:裝置的使用者代理字串。

「大量資料插入」不支援下列變數：

* **`charSet`**: 變數. [`charSet`](/help/implement/vars/config-vars/charset.md)大量資料插入僅支援UTF-8。
* **`timezone`**:訪客的時區以小時為單位，與GMT時差不同。
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**:用於Activity Map資料收集的變數。