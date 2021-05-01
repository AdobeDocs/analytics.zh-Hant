---
title: 可降低瀏覽器Cookie限制影響的選項
description: 瞭解如何降低瀏覽器Cookie限制的影響，以改善Adobe Analytics的資料收集。
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 6%

---


# 可降低瀏覽器Cookie限制影響的選項

本檔案說明如何在主要瀏覽器實施Cookie的追蹤防止措施時，跨屬性和解決方案保留永久性訪客識別。

Adobe Analytics依賴第一方Cookie來記錄訪客的網站活動。 Analytics也依賴第三方Cookie來瞭解訪客的離站活動，例如您擁有之其他網域的活動。 協力廠商Cookie在許多瀏覽器上都會遭到封鎖，Chrome即將移除的支援（目前計畫於2022年推出）將無法使用。 第一方Cookie可在所有瀏覽器上使用，但Apple的[ITP追蹤預防](https://webkit.org/tracking-prevention)措施下的Safari和其他瀏覽器有限期。 如需瀏覽器Cookie目前限制的詳細資訊，請參閱「[Adobe Analytics和瀏覽器Cookie](cookies.md)。

這些瀏覽器限制反映出，用戶與其信任的品牌之間已逐漸從匿名第三方追蹤轉向明確分享資訊。 為支援此動作，Adobe可讓客戶加入透過第一方關係收集的持久識別碼，以補充傳統Cookie。

## Customer Journey Analytics與跨裝置分析

[Adobe客戶歷](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) 程分 [析和跨裝置](/help/components/cda/overview.md) 分析使用者，除了Cookie外，還可包含耐用識別碼，例如雜湊登入：

* **客戶歷程分** 析可透過與Adobe Experience Platform的整合，在Analysis Workspace進行跨通道分析。它使用任何ID，在查詢時整合您可用的線上和離線客戶資料，以Experience Platform方式提供。

* **跨裝置分** 析識別數位裝置如何使用Adobe Experience Platform身分服務，在任何ID間對應並銜接使用者歷程。它使用Adobe Experience Cloud裝置合作圖、私人裝置圖或欄位式拼接。

## 伺服器端資料收集

伺服器端系列提供提供您自己識別碼的彈性，而不需依賴瀏覽器機制來設定Cookie。

您可以使用[資料插入API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md)或[大量資料插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，將伺服器端資料匯入Analytics。 如需兩個API的比較，請參閱「[我應該使用哪個Adobe Analytics工具](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)」。

## 詳細資訊

如需您的企業從第三方Cookie轉移的實際步驟，請參閱「[使用Adobe](https://business.adobe.com/solutions/cookieless.html)獲取並讓客戶留在無Cookie世界」和深度「[超越第三方Cookie思考：您對沒有協力廠商Cookie的世界的完整指南](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)。」

>[!MORELIKETHIS]
>
>[Adobe Analytics 與瀏覽器 Cookie](cookies.md)
