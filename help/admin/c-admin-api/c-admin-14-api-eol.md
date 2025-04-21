---
description: Adobe Analytics 1.4 API生命週期結束通知的詳細資料。
title: Adobe Analytics 1.4 API 終止更新常見問題
feature: Admin Tools
role: Admin
exl-id: 88769032-a7cd-4ca8-958f-3300a4bfe71f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 4%

---

# Adobe Analytics 1.4 API 終止更新常見問題

Adobe計畫在&#x200B;**2026年8月12日**&#x200B;淘汰Adobe Analytics 1.4 API。 在此日期之後將無法再存取。 本公告直接影響下列專案：

* Adobe Analytics 1.4 API，不包括資料插入API
* Adobe Analytics WSSE 驗證

## 1.4 API

[Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/)提供多種動作，例如報告、分類、資料摘要和報告套裝設定。 它們正遭淘汰，而改用[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)。 2.0 API可讓您執行幾乎所有可在Analytics使用者介面中執行的動作，例如報告或管理元件如區段和計算量度。

Adobe為1.4 API使用者提供[移轉路徑](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/)。 您可以將整合移轉至2.0 API (與Adobe Analytics應用程式相依的API相同)並利用最新功能。 1.4 API中可用的任何功能可以使用[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)來完成。

## WSSE驗證

WSSE驗證是Analytics 1.4 API支援的舊版驗證通訊協定。 已由[Adobe Developer Console](https://developer.adobe.com/console/home)中提供的OAuth驗證選項取代。 使用WSSE驗證的專案必須將其憑證更新為Adobe Developer Console中布建的憑證。 若要這麼做，請登入[Adobe Developer Console](https://developer.adobe.com/console/home)，為您的Analytics 2.0 API整合建立專案。 選取OAuth使用者或OAuth伺服器對伺服器驗證方法。

## 常見問題

+++**這會影響我現有的Analytics API Adobe IO專案嗎？**

任何使用Analytics 1.4 API的現有專案都會受到影響。 這些整合必須在EOL期限之前移轉至[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)。

+++

+++**我已與使用Analytics API的其他產品或應用程式共用我的Adobe認證。 他們受到影響嗎？**

如果該產品或應用程式使用您的WSSE憑證和/或呼叫Analytics 1.4 API，則會受到影響，且必須在EOL期限之前移轉。 請洽詢產品或應用程式提供者，以取得其移轉計畫和時程表的詳細資訊。

+++

+++**如何判斷我的專案使用哪個API？**

API呼叫的基本URL會決定您的專案使用的API版本。 Adobe Analytics 1.4 API會使用下列URL：
* `https://api.omniture.com`
* `https://api3.omniture.com`
* `https://api4.omniture.com`
* `https://api5.omniture.com`

[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)使用下列URL：

* `https://analytics.adobe.io`

如果您的任何API專案使用`api*.omniture.com`，則會使用Adobe Analytics 1.4 API，且必須移轉至2.0 API。

+++

+++**此生命週期結束是否會影響資料收集？**

Adobe Analytics 1.4 EOL不會影響您的標籤解決方案，例如標籤(原稱為Adobe Launch)、Web SDK或AppMeasurement。 不過，如果您使用1.4資料來源或分類API來增強資料，必須將這些工作流程移轉至Adobe Analytics 2.0 API。

此資料插入API不受此生命週期結束公告的影響。 雖然Adobe計畫繼續支援資料插入API，但Adobe建議改用[大量資料插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)。

+++

如果您對於本頁未回答的此產品壽命結束公告有其他問題，請聯絡您的Adobe客戶團隊。
