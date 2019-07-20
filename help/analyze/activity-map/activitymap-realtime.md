---
description: 即時頁面分析 (即時模式) 可讓您即時取得分鐘粒度的結果。
seo-description: 即時頁面分析 (即時模式) 可讓您即時取得分鐘粒度的結果。
seo-title: 即時(即時)頁面分析
solution: Analytics
title: 即時(即時)頁面分析
topic: Activity Map
uuid: a3fa9bd-73d8-48b3-be-f818 ed7456 fb
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 即時(即時)頁面分析

即時頁面分析 (即時模式) 可讓您即時取得分鐘粒度的結果。

Activity Map 現在可用 1 到 15 分鐘的增量顯示分析資料，根據選定頁面的微型趨勢監控連結人氣高低。出版企業要追蹤大眾對於某個主題的興趣增加或減少並據以做出回應，或是要監控即時流量時，這一點尤其重要。

身為網站內容擁有者，您的工作之一是了解何時應推廣內容、何時又應移除內容，並讓大家的體驗保持相關。即時資料是這項職責的根基。如果能了解現在的趨勢流行哪些連結和內容，就能迅速、果斷地採取行動，讓讀者和客戶持續關注您的品牌。

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

## Data latency as a result of A4T configuration {#section_806CE36354FC4C539A0DED9266A5C704}

Adobe Target 中的 A4T 整合啟用後，您就會在 Adobe Analytics 中遇到 5 至 10 分鐘的額外延遲。增加此延遲可使 Analytics 和 Target 的資料透過相同的點擊儲存，讓您能夠依頁面和網站區段劃分測試。

此延遲增加的現象會反映在所有 Adobe Analytics 服務和工具中 (包括即時資料流與即時報表)，且適用於下列情況:

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 若是目前轉換量度的資料、已完成的資料及資料摘要，則所有點擊均會額外延遲 5 至 7 分鐘。

Be aware that the latency increase starts after you implement the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), even if you have not fully implemented this integration.
