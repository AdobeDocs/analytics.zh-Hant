---
description: 跨裝置訪客身分識別可協助您連結多個裝置間的訪客。
keywords: Analytics 實施作業
subtopic: Visitors
title: 連結跨裝置的使用者
feature: Implementation Basics
exl-id: dfe278db-01de-4bba-b07a-66d52de1dbe2
role: Developer
source-git-commit: e242276f931e9939081b948a9d9ef8a087e16461
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 95%

---

# 連結跨裝置的使用者

>[!IMPORTANT]
>
>不建議您繼續使用這種跨裝置識別訪客的方法。請參閱元件使用指南中的[跨裝置分析](/help/components/cda/overview.md)。

跨裝置訪客身份識別可協助您連結多個裝置間的訪客。跨裝置訪客身份識別會使用 `visitorID` 變數，為使用者建立裝置間的關聯。識別不重複訪客時，`visitorID` 變數優先順序最高。

使用自訂訪客 ID 傳送點擊時，Adobe 會檢查是否有任何具有相符訪客 ID 的訪客輪廓。若有的話，自此之後都會使用系統中已存在的訪客輪廓，而不再使用先前的訪客輪廓。

通常會在驗證之後設定 `visitorID`，或是在訪客執行其他特定動作而讓您可加以唯一識別 (無論使用什麼裝置) 時設定。有效識別碼包括其使用者名稱的雜湊、電子郵件地址，或不含任何個人識別資訊的內部 ID。

客戶從每部裝置登入後，都會與相同的使用者輪廓相連結。如果訪客稍後登出裝置，仍會屬於相同的訪客輪廓，因為 Adobe 可辨識每部裝置上的瀏覽器 Cookie 屬於相同的訪客輪廓。Adobe 建議在刪除瀏覽器 Cookie 時盡可能使用 `visitorID` 變數。

## 限制

使用您自己的自訂訪客 ID，可讓您更深入控制訪客的識別方式，不過有其限制。

* **訪客重複資料刪除不具可回溯性**：如果訪客首次存取您的網站然後進行驗證，則會計為兩個不重複訪客。系統會自動產生一個一般 Analytics ID 的不重複訪客計數，另外會在其登入時計為另一個自訂訪客 ID 計數。每當訪客使用新裝置或清除其 Cookie 時，都會出現這種不重複訪客的重複資料。
* **與 Experience Cloud ID Service 不相容**：自從跨裝置訪客身份識別功能問世以來，Adobe 已推出功能更強大、更可靠的方式來跨裝置追蹤訪客。這些新的身分識別方法與自訂訪客 ID 覆寫不相容。如果您打算使用ID Service或跨裝置分析(CDA)，Adobe強烈建議不要使用`visitorID`變數。
