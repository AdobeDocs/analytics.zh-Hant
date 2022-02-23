---
title: 大量資料插入 API
description: 批量資料插入API(BDIA)是一種Adobe Analytics功能，它允許您以檔案批次上載伺服器調用資料，而不是使用客戶端庫（如AppMeasurement）。 這些批處理檔案中的伺服器調用可以是當前（即時）資料或歷史資料。 它是Adobe AnalyticsAPI早期版本中資料插入API的更可擴展的後繼項。
solution: Analytics
feature: API
source-git-commit: d8603ddd6cee2ccc930281003d9ff1befa15c95c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 27%

---


# 大量資料插入 API

批量資料插入可解決以下幾種使用情形：

* 從以前的分析系統接收歷史資料

* 使用AppMeasurement不可行的內部分析收集系統。 您可以使用Extract-Transform-Load(ETL)進程將資料放入批處理檔案中，然後使用BDIA將資料上載到Adobe Analytics。

* 從僅間歇性連接到Internet的設備收集資料。 這些設備儲存交互，直到它們收到連接。 然後，設備可以通過BDIA一次性上傳所有資料。

資料插入API和 [批量資料插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)都是將伺服器端收集資料提交給Adobe Analytics的方法。 每發生一個事件時，「資料插入 API」都會被呼叫。「大量資料插入 API」接受含有事件資料的 CSV 格式檔案 (其中每一行儲存一個事件)。 若您正在實施新的伺服器端蒐集作業，建議採用「大量資料插入 API」。