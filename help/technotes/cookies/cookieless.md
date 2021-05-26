---
title: 可減輕瀏覽器 Cookie 限制之影響的選項
description: 了解如何減輕瀏覽器 Cookie 限制之影響，以改良 Adobe Analytics 的資料收集。
source-git-commit: 6c354a343648162ce2951c52a70a688970e1304d
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 51%

---


# 可減輕瀏覽器 Cookie 限制之影響的選項

本檔案探討當主要瀏覽器實作Cookie的追蹤防止措施時，如何跨屬性和解決方案保留持續性訪客身分識別的選項。

Adobe Analytics 仰賴第一方 Cookie 來記錄訪客在網站上的活動。 Analytics 也仰賴第三方 Cookie 來了解訪客在網站外的活動，例如在您擁有的其他網域上的活動。 許多瀏覽器都封鎖第三方 Cookie，而隨著 Chrome 即將取消支援 (目前計劃在 2022 年取消)，大部分的第三方 Cookie 將無法使用。 所有瀏覽器都允許使用第一方 Cookie，但在 Apple 的 [ITP 預防追蹤](https://webkit.org/tracking-prevention)措施之下，這類 Cookie 在 Safari 和其他瀏覽器上的期限受到限制。 如需瀏覽器Cookie目前限制的詳細資訊，請參閱[Adobe Analytics和瀏覽器Cookie](cookies.md)。

這些瀏覽器限制反映了更大規模脫離匿名第三方追蹤將會朝向用戶與他們信任的品牌之間的明確資訊分享。 為了支援此行動，Adobe 為客戶提供方法來補充傳統 Cookie，其方式為包含透過其第一方關係所收集的持久性識別碼。

## Customer Journey Analytics 和 Cross Device Analytics

[AdobeCustomer Journey ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant) Analytics [和跨裝](/help/components/cda/overview.md) 置分析使用者，除了Cookie外，還可包含持久識別碼（例如雜湊登入）。這可讓您了解跨裝置的客戶歷程，若是Customer Journey Analytics，則可了解跨線上和離線管道的客戶歷程：

* **以Adobe Experience Platform** 為建置基礎的Customer Journey Analytics，可讓您根據任何常見客戶ID，靈活地在Analysis Workspace中結合線上和離線資料。您可以指定要用於任何指定分析的ID，並在Analysis Workspace中探索資料。 Analytics Select、Prime和Ultimate客戶均符合購買此附加產品的資格。

* **跨裝置分析** 是對傳統Adobe Analytics的增強功能，可讓客戶使用替代識別碼給訪客。此功能可讓您從以裝置為中心的檢視移至以人為中心的檢視。 Analytics Ultimate客戶可使用跨裝置分析。

## 伺服器端資料收集

伺服器端收集可靈活地提供您自己的識別碼，而不需仰賴瀏覽器機制來設定 Cookie。

您可以使用[資料插入API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md)或[大量資料插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，將資料提交至Analytics伺服器端。 建議新的伺服器端實作使用大量資料插入API。 如需這兩個 API 的比較情況，請參閱「[我應該使用哪一個 Adobe Analytics 工具](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html?lang=zh-Hant)」。

## 詳細資訊

如需您的企業從協力廠商Cookie轉移出去的實際步驟，請參閱[透過Adobe](https://business.adobe.com/solutions/cookieless.html)和深入的[第三方Cookie以外的思考，贏取並讓客戶留在無Cookie的世界中：無第三方Cookie的世界完整指南](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)。」

>[!MORELIKETHIS]
[Adobe Analytics 與瀏覽器 Cookie](cookies.md)>
>
