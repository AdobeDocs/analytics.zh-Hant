---
title: 可降低瀏覽器Cookie限制影響的選項
description: 瞭解如何降低瀏覽器Cookie限制的影響，以改善Adobe Analytics的資料收集。
source-git-commit: 6c354a343648162ce2951c52a70a688970e1304d
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 5%

---


# 可降低瀏覽器Cookie限制影響的選項

本檔案討論當主要瀏覽器實施Cookie的追蹤防範措施時，可跨屬性和解決方案保留永久性訪客識別的選項。

Adobe Analytics依賴第一方Cookie來記錄訪客的網站活動。 Analytics也依賴第三方Cookie來瞭解訪客的離站活動，例如您擁有之其他網域的活動。 協力廠商Cookie在許多瀏覽器上都會遭到封鎖，Chrome即將移除的支援（目前計畫於2022年推出）將無法使用。 第一方Cookie可在所有瀏覽器上使用，但Apple的[ITP追蹤預防](https://webkit.org/tracking-prevention)措施下的Safari和其他瀏覽器有限期。 如需瀏覽器Cookie目前限制的詳細資訊，請參閱[Adobe Analytics和瀏覽器Cookie](cookies.md)。

這些瀏覽器限制反映出，用戶與其信任的品牌之間已逐漸從匿名第三方追蹤轉向明確分享資訊。 為支援此動作，Adobe可讓客戶加入透過第一方關係收集的持久識別碼，以補充傳統Cookie。

## Customer Journey Analytics與跨裝置分析

[Adobe客戶歷](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) 程分析 [和跨裝置](/help/components/cda/overview.md) 分析使用者，除了Cookie外，還可包含耐用的識別碼，例如雜湊登入。這可讓您瞭解跨裝置的客戶歷程，在Customer Journey Analytics的情況下，還可瞭解跨線上和線下通道的客戶歷程：

* **客戶歷程分** 析以Adobe Experience Platform為基礎，根據任何常見的客戶ID，提供在Analysis Workspace結合線上和離線資料的彈性。您可以指定要用於任何指定分析的ID，並探索Analysis Workspace的資料。 Analytics Select、Prime和Ultimate客戶有資格將此產品作為附加產品購買。

* **跨裝置分析** 是對傳統Adobe Analytics的增強功能，可讓客戶為訪客使用替代識別碼。此功能可讓您從裝置導向檢視移至人本導向檢視。 跨裝置分析適用於Analytics Ultimate客戶。

## 伺服器端資料收集

伺服器端系列提供提供您自己識別碼的彈性，而不需依賴瀏覽器機制來設定Cookie。

您可以使用[資料插入API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md)或[大量資料插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，將資料提交至Analytics伺服器端。 建議新的伺服器端實作使用大量資料插入API。 如需兩個API的比較，請參閱「[我應該使用哪個Adobe Analytics工具](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)」。

## 詳細資訊

如需您的企業從第三方Cookie轉移的實際步驟，請參閱[使用Adobe](https://business.adobe.com/solutions/cookieless.html)和深入探討[超越第三方Cookie的思考：您對沒有協力廠商Cookie的世界的完整指南](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)。」

>[!MORELIKETHIS]
[Adobe Analytics 與瀏覽器 Cookie](cookies.md)>
>
