---
title: DFA整合——生命週期結束資訊
description: 為什麼要AdobeDFA資料連接器的生命週期結束，還有哪些替代選擇？
translation-type: tm+mt
source-git-commit: 6669f678c1327b6af4a5b67c8033a9b7d8c9dbcf
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# DFA整合——生命週期結束資訊

Adobe公司最近宣佈了[計畫，計畫終止使用Data Connector](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/data-connectors-eol.html)，這是用於整合第三方資料（如ESP、VOC等）的舊式工具集 和Adobe Analytics。

## 為什麼資料連接器即將淘汰？

合作夥伴整合的支援平台是[AdobeExchange](https://exchange.adobe.com/experiencecloud)，旨在促進Adobe數字型驗應用程式整合、第三方CXM整合，並支援客戶和合作夥伴未來的各種資料需求。 許多使用Data Connectors建立整合的合作夥伴已將這些整合移轉至AdobeExchange，有更多合作夥伴打算這麼做。

## 為什麼DFA整合即將走向生命週期結束？

在[2020年1月，Google宣佈將在2022年前淘汰Chrome中的協力廠商Cookie。 ](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html)這符合Apple和Mozilla分別針對其Safari和Firefox瀏覽器所設定的業界標準。 DFA整合嚴重依賴協力廠商Cookie，因此，跨三大網際網路瀏覽器移除協力廠商Cookie時，將會失效且過時。 Google [在2021年3月宣佈將不發佈替代解決方案，進一步強化了這一立場。](https://blog.google/products/ads-commerce/a-more-privacy-first-web)

不幸的是，谷歌— 擁有DFA整合的DFA。 不太可能在Adobe交換平台上複製。 因此，我們的前進假設是，一旦「資料連接器」離線，現有的整合將停止運作，不會有分類取代。

DFA整合的「檢視」功能是重要且額外的因素。 它可讓Adobe Analytics追蹤使用者看到展示廣告、未點按，但稍後瀏覽網站的案例。 「檢視次數」是以第三方Cookie為基礎，在2021年期間，這些Cookie將繼續淘汰。 這是一個面向整個市場的問題，而不只是一個Adobe問題。 目前，複製此資料的替代方案並不存在。

## 您有哪些替代選擇？

對於有意將展示廣告資料（沒有「檢視」）整合至Adobe Analytics的客戶，我們目前有下列選項：

* Adobe Advertising Cloud DSP客戶可運用與Adobe Analytics的分類整合[來設定從Google到Adobe Analytics的顯示廣告資料。 ](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/ad-cloud/introduction-to-the-analytics-for-advertising-cloud-dsp-integration.html?lang=en#integrations)此項整合是我們的最佳選擇，也是我們對客戶的建議。 Ad CloudDSP允許客戶跨所有廣告通道提供連通的體驗，包括付費搜尋、展示、視訊等。 如需更多詳情，請參閱[此處](https://experienceleague.adobe.com/docs/advertising-cloud/dsp/introduction/dsp-about.html?lang=en#introduction)。但是，Ad CloudDSP也會受到第三方Cookie遺失的影響。
* Adobe Experience Platform和[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en)，它們提供有關顯示和與其他資料來源整合的功能。 客戶可以從付費搜尋提供者下載其顯示資料，並將該資料上傳至Experience Platform。 然後，他們將資料直接匯入CJA，並與其他資料集一起分析。
* Adobe諮詢（工程設計師）可以建立自訂解決方案，將顯示廣告量度內嵌至Adobe Analytics。 此解決方案仍在開發中，歡迎任何有意加入beta版的客戶參與。 當功能、可用性和成本推出時，將會提供更多相關資訊。
* 您可以使用Adobe Analytics的「資料來源」功能和「分類」功能，管理您自己的展示廣告整合。 使用資料來源和分類[手動匯入付費搜尋並顯示資料，如此處](https://experienceleague.adobe.com/docs/analytics/import/use-cases/paid-search-metrics.html?lang=en#use-cases)所述。 (注意：本檔案指付費搜尋，但使用案例和概念相同，可套用於顯示)。

如需其他問題或支援，請聯絡[Adobe客戶服務](https://helpx.adobe.com/contact/enterprise-support.ec.html)。