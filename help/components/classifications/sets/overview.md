---
title: 「分類設定」概觀
description: 使用「分類設定」管理分類資料。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 100%

---

# 「分類設定」概觀

「分類設定」會提供管理分類和規則的單一介面。此工作流程會將在報告套裝設定中建立分類的概念和分類匯入工具的概念相結合，以提供更直覺式的介面來建立和管理分類資料。

**[!UICONTROL 元件]** > **[!UICONTROL 分類設定]**

與分類集一起發布的後端架構包含幾個顯著的改進：

* 大幅縮短處理時間 (72 小時 → 24 小時)
* 使用分類集使用者介面的能力
* 未來透過[用於分類資料的 Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html) 在 Adobe Experience Platform 中使用分類資料的選項

與分類集一起發布的後端架構也包含幾個顯著的變更：

* 使用瀏覽器或 FTP 匯入時，一定要啟用「[!UICONTROL 衝突時覆寫]」。
* 使用瀏覽器或 FTP 匯入時，不再支援匯入後立即匯出的選項。匯出必須單獨啟動。
* Analytics 2.0 API `GetDimensions`端點現在回傳用於分類的字串識別碼，而不是數值識別碼。還是可以使用數值識別碼，但 Adobe 建議盡可能使用新的字串識別碼。可以使用 `?expansion=hidden`查詢字串參數檢索數值識別碼。


「分類設定」包含兩個主要區域：

* [**[!UICONTROL 分類設定管理員]**](set-manager.md)：建立、編輯和刪除「分類設定」。
* [**[!UICONTROL 分類設定作業管理員]**](job-manager.md)：檢視分類設定作業的狀態並下載匯出檔案。
