---
description: 連結到 github 上的 Adobe Analytics 管理員 API。
title: Adobe Analytics 1.4 API 終止更新常見問題
feature: Admin Tools
role: Admin
exl-id: 88769032-a7cd-4ca8-958f-3300a4bfe71f
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 4%

---

# Adobe Analytics 1.4 API 終止更新常見問題

## 生命週期結束(EOL)通知

**即將淘汰的專案？**

* Adobe Analytics 1.4 API

* Adobe Analytics WSSE 驗證

**何時關閉？**

這些服務將於2026年8月12日淘汰。 在此日期之後將無法再存取。

## 1.4 API

**這些服務是什麼？**

[Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/)是API的集合，可提供廣泛的動作，例如報告、分類、資料摘要和報告套裝設定。

**需要做什麼才能移轉？**

[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)提供1.4 API使用者的移轉路徑。 目前使用1.4 API的客戶可將其整合移轉至2.0 API (Adobe Analytics應用程式所依賴的相同API)，並利用最新功能。

2.0 API可讓您執行幾乎所有可在Analytics使用者介面中執行的動作，例如報告或管理元件如區段和計算量度。

**2.0 API是否提供與1.4 API相同的功能？**
1.4 API中可用的任何功能可以使用[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)來完成。 部分功能提供與1.4 API中相同的功能，可讓您執行幾乎所有可在Analytics使用者介面中執行的動作，例如報告或管理區段和計算量度等元件。

## WSSE驗證

**這些服務是什麼？**

WSSE驗證是Analytics 1.4 API支援的舊版驗證通訊協定。 已由[Adobe Developer Console](https://developer.adobe.com/console/home)中提供的OAuth驗證選項取代。

**需要做什麼才能移轉？**

WSSE客戶必須更新其驗證，才能使用Adobe Developer Console中布建的認證。 若要這麼做，請登入[Adobe Developer Console](https://developer.adobe.com/console/home)，為您的Analytics 2.0 API整合建立專案。 在OAuth使用者與OAuth伺服器對伺服器驗證方法之間選取。

## 問題

問：**這會影響我現有的Analytics APIAdobeIO專案嗎？**

答：任何使用Analytics 1.4 API的現有專案都將受到影響。 這些整合必須在EOL期限之前移轉至[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)。

問：**我已與使用Analytics API的其他產品或應用程式共用我的Adobe認證。 他們受到影響嗎？**

答：如果該產品或應用程式使用您的WSSE憑證和/或呼叫Analytics 1.4 API，則會受到影響，需要在EOL期限之前移轉。 請洽詢產品或應用程式供應商，以取得有關其移轉計畫和時程表的詳細資訊。

問：**我不確定我們正在使用哪個Adobe Analytics API。**

答：您可以透過在整合中呼叫的地址，識別您正在使用的API。

您可以呼叫下列任一URL來存取Adobe Analytics 1.4 API：
* https://api.omniture.com
* https://api3.omniture.com
* https://api4.omniture.com
* https://api5.omniture.com

透過呼叫下列URL存取[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)：
* https://analytics.adobe.io

如果您使用api*.omniture.com，則需要移轉至[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)。

問：**Adobe Analytics 2.0 API是否與1.4 API相同？ 如果沒有，最大的差異為何？**

答：Adobe Analytics 2.0 API與1.4 API並不相同，但提供的功能相當多，包括下列優點：

* 更簡單、更有效率的查詢方法加快回應時間，不需要輪詢

* 查詢及動態報告更新的程式化功能

* 更順暢的錯誤處理

* 彈性的功能，可完成您從Analysis Workspace完成的任何工作

* API呼叫與UI動作的一致性和相符性

* 存取Analysis Workspace中使用的所有Attribution IQ模型

* 存取Analysis Workspace中使用的所有異常偵測演演算法

* 與其他Experience Cloud產品整合的能力

* 增加多份劃分報告的容量

* 存取最新的Analytics功能

「[移轉至Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/)」指南會討論1.4和2.0 API之間的主要差異。 [Analytics 2.0 API常見問題集](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/)中也有其他資訊。

問：**這會影響資料收集嗎？**

答：Adobe Analytics 1.4 EOL不會影響您的標籤解決方案，例如Tags (先前稱為Adobe Launch)、WebSDK或AppMeasurement.js。 不過，如果您使用1.4資料來源或分類API來收集或增強資料，您必須將這些工作流程移轉至Adobe Analytics 2.0 API。 如需詳細資訊，請參閱[2.0 API端點指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/)。

問：**資料插入API是否受到影響？**

答：否，資料插入API不會受到Adobe Analytics 1.4 EOL的影響。

問：**如果我的問題沒有在這個FAQ中回答，該怎麼辦？**

答：如果您仍有疑問，請洽詢您的Adobe客戶代表。
