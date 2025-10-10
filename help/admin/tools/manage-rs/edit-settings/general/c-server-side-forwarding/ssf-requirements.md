---
description: 您必須符合這些 Experience Cloud 解決方案、服務及程式碼需求，才能實作伺服器端轉送。這些需求包括如何檢查程式碼版本和取得最新程式碼庫的指示。
solution: Analytics
title: 伺服器端轉送需求
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 100%

---

# 伺服器端轉送需求

您必須符合這些 Experience Cloud 解決方案、服務及程式碼需求，才能實作伺服器端轉送。這些需求包括如何檢查程式碼版本和取得最新程式碼庫的指示。

## 解決方案需求

伺服器端轉送可與 [Analytics](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics.html) 和 [Audience Manager](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlaudience-manager.html) 及/或 [ Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=zh-Hant) 搭配使用。

## 服務需求

伺服器端轉送需要[身分識別服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)才能執行。身分識別服務提供的通用 ID 可識別 Experience Cloud 中所有解決方案的網站訪客。您必須實作 ID 服務，伺服器端轉送才會運作。

## 程式碼版本

伺服器端轉送需使用下列 1.5 版 (或更新版本) 的程式碼庫。我們建議使用最新版本而非滿足最低版本需求，這才是最佳的作法。

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### 判斷您的程式碼庫版本

任何可監控瀏覽器發出之 HTTP 請求的工具，均可顯示 AppMeasurement 和訪客 API 程式碼的版本號碼。`AppMeasurement_Module_AudienceManagement.js` 不會包含或傳回版本 ID。下列範例說明版本 ID 在 `AppMeasurement.js` 和 `VisitorAPI.js` 程式碼中的表示方式。

* `AppMeasurement.js`：[Adobe 除錯程式](/help/implement/validate/debugger.md)傳回的 AppMeasurement 版本如下： `Version of Code | JS-1.5.1`。其他工具可能會使用不同標籤，但數值一律按照 `JS-X.X.X` 的模式，其中 `X` 為版本號碼。
* `VisitorAPI.js`：搜尋 `d_visid_ver` 參數。此參數會以下列方式顯示訪客 ID 服務：`d_visid_ver: 1.5.5`。早於 1.5.2 版的訪客 API 程式碼不包含版本號碼。如果您的監控結果沒有傳回版本號碼，則您可能是使用舊版程式碼庫 (且必須升級)。
