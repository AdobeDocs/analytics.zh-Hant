---
title: 延遲送達點選
description: 瞭解資料摘要如何處理延遲送達點選。
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
TQID: 'https://experienceleague.adobe.com/oB9bBU9KV8O1-IRM20QWBFhQXt1mykn28KITDRTsWqc'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: ede9f3ba-4ee4-4497-9d8e-e9da5848bda0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 317
ht-degree: 48%

---

# 延遲送達點擊 {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="允許延遲送達點擊"
>abstract="選取此選項，可在設定的報告頻率內 (通常是每日或每小時)，納入資料摘要工作完成資料處理之後抵達的資料。 啟用此選項，則每次資料摘要處理資料時，都會查看任何送達的延遲點擊，並將其整批放進下一個傳送的資料摘要檔案中。"

<!-- markdownlint-enable MD034 -->

## 瞭解延遲送達點選

歷史資料可能會在資料摘要工作完成特定小時或當天的處理後才送達，例如透過時間戳記點擊或資料來源。

資料摘要一般在處理資料時，只會在其報表視窗 (通常是最近的小時或當天) 中查看資料。 如果資料在摘要完成該報表視窗的處理後送達，該資料不會納入到任何資料摘要中。

啟用延遲送達點選後，處理方法會變更為納入此資料。 每次資料摘要處理資料時，都會檢視任何已送達的延遲點選，並將它們批次放入下一個已傳送的資料摘要檔案中。

## 啟用延遲送達點選

啟用選項以允許資料摘要的延遲送達點選之前，請考量下列事項：

* 啟用延遲送達點選時，不同天的資料經常會出現在資料摘要中。 請確定您用來內嵌資料摘要的平台可容納相同檔案中不同天的資料。
* 如果重新處理資料摘要檔案，則當在前5天內發生重新處理時，包含在原始檔案中的延遲送達點選會包含在重新處理的檔案中。 5天後，延遲送達點選不會納入重新處理的檔案中。

您可以在建立或編輯資料摘要時啟用延遲送達點選，方法是啟用選項&#x200B;**[!UICONTROL 允許延遲送達點選]**，如[建立資料摘要](/help/export/analytics-data-feed/create-feed.md)中所述。
