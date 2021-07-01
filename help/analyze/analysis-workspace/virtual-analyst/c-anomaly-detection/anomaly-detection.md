---
description: 您可以在 Analysis Workspace 中根據內容檢視和分析資料異常。
title: 異常偵測概觀
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
feature: AI 工具
role: Business Practitioner, Administrator
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '282'
ht-degree: 100%

---

# 異常偵測概觀

您可以根據 Analysis Workspace 中的內容檢視和分析資料異常。

[「異常偵測」教學影片](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=zh-Hant) (4:53)

[「貢獻分析」教學影片](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/contribution-analysis-workspace.html?lang=zh-Hant) (3:20)

>[!IMPORTANT]
>
>異常偵測功能已從 Reports &amp; Analytics 功能集中移除，現在只能透過 Analysis Workspace 使用。請注意，Adobe Analytics Select 與 Adobe Analytics Foundation 客戶在 Workspace 中只能存取「每日詳細程度」的異常偵測功能。如需更多資訊，請參閱[異常偵測和貢獻分析使用權限](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A)。

「異常偵測」提供一種統計方法，以判斷指定的量度和先前的資料比較有何變更。

異常偵測可讓您區隔「真實訊號」與「雜訊」，接著找出形成這些訊號或異常情形的可能因素。換句話說，可讓您識別哪些統計波動是重要的、哪些不重要。接著您可以找出真正異常的根本原因。此外，您還可以取得可靠的量度 (KPI) 預測。

您可能會調查的異常例子包括：

* 訂單平均值大幅下降
* 低收入訂單發生尖峰
* 試用版註冊發生尖峰或下降
* 登陸頁面檢視次數下降
* 影片緩衝事件的尖峰
* 低影片位元率的尖峰

異常偵測和[貢獻分析](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=zh-Hant)是 Analysis Workspace 的核心工作流程。您可以對任何每日異常情形執行貢獻分析，並將結果內嵌至 Analysis Workspace 專案。

Analysis Workspace 異常偵測的演算法包含

* 除了現有的每日詳細程度，另支援對每小時、每週和每月的詳細程度。
* 感知季節性 (例如「黑色星期五」) 和假日。
