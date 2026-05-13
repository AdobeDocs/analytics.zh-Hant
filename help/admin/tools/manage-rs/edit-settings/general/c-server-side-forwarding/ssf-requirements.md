---
description: 您必須符合這些Experience Cloud解決方案、服務和程式碼需求，才能實作伺服器端轉送。 這些需求還包括如何檢查程式碼版本以及在何處取得最新程式碼程式庫的指示。
solution: Analytics
title: 伺服器端轉送需求
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
TQID: https://experienceleague.adobe.com/1GCflxlY4IpT-pPTr93FuOmxkJLC4baJe3Z2SGjj1So
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 326
ht-degree: 58%

---

# 伺服器端轉送需求

您必須符合這些Experience Cloud解決方案、服務和程式碼需求，才能實作伺服器端轉送。 這些需求還包括如何檢查程式碼版本以及在何處取得最新程式碼程式庫的指示。

## 解決方案需求

伺服器端轉送可與 [Analytics](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics.html) 和 [Audience Manager](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlaudience-manager.html) 及/或 [&#x200B; Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) 搭配使用。

## 服務需求

伺服器端轉送需要[身分識別服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)才能執行。 身分識別服務提供的通用 ID 可識別 Experience Cloud 中所有解決方案的網站訪客。 您必須實作 ID 服務，伺服器端轉送才會運作。

## 程式碼版本

伺服器端轉送需要下列程式碼程式庫的1.5版（或更新版本）。 我們建議您使用最新版本，而非下列所需的最低版本，當作最佳作法。

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### 判斷您的程式碼庫版本

任何可監控瀏覽器發出之 HTTP 請求的工具，均可顯示 AppMeasurement 和訪客 API 程式碼的版本號碼。 `AppMeasurement_Module_AudienceManagement.js` 不會包含或傳回版本 ID。 下列範例說明版本 ID 在 `AppMeasurement.js` 和 `VisitorAPI.js` 程式碼中的表示方式。

* `AppMeasurement.js`：[Adobe 除錯程式](/help/implement/validate/debugger.md)傳回的 AppMeasurement 版本如下： `Version of Code | JS-1.5.1`。 其他工具可能會使用不同標籤，但數值一律按照 `JS-X.X.X` 的模式，其中 `X` 為版本號碼。
* `VisitorAPI.js`：搜尋 `d_visid_ver` 參數。 此參數會以下列方式顯示訪客 ID 服務：`d_visid_ver: 1.5.5`。 1.5.2版之前的訪客API程式碼不包含版本號碼。 如果您的監視結果未傳回版本號碼，表示您可能使用的是舊版程式碼程式庫（且需要升級）。
