---
title: 可減輕瀏覽器 Cookie 限制之影響的選項
description: 了解如何減輕瀏覽器 Cookie 限制之影響，以改良 Adobe Analytics 的資料收集。
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
role: Admin
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 99%

---

# 可減輕瀏覽器 Cookie 限制之影響的選項

此文件說明當主要瀏覽器實施預防 Cookie 的追蹤措施時，可跨屬性和解決方案來保留永續性訪客身分識別的選項。

Adobe Analytics 仰賴第一方 Cookie 來記錄訪客在網站上的活動。 Analytics 也仰賴第三方 Cookie 來了解訪客在網站外的活動，例如在您擁有的其他網域上的活動。 許多瀏覽器都封鎖第三方 Cookie，而隨著 Chrome 即將取消支援 (目前計劃在 2024 年底取消)，大部分的第三方 Cookie 將無法使用。 所有瀏覽器都允許使用第一方 Cookie，但在 Apple 的 [ITP 預防追蹤](https://webkit.org/tracking-prevention)措施之下，這類 Cookie 在 Safari 和其他瀏覽器上的期限受到限制。 如需有關瀏覽器 Cookie 的目前限制的詳細資訊，請參閱 [Adobe Analytics 和瀏覽器 Cookie](cookies.md)。

這些瀏覽器限制反映了更大規模脫離匿名第三方追蹤將會朝向用戶與他們信任的品牌之間的明確資訊分享。 為了支援此行動，Adobe 為客戶提供方法來補充傳統 Cookie，其方式為包含透過其第一方關係所收集的持久性識別碼。

## Customer Journey Analytics 和 Cross Device Analytics

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant) 和[跨裝置分析](/help/components/cda/overview.md)允許使用者包含持久性識別碼 (例如雜湊登入) 和 Cookie。 這可讓您了解跨裝置的客戶歷程，若是 Customer Journey Analytics，則為跨線上和離線頻道：

* **Customer Journey Analytics** 建立在 Adobe Experience Platform 上，提供在 Analysis Workspace 中根據任何常見客戶 ID 結合線上和離線資料的靈活性。 您可以指定要用於任何特定分析的 ID，並探索 Analysis Workspace 中的資料。 Analytics Select、Prime 和 Ultimate 客戶均符合購買此附加產品的資格。

* **跨裝置分析**&#x200B;是傳統 Adobe Analytics 的增強功能，允許客戶對訪客使用替代識別碼。 此功能可讓您從以裝置為中心的觀點轉變為以人為中心的觀點。 Cross-Device Analytics 提供給 Analytics Ultimate 客戶使用。

## 伺服器端資料收集

伺服器端收集可靈活地提供您自己的識別碼，而不需仰賴瀏覽器機制來設定 Cookie。

您可以使用[資料插入 API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) 或[大量資料插入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)，提交資料至 Analytics 伺服器端。 建議將大量資料插入 API 用於新伺服器端的實施。 如需這兩個 API 的比較情況，請參閱「[我應該使用哪一個 Adobe Analytics 工具](/help/analyze/get-started/which-analytics-tool.md)」。

## 使用 Web SDK 的第一方裝置 ID (FPID)

使用 Adobe Experience Platform Web SDK，您可以選擇設定和管理您自己的裝置識別碼，而不是使用 Adobe 生成的 Experience Cloud ID (ECID)。 這些被稱為第一方裝置 ID (FPID)。 如需更多詳情，請參閱[此處](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=zh-Hant)。

## 詳細資訊

如需了解貴公司可採取哪些實用步驟來脫離第三方 Cookie，請參閱[借助 Adobe 獲得客戶並在無 Cookie 的世界中留住客戶](https://business.adobe.com/tw/solutions/cookieless.html)和深入的[超越第三方 Cookie 的思維：您通往無第三方 Cookie 的世界的完整指南](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)。

>[!MORELIKETHIS]
>
>[Adobe Analytics 與瀏覽器 Cookie](cookies.md)
