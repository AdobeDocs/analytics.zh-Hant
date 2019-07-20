---
description: 您必須符合這些 Experience Cloud 解決方案、服務及程式碼需求，才能實作伺服器端轉送。這些需求包括如何檢查程式碼版本和取得最新程式碼庫的指示。
seo-description: 您必須符合這些 Experience Cloud 解決方案、服務及程式碼需求，才能實作伺服器端轉送。這些需求包括如何檢查程式碼版本和取得最新程式碼庫的指示。
seo-title: 伺服器端轉送需求
solution: Audience Manager
title: 伺服器端轉送需求
uuid: e52c9292-b2 ed-4782-9594-c813 e4 f894 e1
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 伺服器端轉送需求

您必須符合這些 Experience Cloud 解決方案、服務及程式碼需求，才能實作伺服器端轉送。這些需求包括如何檢查程式碼版本和取得最新程式碼庫的指示。

## 解決方案需求

伺服器端轉送可與 [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html) 和 [Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) 及/或 [ Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) 搭配使用。

## 服務需求

Server-side forwarding requires the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/). Identity Service提供通用ID，可識別Experience Cloud所有解決方案中網站訪客的身分。您必須實作 ID 服務，伺服器端轉送才會運作。

## 程式碼版本

伺服器端轉送需使用下列 1.5 版 (或更新版本) 的程式碼庫。我們建議使用最新版本而非滿足最低版本需求，這才是最佳的作法。

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### 判斷您的程式碼庫版本

任何可監控瀏覽器發出之 HTTP 請求的工具，均可顯示 AppMeasurement 和訪客 API 程式碼的版本號碼。The `AppMeasurement_Module_AudienceManagement.js` does not contain or return a version ID. 下列範例說明版本 ID 在 `AppMeasurement.js` 和 `VisitorAPI.js` 程式碼中的表示方式。

* `AppMeasurement.js`： [Adobe Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html) 會傳回AppMeasurement版本，如下所示： `Version of Code | JS-1.5.1`。其他工具可能會使用不同標籤，但數值一律按照 `JS-X.X.X` 的模式，其中 `X` 為版本號碼。
* `VisitorAPI.js`：尋找 `d_visid_ver` 參數。It will show you the Visitor ID service like this: `d_visid_ver: 1.5.5`. 早於 1.5.2 版的訪客 API 程式碼不包含版本號碼。如果您的監控結果沒有傳回版本號碼，則您可能是使用舊版程式碼庫 (且必須升級)。