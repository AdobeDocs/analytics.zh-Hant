---
description: 即時頁面分析 (即時模式) 可讓您即時取得分鐘粒度的結果。
title: 即時頁面分析
feature: Activity Map
role: 業務從業人員、管理員
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 71%

---


# 即時頁面分析（即時模式）

即時頁面分析 (即時模式) 可讓您即時取得分鐘粒度的結果。

Activity Map現在會以1分鐘至15分鐘的增量顯示分析資料，以根據所選頁面的微趨勢監控連結人氣。 出版企業要追蹤大眾對於某個主題的興趣增加或減少並據以做出回應，或是要監控即時流量時，這一點尤其重要。

身為網站內容擁有者，您的工作之一是了解何時應推廣內容、何時又應移除內容，並讓大家的體驗保持相關。即時資料是這項職責的根基。如果能了解現在的趨勢流行哪些連結和內容，就能迅速、果斷地採取行動，讓讀者和客戶持續關注您的品牌。

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

如果您想檢查哪個元素在「即時模式」中大部分被點按：

1. 在工具列的&#x200B;**[!UICONTROL 即時模式]**&#x200B;趨勢線上，選取您要分析的時段。
1. 按一下工具列中的「眼睛」圖示，以存取「連結報表」表格。
1. 依連結排序表格。

## 因為 A4T 設定造成的資料延遲

在Adobe Target啟用[A4T整合](https://docs.adobe.com/content/help/zh-Hant/target/using/integrate/a4t/a4t.html)後，您將在Adobe Analytics再體驗5-10分鐘的延遲。 增加此延遲可使 Analytics 和 Target 的資料透過相同的點擊儲存，讓您能夠依頁面和網站區段劃分測試。

此延遲增加的現象會反映在所有 Adobe Analytics 服務和工具中 (包括即時資料流與即時報表)，且適用於下列情況：

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 若是目前轉換量度的資料、已完成的資料及資料摘要，則所有點擊均會額外延遲 5 至 7 分鐘。

請注意，即使您尚未完全實施該整合，該延遲增加現象也會在您實施[身份服務](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.html)後開始。

詳細資訊[這裡](/help/analyze/activity-map/activitymap-standard-live.md)。